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