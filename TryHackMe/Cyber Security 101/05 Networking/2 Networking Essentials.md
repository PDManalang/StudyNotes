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

## 2.5 Routing
- routing algorithms:
    1) `Open Shortest Path First (OSPF)`allows routers to share information about the network topology and calculate the most efficient paths for data transmission.
    2) `Enhanced Interior Gateway Routing Protocol (EIGRP)` a Cisco proprietary protocol that combines aspects of different routing algorithms. Allows routers to share information about the networks they can reach and the cost (bandwidth or delay) associated with those routes - then use this information to choose the most efficient paths for data transmission.
    3) `Border Gateway Protocol (BGP)` primary routing protocol used on the Internet. It allows different networks (like ISPs) to exchange routing information and establish paths for data to travel between these networks. Helps ensure that data cab be routed efficiently across the Internet, even when traversing multiple networks.
    4) `Routing Information Protocol (RIP)` simple routing protocol often used in small networks. Share information about networks they can reach and number of hops (routers) required to get there. As a result, each router builds a routing table based on this information, choosing the routes with the fewest hops to reach the destination.

## 2.6 NAT
- `Network Address Transmission (NAT)` a solution to address the depletion of IPv4 address space.
- the idea lies in using `one public IP address` to provide Internet access to `many private IP addresses`.
- routers that support NAT must find a way to track `ongoing connections`.
- NAT-supporting routers maintain a table translating network addresses between internal and external networks.