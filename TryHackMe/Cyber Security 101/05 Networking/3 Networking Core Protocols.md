# 3 Networking Core Protocols

## 3.2 DNS:Remembering Addresses
- `Domain Name System (DNS)`, responsible for **mapping domain name to an IP address**.
- DNS operates on `Layer 7`.
- DNS traffic uses `UDP port 53 by default` and `TCP port 53 as a fallback default`.
- DNS records:
    1. `Address (A) Record`, maps a hostname to one or more IPv4 addresses. Ex. you can set `example.com` to resolve to `172.17.2.172`.
    2. `AAAA (Quad-A) Record`, similar to A Record but for IPV6 addresses. The (A)AAA refers to `Authentication,Authorization,and Accounting`.
    3. `Canonical Name (CNAME) Record`, maps a domain name to another domain name. Ex. `www.example.com` can be mapped to `example.com` or `example.org`.
    4. `Mail Exchange (MX) Record`, specifies the mail server responsible for handling emails for a domain.

## 3.3 WHOIS
- provides information about an entity that registered a domain name, including their name, phone number, email, and address.

## 3.4 HTTP(S):Accessing the Web