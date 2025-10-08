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

### 1.4 Making a Request
What happens when you make a DNS Request
1. Computer checks the `local cache` first if you've previously looked up, if not a request to your `Recursive DNS Server` will be made.
2. `Recursive DNS Server` is usually provided by your **ISP** - looks up the `local cache` (usually with services like Facebook, Twitter, Google), if not found it will start looking into the `Internet's root DNS servers`.
3. `root servers` act as **DNS backbone of the Internet** - their job is to redirect you to the correct `TLD Server`. Example you request for `tryhackme.com`, it will recognize the TLD of `.com` and will refer you to TLD server that deals with `.com addresses`.
4. `authorative server` or also known as `nameserver`, multiple nameservers that act as a `backup` in case one goes down.

### 1.5 Extra Learning
- `nslookup` command tool used for querying DNS to obtain information about `domain names and IP addresses`. primary uses:
  - Find IP Address of Domains
  - Perform Reverse DNS Lookups
  - Check DNS Records
  - Test DNS Server Configuration
  - Troubleshoot Network Problems

## 2 HTTP in Detail
### 2.1 What is HTTP?
- **Hypertext Transfer Protocol (HTTP)** used when viewing a website. It is the set of rules used for communicating with web servers for transmitting webpage data (ex. HTML, Images, Videos, etc.)
- **Hypertext Transfer Protocol Secure (HTTPS)** a `secure` version of HTTP. Data is `encrypted`, not only that it stops people from seeing the data you are receiving and sending, but it also assures that you're talking to the correct web server (not an impersonator).
