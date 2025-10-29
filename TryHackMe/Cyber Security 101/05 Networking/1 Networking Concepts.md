# 1 Networking Concepts

## 1.2 OSI Model
- `Open Systems Interconnection (OSI) Model` conceptual model developed by the `International Organization for Standardization (ISO)` that describes how communications should occur in a computer network.
- Composed of 7 layers, namely:
    1. **Physical Layer**, deals with physical connection between devices.
    2. **Data Link Layer**, describes an agreement between different systems on the same network on how to communicate (protocol that enables transfers between nodes on the same network).
    3. **Network Layer**, concerned with sending data between different networks (logical addressing and routing, finding a path to transfer network packets between diversed networks).
    4. **Transport Layer**, enables end-to-end communication between running applications on different hosts. Ex. `Transimission Controll Protocol (TCP), User Datagram Protocol (UDP)`.
    5. **Session Layer**, responsible for establishing, maintaining, and synchronizing communication between application running on different hosts. Ex. `Network File System (NFS), Remote Procedure Call (RPC)`.
    6. **Presentation Layer**, handles data encoding, compression, and encryption (something that the application layer can understand).
    7. **Application Layer**, provides network services directly to end-user applications. Ex. `HTTP, FTP, DNS, POP3, SMTP, IMAP`.

## 1.3 TCP/IP Model
- `Transmission Control Protocol / Internet Protocol (TCP/IP) Model` developed by the `Department of Defense (DoD)`.
- Composed of 4 layers, namely:
    1. **Link Layer**, layer 2 of OSI Model.
    2. **Internet Layer**, layer 3 of OSI Model.
    3. **Transport Layer**, layer 4 of OSI Model.
    4. **Application Layer**, grouped version of layers 5,6,7 of OSI Model.
- in modern textbooks, they also include `Layer 1: Physical Layer`.

## 1.4 IP Addresses and Subnets
- IP addresses are composed of `four octets, 32-bits`. Being 8 bits, an octet allows us to represent a decimal number between `0 and 255`.
- `0` is reserved for `network address`, while `255` is reserved for `broadcast address`.

### Looking up your Network Configuration
- line command, `ipconfig` for Windows.
- line command, `ifconfig`, `ip address show` or `ip a s` for Linux / UNIX-based systems.

### Private Addresses
- `RFC 1918` defines the following ranges of private IP addresses:
    - `10.0.0.0` - `10.255.255.255` (`10/8`)
    - `172.16.0.0` - `172.31.255.255` (`172.16/12`)
    - `192.168.0.0` - `192.168.255.255` (`192.168/16`)

## 1.5 UPD and TCP
- protocols that enable processes on networked hosts to communicate with each other.
- valid port numbers ranges between `1 and 65535`.
- `User Datagram Protocol (UDP)` simple connectionless protocol that operates at the transport layer (layer 4).
    - does not need to `establish a connection`.
    - does not provide a mechanism to know that the packet has been delivered.
- `Transmission Control Protocol (TCP)` a connection-oriented protocol, also operates at the transport layer (layer 4).
    - requires establishment of a TCP connection before any data can be sent.
    - connection is established using the `three-way-handshake`.
        - SYN, client initiate connection to server.
        - SYN-ACK, server responds to packet.
        - ACK, client sends acknowledgement on receiving the SYN-ACK packet.