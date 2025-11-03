# 2 Networking Essentials

## 2.2 DHCP
- Needed configurations to access a network:
    - IP address (+subnet mask)
    - Router (or gateway)
    - DNS server
- `Dynamic Host Configuration Protocol (DHCP)`, application-level protocol that relies on `UDP` (server listens on `UDP port 67`, while client sends from `UDP port 68`).
- DHCP follows four steps:
    1) DHCP `Discover`, client broadcasts a DHCPDISCOVER message seeking the local DHCP server if one exists.
    2) DHCP `Offer`, server responds with DHCPOFFER message with an IP address available for client to accept.
    3) DHCP `Request`, client responds with DHCPREQUEST message to indicate that it has accepted the offered IP.
    4) DHCP `Acknowledgement`, server responds with DHCPACK message to confirmed IP address is now assigned to this client.

## 2.3 ARP
- `Address Resolution Protocol (ARP)` makes it possible to find the MAC address of another device on the Ethernet.
- An ARP Request or ARP Reply is `not encapsulated within UDP or IP packet`, it is directly with the `Ethernet frame`.

## 2.4 ICMP
- `Internet Control Message Protocol (ICMP)` used for network diagnostics and error reporting.
- the two popular commands that rely on ICMP:
    - `ping` command that uses ICMP to `test the connectivity to a target system and measures that round-trip time (RTT)`. Use to learn that target is alive and it's relpy can reach our system.
    - `traceroute (tracert)` uses ICMP to discover the route from your host to the target.