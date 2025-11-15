# 6 TCPdump - The Basics

## 6.1 Introduction
- The `Tcpdump` tool and its `libpcap` library are written in C and C++ and were released for Unix-like systems in the late 1980s or early 1990s.
- The `libpcap` library is the foundation for various networking tools today, it was also ported to Windows as `winpcap`.

## 6.2 Basic Packet Capture

### Specify the Network Interface
- first thing to decide in which network interface to listen to using `-i INTERFACE`.
- to listen on all available interfaces use `-i any`.
- can also specify an interface you want to listen on, like `-i eth0`.
- command like `ip address show (ip a s)` would list all available network interfaces.

### Save Captured Packets
- in many cases, you will check captured packets again, you can save a file using `-w FILE`.
- file extension is most commonly set to `.pcap`.

### Read Captured Packets from a File
- you can use `Tcpdump` to read packets by using `-r FILE`.
- can be useful for learning protocol behavior.

### Limit the Number of Captured Packets
- you can specify the number of packets to capture by using `-c COUNT`.
- without specifying a count, the packet capture will continue till you interrupt it by pressing `CTRL-C`.

### Don't Resolve IP Addresses and Port Numbers
- Tcpdump will resolve IP addresses and print friendly domain names where possible - to avoid making such DNS lookups, use the `-n` argument.
- Similarly if you don't want port numbers to be resolved, such as `80` being resolved to `http`, use the `-nn` to stop both DNS and port number lookups.

### Produce (More) Verbose Output
- if you want to print more details about the packets, use `-v` to produce a slightly more verbose output. This will print "the time to live, identification, total length and options in an IP packet.
- commands like `-vv` and `-vvv` does the same but more verbosity.
- `man tcpdump` for TCPdump manual page.

### Examples
- `tcpdump -i eth0 -c 50 -v` captures and displays 50 packets by listening on `eth0` (wired ethernet), and displays them verbosely.
- `tcpdump -i wlo1 -w data.pcap` captures packets by listening on port `wlo1` (WiFi interface) and writes the packets to `data.pcap`. It will continue to capture till user interrupts.
- `tcpdump -i any -nn` captures all packets on all interfaces and displays then without domain name and protocol resolution.

## 6.3 Filtering Expressions

### Filter by Host
- `host IP or host HOSTNAME` can be used if you're only interested in IP packets exchanged with a specific network or server.
- `src host IP or src host HOSTNAME` can be used if you want to limit the packets from a particular source.
- `dst host IP or dst host HOSTNMAE` can also be done for particular destination.

### Filter by Port
- `port PORT_NUMBER` can be used if you want to limit captured packets on a specified port.
- `src port PORT_NUMBER` or `dst port PORT_NUMBER` can also be used to limit the source and destination port.

### Filter by Protocol
- protocol examples that can be used in filtering, `ip`, `ip6`, `udp`, `tcp`, and `icmp`

### Logical Operators
- `and`, capture packets if both conditions are true. example `tcpdump host 1.1.1.1 and tcp`.
- `or`, capture packets if either one of conditions is true. example `tcpdump udp or icmp`.
- `not`, capture packets when the condition is not true. example `tcpdump not tcp` -> capture all packets except TCP segments.

### Examples
- `tcpdump -i any tcp port 22` listen on all interfaces and capture tcp packets to or from port 22 (SSH traffic).
- `tcpdump -i wlo1 udp port 123` listen on WiFi network and filter udp traffic to port 123 (Network Time Protocol, NTP).
- `tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap` listen to eth0 and filter traffic exchanged with example.com that uses tcp port 443 (HTTPS traffic related to example.com).
- `tcpdump -r traffic.pcap dst host 1.1.1.1 and arp` to get ip address host that's asking for MAC address of IP 1.1.1.1 (ARP protocol handles MAC address).
- `tcpdum -r traffic.pcap port 53 -c 5` to get the hostname of the first DNS query (port 53 is used by default).

## 6.4 Advanced Filtering
- `greater LENGTH` filter packets that have a length greater or equal to the specified length.
- `less LENGTH` filter packets that have a length less or equal to the specified length.
- `man pcap-filter` manual page (as reference).

### Binary Operations
- `& (AND)` takes two bits and returns 0 unless both inputs are 1.
- `| (OR)` take two bits and returns 1 unless both inputs are 0.
- `! (NOT)` takes one bit and inverts it; an input of 1 gives 0, and an input of 0 gives 1.

### Header Bytes
- purpose is to be able to filter packets based on the contents of a header byte.
- `proto [expr:size]` refer to the contents of any byte in the header.
    - `proto` refers to protocol, such as `arp`, `ether`, `icmp`, `ip`, `ip6`, `tcp`, and `udp`.
    - `expr` indicates byte offset, where 0 refers to first byte.
    - `size` indicate number of bytes that interest us, can be one, two, or four (optional and is one by default).

### Examples
- `ether[0] & 1 != 0` takes that first byte in the Ethernet header and decimal number 1 and applies the `& (AND)`. It will return true if the result is not equal to the number 0. Purpose of the filter is to show packets sent to a multicast address. A multicast Ethernet address is a particular address that identifies a group of devices intended to receive the same data.
- `ip[0] & 0xf != 5` takes the first byte in the IP header and compares it with hexadecimal number F. It will return true if result is not equal to decimal number 5. Purpose is to catch all IP packets with options.

### TCP Flags
- `tcp[tcpflags]` to refer to the TCP flags field. availabe to compare with:
    - `tcp-syn` TCP Synchronize
    - `tcp-ack` TCP Acknowledge
    - `tcp-fin` TCP Finish
    - `tcp-rst` TCP Reset
    - `tcp-push` TCP Push
- based on above, we can write:
    - `tcpdump "tcp[tcpflags] == tcp-syn"` to capture TCP packets with only SYN flag set, while all other flags are unset.
    - `tcpdump "tcp[tcpflags] & tcp-syn != 0"` to capture TCP packets with at least the SYN flag set.
    - `tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"` to capture TCP packets with at least the SYN or ACK flags set.