# 04 - TCP/IP Model

The **TCP/IP (Transmission Control Protocol/Internet Protocol) Model** is the standard networking model used by the Internet and modern computer networks. Unlike the OSI Model, which is a conceptual reference model, the TCP/IP Model is a practical protocol suite that defines how devices communicate over a network.

It consists of **four layers**, each responsible for a specific part of the communication process. Together, these layers ensure that data is transmitted reliably from a source device to a destination device.

---

# What is the TCP/IP Model?

The **TCP/IP Model** is a framework that describes how data is transmitted across interconnected networks using the **TCP/IP protocol suite**.

Every time you browse a website, send an email, stream a video, or connect to a remote server, your device uses the TCP/IP Model to communicate.

Unlike the OSI Model, which mainly serves as a reference for understanding networking concepts, the TCP/IP Model is implemented in almost every modern operating system and networking device.

---

# Why is the TCP/IP Model Important?

The TCP/IP Model provides a standardized method for communication between different devices and networks.

### Benefits

* Enables communication between different operating systems.
* Forms the foundation of the Internet.
* Supports routing between multiple networks.
* Allows devices from different manufacturers to communicate.
* Provides reliable and scalable communication.

---

# The Four Layers of the TCP/IP Model

```text
+------------------------------+
| Application Layer            |
+------------------------------+
| Transport Layer              |
+------------------------------+
| Internet Layer               |
+------------------------------+
| Network Access Layer         |
+------------------------------+
```

---

# Layer 4 – Application Layer

The **Application Layer** provides network services directly to end-user applications.

It combines the functions of the **Application**, **Presentation**, and **Session** layers of the OSI Model.

### Responsibilities

* Web browsing
* Email communication
* File transfer
* Name resolution
* Remote access
* Network management

### Common Protocols

* HTTP
* HTTPS
* DNS
* DHCP
* FTP
* SMTP
* POP3
* IMAP
* SSH
* Telnet
* SNMP

### Protocol Data Unit (PDU)

**Data**

### Real-World Example

When you open a web browser and visit **[www.example.com](http://www.example.com)**, the browser generates an HTTP or HTTPS request at the Application Layer.

---

# Layer 3 – Transport Layer

The **Transport Layer** is responsible for end-to-end communication between devices.

It ensures that data reaches the correct application on the destination device.

### Responsibilities

* Segmentation
* Reassembly
* Flow control
* Error detection
* Reliable communication
* Port addressing

### Common Protocols

* TCP
* UDP

### Protocol Data Unit (PDU)

* Segment (TCP)
* Datagram (UDP)

### Address Used

**Port Number**

### Real-World Example

A web browser uses **TCP Port 443** to communicate securely with a web server over HTTPS.

---

# Layer 2 – Internet Layer

The **Internet Layer** is responsible for logical addressing and routing packets between different networks.

It determines the best path for data to travel from the source to the destination.

### Responsibilities

* Logical addressing
* Routing
* Packet forwarding
* Path selection

### Common Protocols

* IPv4
* IPv6
* ICMP
* ARP*
* IGMP

> **Note:** In the TCP/IP model, ARP is often associated with the Internet Layer, although its exact placement can vary depending on the reference.

### Device

* Router

### Protocol Data Unit (PDU)

**Packet**

### Address Used

**IP Address**

### Real-World Example

A router forwards an IP packet from your home network to a web server on the Internet.

---

# Layer 1 – Network Access Layer

The **Network Access Layer** combines the **Physical** and **Data Link** layers of the OSI Model.

It is responsible for transmitting data over the physical network.

### Responsibilities

* Framing
* MAC addressing
* Error detection
* Physical transmission
* Media access

### Common Technologies

* Ethernet
* Wi-Fi (IEEE 802.11)
* PPP
* HDLC

### Devices

* Switch
* Access Point
* Hub
* Network Interface Card (NIC)

### Protocol Data Unit (PDU)

* Frame
* Bits

### Address Used

**MAC Address**

### Real-World Example

A switch forwards an Ethernet frame to the correct device using its MAC address.

---

# TCP/IP Layer Summary

| Layer          | Main Function                | PDU                | Address     |
| -------------- | ---------------------------- | ------------------ | ----------- |
| Application    | User network services        | Data               | —           |
| Transport      | End-to-end communication     | Segment / Datagram | Port Number |
| Internet       | Routing & Logical Addressing | Packet             | IP Address  |
| Network Access | Physical Transmission        | Frame / Bits       | MAC Address |

---

# Encapsulation

Before data is transmitted, each layer adds its own protocol information.

```text
Application Data
        │
        ▼
TCP Header
        │
        ▼
IP Header
        │
        ▼
Ethernet Header
        │
        ▼
Frame
        │
        ▼
Bits
```

Each layer prepares the data for the next layer until it is transmitted over the network.

---

# Decapsulation

When the destination device receives the data, each layer removes the corresponding header.

```text
Bits
 │
 ▼
Frame
 │
 ▼
Packet
 │
 ▼
Segment
 │
 ▼
Application Data
```

The original application data is finally delivered to the receiving application.

---

# Data Flow Example

Suppose a user opens **https://www.example.com**.

1. The browser creates an HTTPS request at the **Application Layer**.
2. The **Transport Layer** adds a TCP header.
3. The **Internet Layer** adds source and destination IP addresses.
4. The **Network Access Layer** adds source and destination MAC addresses and prepares the frame for transmission.
5. The data travels through switches and routers across the Internet.
6. The destination server removes each header in reverse order.
7. The web server processes the request and sends the response back to the client.

---

# TCP/IP Model vs OSI Model

| TCP/IP Model             | OSI Model                             |
| ------------------------ | ------------------------------------- |
| 4 Layers                 | 7 Layers                              |
| Practical implementation | Reference model                       |
| Used on the Internet     | Used for learning and troubleshooting |
| Developed by DoD         | Developed by ISO                      |
| Protocol-based           | Concept-based                         |

### Layer Mapping

| TCP/IP Layer   | Corresponding OSI Layers           |
| -------------- | ---------------------------------- |
| Application    | Application, Presentation, Session |
| Transport      | Transport                          |
| Internet       | Network                            |
| Network Access | Data Link, Physical                |

---

# Advantages of the TCP/IP Model

* Open standard used worldwide.
* Highly scalable.
* Supports communication across different networks.
* Compatible with nearly all operating systems.
* Reliable and widely adopted.
* Forms the foundation of the modern Internet.

---

# Limitations of the TCP/IP Model

* Less detailed than the OSI Model.
* Does not clearly separate presentation and session functions.
* Some protocols do not map perfectly to a single layer.

---

## 🚀 Next Steps

Now that you understand how the TCP/IP Model organizes network communication, the next step is to learn **how data is packaged and prepared for transmission**.

**Next Lab:**
➡️ **05 - Data Encapsulation & Decapsulation**
