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

### 2.2 Requests and Responses
**Uniform Resource Locator (URL)** an instruction on how to access Internet resource.
<img width="1140" height="270" alt="image" src="https://github.com/user-attachments/assets/313fb5a7-0c54-4396-b1bc-2ee64cb0d1d2" />

Features of URL
- **Scheme:** protocol to use (ex. HTTP, HTTPS, FTP).
- **User:** user authentication (as required by some websites).
- **Host:** domain name or ip address of server you wish to access.
- **Port:** port you're going to connect to, usually `80` for `HTTP` and `443` for `HTTPS` (but can be hosted by any port between 1-65535).
- **Path:** file name or location of resource you're trying to access.
- **Query String:** extra bits of information that can be sent from requested path. (ex. `/blog?id=1` would tell blog path that wish to receive blog article with id=1.)
- **Fragment:** reference to a location on the actual page requested.

### 2.3 HTTP Methods
- **GET Request** getting information from a web server.
- **POST Request** submitting data to a web server and potentially create new records.
- **PUT Request** submitting data to a web server to update information.
- **DELETE Request** deleting information/data from a web server.

### 2.4 HTTP Status Codes
**HTTP Status Codes**
- **100-199 Information Response**
  - sent to tell the client that their request is accepted and can proceed. These codes are no longer common.
- **200-299 Success**
  - sent to tell the client that their request was successful.
- **300-399 Redirection**
  - redirect the client request to another resource.
- **400-499 Client Errors**
  - inform client that there's an error with their request.
- **500-599 Server Errors**
  - reserved errors that are happening on the server-side, usually indicate a `major problem` with the server handling the request.

**Common HTTP Status Codes**
- **200 OK**
  - request completed successfully.
- **201 Created**
  - resource has been created (ex. a new user or new blog post).
- **301 Moved Permanently**
  - redirect the client to a new webpage or tells search engine that the page has moved elsewhere.
- **302 Found**
  - similar to `code 301` but can be temporary and may change again in the future.
- **400 Bad Request**
  - tells the browser that something is wrong or missing in their request.
- **401 Not Authorized**
  - you are not allowed to view this resource until you have authorization.
- **403 Forbidden**
  - you do not have the permission to view this resource (whether you're logged in or not).
- **405 Method Not Allowed**
  - resource does not allow this method request (ex. you send a `GET` request, but it was expecting a `POST` request instead).
- **404 Page Not Found**
  - page/resource you request does not exist.
- **500 Internal Service Error**
  - server has encountered some kind of error in your request that it doesn't know how to handle properly.
- **503 Service Unavailable**
  - server cannot handle your request as it's either overloaded or down for maintenance.

HTTP Status Code Learning Resource (taught by Cats HAHA) - (https://http.cat/)


