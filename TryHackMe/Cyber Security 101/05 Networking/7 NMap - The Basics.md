# 7 NMap - The Basics

## 7.2 Host Discovery: Who is Online
- NMap ways to specify targets:
    - IP Range `-`, if you want to scan all IP addresses from 192.168.0.1 to 192.168.0.10 you can write `192.168.0.1-10`
    - IP Subnet `/`, if you want to scan a subnet it can be expressed as `192.168.0.1/24` - this would be equivalent to 192.168.0.0-255
    - Hostname, can also be specified for example `example.thm`
- NMap offers `-sn` option to discover online hosts on a network (much broad than `ping`)
- Nmap discovers live hosts such as:
    - `-PS[portlist]`
    - `-PA[portlist]`
    - `-PU[portlist]`
- Scan list `-sL`, list the targets to scan without actually scanning them

## 7.3 Port Scanning: Who is Listening
- `-sn` is used to discover live hosts.
- but this time, we want to discover the `network services` *listening* on these live hosts. Network services include:
    - `web servers`, usually listens to TCP port 80 and 443
    - `DNS servers`, usually listens to UDP (and TCP) port 53
### Scanning TCP Ports
- easiest way to know whether a TCP port is open would be to `telnet` to the port. Only open TCP ports would respond appropriately and allow TCP connection to be established.
#### Connect Scan
- can be triggered using `-sT`, it tries to complete the TCP-three way handshake with every target TCP port.
- If TCP port is open and Nmap connects, Nmap will tear down the established connection.
#### SYN Scan (Stealth)
- SYN scan can only execute the first step: send a TCP SYN packet.
- advantage is that it lead to few logs as the connection is never established, thus considered a `realtively stealth scan`.
- can be executed using `-sS` flag.
### Scanning UDP Ports
- UDP does not require establishing a connection and tearing it down afterwards
- very suitable for `real-time communication`
- Nmap offers the option `-sU` to scan UDP services
### Limiting the Target Ports
- Nmap scans the most common 1000 ports by default
- Nmap offers a few more options:
    - `-F` for Fast mode, which scans the 100 most common ports (instead of the default 1000)
    - `-p[range]` allows you to specify a range of ports to scan:
        - `-p10-1024` scan from port 10 to port 1024
        - `-p-25` scann all ports between 1 and 25
        - `-p-` scan all ports and is equivalent to `-p1-65535`
        - `p1-1023` scan for well-known ports

## 7.4 Version Detection: Extract More Information
### OS Detection
- enable OS Detection by adding the `-O` option - triggers Nmap to rely on various indicators to make an educated guess about the target OS.
### Service and Version Detection
- `-sV` enables version detection - convenient for gathering more information.
- `-A` option enables OS detection, version scanning, traceroute, and among other things.
### Forcing the Scan
- `-Pn` scan hosts that appear to be down

##
