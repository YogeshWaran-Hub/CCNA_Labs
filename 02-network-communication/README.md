#  Lab 02 – Network Communication
---

# 📖 Overview

Network communication is the process of exchanging data between two or more devices using wired or wireless media. Every network operation, from opening a website to sending an email, relies on devices communicating using standard networking protocols.

This lab introduces the fundamental concepts of network communication that form the foundation of the CCNA 200-301 certification.

---

# 🎯 Learning Objectives

After completing this lab, you will be able to:

- Explain network communication.
- Identify the components involved in communication.
- Differentiate between Simplex, Half-Duplex, and Full-Duplex communication.
- Explain Unicast, Broadcast, Multicast, and Anycast communication.
- Compare different transmission media.
- Understand Encapsulation and Decapsulation.

---

# 📑 Table of Contents

1. Introduction to Network Communication
2. Communication Components
3. Communication Modes
4. Types of Network Communication
5. Transmission Media
6. Encapsulation & Decapsulation

---

# 1️⃣ Introduction to Network Communication

## What is Network Communication?

Network communication is the process of transmitting data between two or more devices connected through a network.

The communication can occur over:

- Wired networks
- Wireless networks
- Local Area Networks (LAN)
- Wide Area Networks (WAN)
- The Internet

Communication follows a set of predefined rules called **Protocols**.

### Example

```
Laptop
   │
Switch
   │
Router
   │
Internet
   │
Web Server
```

When you visit a website:

1. Your browser sends a request.
2. The request travels through your network.
3. The server processes the request.
4. The server sends a response.
5. The webpage is displayed.

---

## Why is Network Communication Important?

Network communication enables:

- Web browsing
- Email
- Video conferencing
- Online gaming
- Cloud computing
- File sharing
- Remote access
- Voice over IP (VoIP)

Without network communication, devices cannot exchange information.

---

# 2️⃣ Communication Components

Every communication consists of five essential components.

## Sender (Source)

The sender is the device that creates and sends data.

Examples

- PC
- Laptop
- Smartphone
- Server

```
PC ---->
```

---

## Receiver (Destination)

The receiver is the device that receives the data.

Examples

- Computer
- Server
- Printer
- Mobile Device

```
------> PC
```

---

## Message

The message is the information being transmitted.

Examples

- Email
- Image
- Video
- Voice
- Text Document

---

## Transmission Medium

The transmission medium carries the data between devices.

Examples

- Ethernet Cable
- Fiber Cable
- Wi-Fi
- Bluetooth

```
PC -------- Cable -------- Switch
```

---

## Protocol

Protocols define the rules of communication.

Common protocols include:

| Protocol | Purpose |
|----------|----------|
| IP | Logical Addressing |
| TCP | Reliable Communication |
| UDP | Fast Communication |
| ICMP | Error Reporting & Ping |
| ARP | MAC Address Resolution |

---

# 3️⃣ Communication Modes

Communication mode defines how data flows between devices.

There are three communication modes.

---

## Simplex Communication

Simplex communication allows data to travel in **one direction only**.

```
Sender -----------> Receiver
```

### Characteristics

- One-way communication
- No response
- Simple implementation

### Examples

- Keyboard → Computer
- Television Broadcast
- Radio Broadcast

### Advantages

- Low cost
- Simple design

### Disadvantages

- No acknowledgment
- Cannot send data back

---

## Half-Duplex Communication

Data travels in both directions but **only one device transmits at a time**.

```
PC A <---------> PC B

(One device speaks at a time)
```

### Examples

- Walkie-Talkie
- Police Radio
- Old Ethernet Hub Networks

### Advantages

- Two-way communication
- Lower cost

### Disadvantages

- Waiting time
- Lower performance

---

## Full-Duplex Communication

Both devices transmit and receive data simultaneously.

```
PC A ==========> PC B

PC A <========== PC B
```

### Examples

- Telephone
- Mobile Phone
- Modern Ethernet
- Video Calls

### Advantages

- High speed
- Better performance
- No collisions

### Disadvantages

- More complex hardware

---

## Comparison

| Feature | Simplex | Half-Duplex | Full-Duplex |
|----------|----------|-------------|-------------|
| Data Direction | One Way | Two Way | Two Way |
| Simultaneous | No | No | Yes |
| Performance | Low | Medium | High |
| Example | Keyboard | Walkie-Talkie | Telephone |

---

# 4️⃣ Types of Network Communication

---

## Unicast

One sender communicates with one receiver.

```
PC1 --------> PC2
```

Examples

- SSH
- FTP
- Web Browsing

---

## Broadcast

One sender sends data to every device in the network.

```
         PC2
          ▲
          │
PC1 ---> Switch
          │
          ▼
         PC3
          │
          ▼
         PC4
```

Examples

- ARP Request
- DHCP Discover

---

## Multicast

One sender sends data to a selected group of receivers.

```
Server
   │
Router
 ├──── PC2
 └──── PC3
```

Examples

- IPTV
- Live Streaming
- Online Classes

---

## Anycast

Multiple servers share the same IP address.

The nearest server responds.

```
        Server A

Client ---------> Closest Server

        Server B

        Server C
```

Examples

- DNS Servers
- CDN Networks

---

## Comparison

| Type | Sender | Receiver |
|------|----------|-----------|
| Unicast | One | One |
| Broadcast | One | All |
| Multicast | One | Group |
| Anycast | One | Nearest |

---

# 5️⃣ Transmission Media

Transmission media carry data from one device to another.

---

## Guided Media (Wired)

### UTP (Unshielded Twisted Pair)

Most common Ethernet cable.

Examples

- Cat5e
- Cat6
- Cat6A

Maximum Distance

100 meters

Advantages

- Low cost
- Easy installation

---

### STP (Shielded Twisted Pair)

Provides shielding against interference.

Used in

- Hospitals
- Factories
- Data Centers

Advantages

- Better noise protection

---

### Coaxial Cable

Contains a copper conductor surrounded by insulation.

Uses

- Cable Television
- Broadband Internet

Advantages

- Better shielding
- Longer distance than UTP

---

### Fiber Optic Cable

Uses light instead of electrical signals.

Types

- Single Mode Fiber (SMF)
- Multi Mode Fiber (MMF)

Advantages

- Extremely high speed
- Long distance
- Immune to electromagnetic interference

Uses

- ISP Networks
- Enterprise Backbone
- Data Centers

---

## Unguided Media (Wireless)

Examples

- Wi-Fi
- Bluetooth
- Infrared
- Microwave
- Satellite

Advantages

- Mobility
- Easy deployment

Disadvantages

- Interference
- Lower security
- Signal loss

---

## Comparison

| Media | Speed | Distance | Cost |
|---------|---------|----------|------|
| UTP | High | 100 m | Low |
| STP | High | 100 m | Medium |
| Coaxial | Medium | Long | Medium |
| Fiber | Very High | Very Long | High |
| Wireless | Variable | Variable | Medium |

---

# 6️⃣ Encapsulation & Decapsulation

## Encapsulation

Encapsulation is the process of adding protocol information (headers and, in some cases, trailers) to data as it moves down the network stack before transmission.

```
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

Each protocol layer adds information that helps deliver the data correctly.

---

## Decapsulation

Decapsulation is the reverse process.

The receiving device removes the headers layer by layer until the original data reaches the application.

```
Bits
 │
 ▼
Ethernet
 │
 ▼
IP
 │
 ▼
TCP
 │
 ▼
Application Data
```

---

## Real-World Example

A user opens **www.example.com**.

1. The browser creates an HTTP request.
2. TCP adds a TCP header.
3. IP adds source and destination IP addresses.
4. Ethernet adds source and destination MAC addresses.
5. The frame is transmitted across the network.
6. The destination host removes each header.
7. The web server processes the request.
8. The response is sent back to the client.

---
