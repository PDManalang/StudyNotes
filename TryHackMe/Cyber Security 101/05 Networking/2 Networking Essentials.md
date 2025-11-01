# 2 Networking Essentials

# 2.2 DHCP
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