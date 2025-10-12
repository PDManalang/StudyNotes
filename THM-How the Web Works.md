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

### 2.5 Headers
**Common Request Headers**
(these headers are sent `from the client (your browser) to the server`)
- **Host** as some web servers host multiple websites, this can help you tell which one you require.
- **User-Agent** this is your browser `software and version number`, can help format the website properly for your browser.
- **Content-Length** tells the webserver `how much data to expect` in the web request.
- **Accept-Encoding** tells the web server what types of `compression methods` the browser supports.
- **Cookie** help remember your information.

**Common Response Headers**
(these headers are `returned back to the client` from the server after a request)
- **Set-Cookie** information to store which gets sent back to the web server on each request.
- **Cache-Control** how long to store content of the response in the browser's cache before it requests it again.
- **Content-Type** tells the client what type of data is being returned.
- **Content-Encoding** what method has been used to compress the data to make it smaller when sending over the Internet.

### 2.6 Cookies
- **Cookies** a small piece of data that is stored in your computer. Can be used to remind the computer who you are.
- **Set-Cookies** header response that you receive once cookies are saved.

## 3 How Websites Work
### 3.1 How Websites Work

**Web Server** a dedicated computer that handles requests.

Major components that makes up a website:
- **Front-end (Client-Side)** the way a browser renders a website.
- **Back-end (Server-Side)** a server that processes request and returns a response.

### 3.2 HTML
Websites are primarily created using:
- **HTML** build websites and define their structure.
- **CSS** make websites look pretty (styling options).
- **JavaScript** implement features to make pages interactive.

**HyperText Markup Language (HTML)** is the language websites are written in. **Elements (also known as `tags`)** are the building blocks of HTML pages and tells the browser how to display content.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Example Heading</h1>
    <p>Example Paragraph..</p>
  </body>
</html>
```
The HTML structure (as shown above) has the following components:
- The `<!DOCTYPE html>` defines that the page is a HTML5 document. Helps `standardized` for a browser to use HTML5 to interpret the page.
- The `<html>` the `root` element of HTML page - all other elements come after this.
- The `<head>` contains information about the page (such as the title page).
- The `<body>` defines the content shown in the browser.
- The `<h1>` defines a large heading.
- The `<p>` defines a paragraph.
- and many more elements (ex. `<img>,<button>`)

### 3.3 JavaScript
**JavaScript (JS)** used to control the functionality of web pages (dynamic updates on the page in real-time).

### 3.4 Sensitive Data Exposure
- occurs when a website doesn't properly protect (or remove) sensitive clear-text information to the end-user (usually found in the front-end source code).
- can potentially leveraged to further an attacker's access within different parts of a web application.

### HTML Injection
- a vulnerability that occurs when `unfiltered user input is displayed on the page`.
- **Input Sanitisation** filters any `malicious` text that a user inputs into a website.

## 4 Putting it all together
### 4.1 Putting it all together
To summarize the process behind-the-scenes when requesting a webpage in your browser:
1. Request website in your browser (domain name or IP address)
2. Find Web Server IP address with DNS
3. Connect to Web Server
4. View Website

### 4.2 Other Components
**Load Balancers**
- ensure that high traffic websites can handle the load and provide a failover if server becomes unresponsive.
- will initially receive the request, then forward to one of the multiple servers behind it.
- perform periodic checks with each server ensuring that they are running correctly, this is called `health check`.

**Content Delivery Networks (CDN)**
- excellent resource for cutting down traffic to a busy website.
- host requests across thousands of servers (works out where the nearest server is physically located).

**Databases**
- use by web server to store and recall data.

**Web Application Firewall (WAF)**
- is what sits between `web request and web server`.
- primary purpose is to protect the web server from hacking or denial of service attacks.
- analysese web request for common attack techniques (if request by real browser or a bot).
- checks if an excessive amount of web requests are being sent (utilizing `rate limiting`).

### 4.3 How Web Servers Work
**Web Server**
- a software that *listens for incoming connections and utilizes HTTP protocol to deliver web content to clients*.
- common web server(s): *Apache,Nginx,IIS,and NodeJS*.

**Virtual Hosts**
- text-based configuration files.
- allows web servers to host multiple websites with different domain names.

**Static vs Dynamic Content**
- *Static* a content that never changes.
- *Dyanmic* on the other hand, is content that could change with different request. Changes made are done in what is called the `Backend` (done behind the scenes). While `Frontend` is what you see in your browser.

**Scripting and Backend Languages**
- example langauges: PHP, Python, Ruby, NodeJS, Perl, and many more.


