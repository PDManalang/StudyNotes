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
- `Hypetext Transfer Protocol (HTTP) / Hypertext Transfer Protocol (HTTPS)`, this protocol relies on `TCP` and defines how web browser communicates with web servers.
- commands/methods issued by web browser to communicate with webserver:
    1. `GET` retrieves data from a server, such as an HTML file or image.
    2. `POST` allows us to submit new data to the server, such as submitting a form or uploading a file.
    3. `PUT` used to create new resource on the server and to update or overwrite existing information.
    4. `DELETE` delete specified file or resource on the server.
- HTTP(S) commonly use TCP ports `80 and 443`, and less commoly other ports such as `8080 and 8443`.

## 3.5 FTP: Transferring Files
- `File Transfer Protocol (FTP)`, designed to transfer files.
- commands defined by FTP protocol are:
    - `USER` to input username
    - `PASS` to input password
    - `RETR` (retrieve) used to download a file from FTP server to a client.
    - `STOR` (store) used to upload a file from client to FTP server.
- FTP listens to TCP `port 21` by default; data transfer is conducted via another connection from the client to the server.