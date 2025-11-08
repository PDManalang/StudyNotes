# 4 Networking Secure Protocols

## 4.2 TLS
- `Secure Sockets Layer (SSL)`
- `Transport Layer Security (TLS)`
    - a cryptographic protocol operating at OSI model's `transport layer`.
    - allows secure (confidentiality and integrity) communication between a client and server over a insecure network.
    - ensures that no once can read or modify the exchanged data.
- To get a `TLS Certificate`, the server admin will create a `Certificate Signing Request (CSR)` and submits to a `Certificate Authority (CA)`.

## 4.3 HTTPS
- `HTTP` relies on TCP and uses `port 80` by default.
- As observed using `telnet`, traffic was sent in cleartext for anyone to intercept and monitor.
- common steps before web browser request a page over HTTP:
    1. Establish a TCP three-way handshake with target server
    2. Communicate using HTTP protocol, example `GET / HTTP/1.1
- `HTTPS over TLS` will require the following steps:
    1. Establish a TCP three-way handshake with target server
    2. Establish a TLS session
    3. Communicate using HTTP protocol, example `GET / HTTP/1.1
- adding TLS to HTTP leads to all packets being encypted, we can no longer see the contents of exchanged packets unless we get the private key.

## 4.4 SMTPS, POP3S, and IMAPS

### Insecure Version (TCP)
![TCP Ports](TCP-Ports.png)

### Secure Version (TLS)
![TLS Ports](TLS-Ports.png)

## 4.5 SSH
- `Secure Shell (SSH)` protocol more secure version of telnet.
- `OpenSSH`, an open-source implementation of SSH. Benefits:
    - **secure authentication**, besides password authentication, it also supports public key and two-factor auth.
    - **confidentiality**, end-to-end encryption - protection from eavesdropping.
    - **integrity**, cryptography protects the integrity of the traffic.
    - **tunneling**, create secure tunnel to other protocols (much like a VPN connection).
    - **X11 forwarding**, if you connect to a Unix-like system with a GUI, SSH allows you to use graphical application over the network.
- SSH listens to `port 22`.

## 4.6 SFTP and FTPS
- `SSH File Transfer Protocol (SFTP)`

## 4.7 VPN
- `Virtual Private Network (VPN)`, connect remotely to the main branch.