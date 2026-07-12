#  03 - OSI Model

The **Open Systems Interconnection (OSI) Model** is a conceptual framework developed by the **International Organization for Standardization (ISO)** to standardize how different networking systems communicate. It divides network communication into **seven logical layers**, where each layer performs a specific function and communicates with the layers directly above and below it.

Although modern networks primarily use the **TCP/IP model**, the OSI model remains the industry standard for understanding, designing, and troubleshooting networks.

---

# 1. What is the OSI Model?

The **OSI (Open Systems Interconnection) Model** is a **7-layer reference model** that describes how data moves from one device to another across a network.

Each layer has a specific responsibility. Instead of one large process handling everything, networking tasks are divided into smaller layers, making communication easier to understand, develop, and troubleshoot.

### Key Characteristics

* Contains **7 layers**
* Each layer performs a specific function
* Uses **encapsulation** and **decapsulation**
* Helps vendors build compatible networking products
* Used mainly for learning and troubleshooting

---

# 2. Why Was the OSI Model Created?

Before the OSI model, networking vendors developed proprietary communication methods. Devices from different manufacturers often could not communicate with each other.

The OSI model introduced a standardized framework so that different systems could communicate using common networking principles.

### Benefits

* Standardizes network communication
* Simplifies troubleshooting
* Supports interoperability
* Makes network design easier
* Helps students understand networking concepts

---

# 3. The Seven OSI Layers

```
+---------------------------+
| Layer 7 | Application     |
+---------------------------+
| Layer 6 | Presentation    |
+---------------------------+
| Layer 5 | Session         |
+---------------------------+
| Layer 4 | Transport       |
+---------------------------+
| Layer 3 | Network         |
+---------------------------+
| Layer 2 | Data Link       |
+---------------------------+
| Layer 1 | Physical        |
+---------------------------+
```

---

# 4. Layer-by-Layer Explanation

## Layer 7 – Application

### Purpose

Provides network services directly to end-user applications.

### Responsibilities

* Web browsing
* Email services
* File transfers
* Network management

### Common Protocols

* HTTP
* HTTPS
* FTP
* SMTP
* POP3
* IMAP
* DNS
* DHCP
* SNMP

### PDU

**Data**

### Real-World Example

Opening a website in a browser.

---

## Layer 6 – Presentation

### Purpose

Ensures data is presented in a format the receiving application can understand.

### Responsibilities

* Data translation
* Encryption
* Decryption
* Compression
* Decompression

### Examples

* SSL/TLS encryption
* JPEG images
* PNG images
* MP3 audio
* MPEG video

### PDU

**Data**

---

## Layer 5 – Session

### Purpose

Establishes, maintains, and terminates communication sessions.

### Responsibilities

* Session setup
* Session management
* Synchronization
* Session termination

### Examples

* Remote Desktop
* NetBIOS
* RPC

### PDU

**Data**

---

## Layer 4 – Transport

### Purpose

Provides reliable or best-effort delivery between end devices.

### Responsibilities

* Segmentation
* Error recovery
* Flow control
* Port numbers
* Reliability

### Protocols

* TCP
* UDP

### PDU

* Segment (TCP)
* Datagram (UDP)

### Address Used

**Port Number**

---

## Layer 3 – Network

### Purpose

Provides logical addressing and determines the best path to the destination.

### Responsibilities

* Routing
* IP addressing
* Packet forwarding

### Protocols

* IPv4
* IPv6
* ICMP
* OSPF
* RIP
* EIGRP

### Device

Router

### PDU

Packet

### Address Used

IP Address

---

## Layer 2 – Data Link

### Purpose

Transfers data between devices on the same local network.

### Responsibilities

* MAC addressing
* Framing
* Error detection
* Switching

### Protocols

* Ethernet (IEEE 802.3)
* PPP
* HDLC
* ARP

### Devices

* Switch
* Bridge

### PDU

Frame

### Address Used

MAC Address

---

## Layer 1 – Physical

### Purpose

Transmits raw bits across the physical medium.

### Responsibilities

* Electrical signals
* Optical signals
* Wireless signals
* Cabling
* Connectors

### Devices

* Hub
* Repeater
* Cables
* Connectors

### PDU

Bits

---

# 5. OSI Layer Summary

| Layer | Name         | PDU     | Address     | Device     |
| ----: | ------------ | ------- | ----------- | ---------- |
|     7 | Application  | Data    | -           | PC         |
|     6 | Presentation | Data    | -           | PC         |
|     5 | Session      | Data    | -           | PC         |
|     4 | Transport    | Segment | Port        | Firewall   |
|     3 | Network      | Packet  | IP Address  | Router     |
|     2 | Data Link    | Frame   | MAC Address | Switch     |
|     1 | Physical     | Bits    | -           | Hub, Cable |

---

# 6. Encapsulation

As data travels from the sender to the receiver, each OSI layer adds its own header.

```
Application Data
        ↓
TCP Header
        ↓
IP Header
        ↓
Ethernet Header
        ↓
Frame
        ↓
Bits
```

---

# 7. Decapsulation

The receiving device removes each header in reverse order until the application receives the original data.

```
Bits
 ↓
Frame
 ↓
Packet
 ↓
Segment
 ↓
Data
```

---

# 8. Data Flow Example

A user opens **[www.example.com](http://www.example.com)**.

1. Browser creates an HTTP request.
2. Transport layer adds a TCP header.
3. Network layer adds an IP header.
4. Data Link layer adds a MAC header.
5. Physical layer transmits bits.
6. The destination host removes each header.
7. The web server processes the request.
8. A response is returned to the client.

---

# 9. OSI vs TCP/IP

| OSI                | TCP/IP                |
| ------------------ | --------------------- |
| 7 Layers           | 4 Layers              |
| Reference Model    | Protocol Suite        |
| Mainly Educational | Used in Real Networks |
| Developed by ISO   | Developed by DoD      |

---

# 10. Troubleshooting with the OSI Model

| Layer        | Common Issue               |
| ------------ | -------------------------- |
| Physical     | Cable unplugged            |
| Data Link    | VLAN mismatch              |
| Network      | Incorrect IP address       |
| Transport    | Blocked port               |
| Session      | Session timeout            |
| Presentation | Encryption mismatch        |
| Application  | DNS or application failure |

---

# 11. Memory Trick

Top → Bottom

**All People Seem To Need Data Processing**

Bottom → Top

**Please Do Not Throw Sausage Pizza Away**

---

# 🚀 Next Step

Now that you understand the **OSI Model** and the responsibilities of its seven layers, it's time to learn how modern networks actually communicate.

While the OSI Model provides a **conceptual framework** for understanding network communication, real-world networks use the **TCP/IP Model**, which forms the foundation of the Internet and most modern communication systems.

**➡️ Next Lab:**  
**[04 - TCP/IP Model](../04_TCP_IP_Model/README.md)**
