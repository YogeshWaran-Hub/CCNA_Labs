# 05 - Data Encapsulation & Decapsulation

> Learn how data is prepared, transmitted, and received across a network using the processes of encapsulation and decapsulation.

---

# What is Encapsulation?

- Definition of encapsulation
- Why encapsulation is required
- How encapsulation works
- Why every network uses encapsulation
- Real-world analogy (Sending a Letter)

---

# Why Encapsulation is Needed

Explain why networks cannot communicate without encapsulation.

Include:

- Logical Addressing
- Physical Addressing
- End-to-End Communication
- Routing
- Error Detection
- Data Identification
- Multiplexing using Port Numbers
- Standardized Communication
- Interoperability

---

# Network Communication Before Encapsulation

Explain what happens before encapsulation starts.

Example:

```
User Opens Website
        │
        ▼
Browser Creates HTTP Request
        │
        ▼
Application Generates Data
        │
        ▼
Encapsulation Begins
```

Explain:

- User request
- Application generates data
- Data passed to lower layers

---

# What is Decapsulation?

- Definition
- Why decapsulation is required
- How the receiver removes protocol information
- Difference between encapsulation and decapsulation

---

# How Data Travels Through the OSI Model

Explain every layer.

## Layer 7 – Application

- Function
- What happens here

## Layer 6 – Presentation

- Translation
- Encryption
- Compression

## Layer 5 – Session

- Session establishment
- Session maintenance
- Session termination

## Layer 4 – Transport

- TCP Header
- UDP Header
- Segmentation
- Port Numbers

## Layer 3 – Network

- IP Header
- Routing
- Logical Addressing

## Layer 2 – Data Link

- Ethernet Header
- MAC Address
- FCS Trailer
- Framing

## Layer 1 – Physical

- Converts Frame into Bits
- Electrical Signals
- Optical Signals
- Wireless Signals

---

# How Data Travels Through the TCP/IP Model

Explain every layer.

## Application Layer

Responsibilities

Protocols

---

## Transport Layer

TCP

UDP

Port Numbers

---

## Internet Layer

IP

ICMP

ARP

Routing

---

## Network Access Layer

Ethernet

Wi-Fi

MAC Address

Frame Transmission

---

# Protocol Data Units (PDUs)

Explain every PDU individually.

## Data

What is Data?

---

## Segment

Why TCP creates Segments

---

## Datagram

Why UDP creates Datagrams

---

## Packet

What is an IP Packet?

---

## Frame

What is an Ethernet Frame?

---

## Bits

Binary transmission

Electrical signals

---

# Headers and Trailers

## What is a Header?

Purpose

Common Information

- Source Address
- Destination Address
- Sequence Number
- Port Number
- Protocol

---

## Types of Headers

### TCP Header

Explain every important field.

### UDP Header

Explain fields.

### IP Header

Explain fields.

### Ethernet Header

Explain fields.

---

## What is a Trailer?

Explain:

Frame Check Sequence (FCS)

CRC

Error Detection

---

# Step-by-Step Encapsulation Process

Step 1

Application creates Data

↓

Step 2

Transport Layer adds TCP Header

↓

Step 3

Network Layer adds IP Header

↓

Step 4

Data Link Layer adds Ethernet Header and Trailer

↓

Step 5

Physical Layer converts everything into Bits

---

# Step-by-Step Decapsulation Process

Bits Received

↓

Frame Created

↓

Ethernet Header Removed

↓

IP Header Removed

↓

TCP Header Removed

↓

Original Data Delivered

---

# Encapsulation Diagram

```
Application Data
        │
        ▼
+-----------------------+
| TCP Header            |
+-----------------------+
| Application Data      |
+-----------------------+
        │
        ▼
+-----------------------+
| IP Header             |
+-----------------------+
| TCP Header            |
+-----------------------+
| Application Data      |
+-----------------------+
        │
        ▼
+-----------------------+
| Ethernet Header       |
+-----------------------+
| IP Header             |
+-----------------------+
| TCP Header            |
+-----------------------+
| Application Data      |
+-----------------------+
| FCS Trailer           |
+-----------------------+
        │
        ▼
Bits
```

---

# Packet Journey

```
PC
 │
 ▼
Switch
 │
 ▼
Router
 │
 ▼
ISP Router
 │
 ▼
Internet
 │
 ▼
Destination Router
 │
 ▼
Switch
 │
 ▼
Server
```

Explain what each device does.

- PC
- Switch
- Router
- ISP
- Internet
- Destination Router
- Server

---

# What Changes During Transmission?

| Information | Changes? | Reason |
|------------|----------|--------|
| Source MAC | ✅ Yes | New Frame for every hop |
| Destination MAC | ✅ Yes | Next-Hop Device |
| Source IP | ❌ No | Original Sender |
| Destination IP | ❌ No | Final Destination |
| TCP Port | ❌ No | Same Application |
| HTTP Data | ❌ No | Original Payload |

Explain why MAC addresses change while IP addresses usually remain the same.

---

# Real-World Example

Opening a Website

```
User
 │
 ▼
Browser
 │
 ▼
Application Layer
 │
 ▼
Transport Layer
 │
 ▼
Internet Layer
 │
 ▼
Network Access Layer
 │
 ▼
Switch
 │
 ▼
Router
 │
 ▼
Internet
 │
 ▼
Web Server
```

Explain every stage.

---

# Encapsulation vs Decapsulation

| Encapsulation | Decapsulation |
|---------------|---------------|
| Sender | Receiver |
| Adds Headers | Removes Headers |
| Creates Frames | Removes Frames |
| Data → Bits | Bits → Data |

---

# Common Mistakes

- Switch forwards **Frames**, not Packets.
- Router forwards **Packets**, not Frames.
- MAC addresses are used within a Local Area Network (LAN).
- IP addresses identify devices across networks.
- Only the Data Link Layer adds a trailer.
- Every router creates a new Layer 2 frame for the next hop.

---

# 🚀 Next Step

Now that you understand **Data Encapsulation and Decapsulation** and how data is packaged and unpackaged as it travels through the network layers, it's time to explore the **Ethernet Frame Structure**.

In the next lab, you'll learn how Ethernet frames are constructed, the purpose of each field, how MAC addresses are used for local communication, and how Ethernet ensures reliable data transmission within a Local Area Network (LAN).

**➡️ Next Lab:**  
[**06 - Ethernet Frame Structure**](../06-Ethernet-Frame-Structure/README.md)
