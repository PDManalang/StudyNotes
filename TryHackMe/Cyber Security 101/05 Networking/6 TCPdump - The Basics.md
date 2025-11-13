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