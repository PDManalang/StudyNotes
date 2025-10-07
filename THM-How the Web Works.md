# How the Web Works

## 1 DNS in Detail
### 1.1 What is DNS?
**Domain Name System (DNS)** provides a simple way to communicate with devices on the Internet without remembering complex numbers.
> So instead of remembering 104.26.10.229, you can remember tryhackme.com instead.

### 1.2 Domain Hierarchy
**Top-Level Domain (TLD)** is the most righthand part of a domain name. So for `tryhackme.com` TLD is `.com`.
Two types of TLD:
- **Generic Top Level (gTLD)** - meant to tell the domain's purpose. Example `.com` is for `commercial`, `.org` is for `organization`.
- **Country Code Top Level (ccTLD)** - used for geographical purpose. Example `.ca` is for sites based on `Canada`, `.uk` for `United Kingdom`.

**Second-Level Domain** taking `tryhackme.com` as an example, the Second-Level Domain is `tryhackme`.

**Subdomain** sits on the left-hand side of Second-Level Domain using a period to separate it. For example `admin.tryhackme.com`, the `admin` part is the subdomain.

### 1.3 Record Types
- **A Record** resolve to IPv4 addresses
- **AAAA Record** resolve to IPv6 addresses
- **CNAME Record** resolve to another domain name. Example, THM's online shop has the subdomain name `store.tryhackme.com` which returns a CNAME record `shops.shopify.com`.
- **MX Record** resolve to the address of the servers that handle the email for the domain you are querying. Example MX record response for `tryhackme.com` would look something like `alt1.aspmx.l.google.com`.
- **TXT Record** free text fields where any text-based data can be stored.

