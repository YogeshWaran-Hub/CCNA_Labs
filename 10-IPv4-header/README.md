# 10 - IPv4 Header

## 📖 Overview

This project explores the **IPv4 Header**, a critical component of the Internet Protocol (IP). Every IPv4 packet contains a header that carries essential information required for routing, delivery, fragmentation, and error handling across networks.

Understanding the IPv4 header is an important CCNA topic because routers examine header fields to determine how packets should be forwarded.

---

## 🎯 Objectives

- Understand the structure of an IPv4 packet.
- Identify the fields in an IPv4 header.
- Learn the purpose of each header field.
- Analyze IPv4 packets using Wireshark.
- Understand packet forwarding and fragmentation.

---

## 🌐 What is an IPv4 Header?

An IPv4 header contains control information that helps network devices deliver packets from a source to a destination.

### IPv4 Packet Structure

```text
+------------------+
|   IPv4 Header    |
+------------------+
|      Data        |
+------------------+
```

The header size ranges from:

```text
20 Bytes (Minimum)
60 Bytes (Maximum)
```

---

## 🏗️ IPv4 Header Format

```text
0                   15                  31
+----+----+------------------------------+
|Ver |IHL | Type of Service              |
+----+----+------------------------------+
| Total Length                           |
+----------------------------------------+
| Identification                         |
+----------------------------------------+
| Flags | Fragment Offset                |
+----------------------------------------+
| TTL   | Protocol | Header Checksum     |
+----------------------------------------+
| Source IP Address                      |
+----------------------------------------+
| Destination IP Address                 |
+----------------------------------------+
| Options (Optional)                     |
+----------------------------------------+
```

---

## 📌 Header Fields

### 1. Version

Indicates the IP version being used.

For IPv4:

```text
Version = 4
```

Field Size:

```text
4 bits
```

---

### 2. Internet Header Length (IHL)

Specifies the length of the IPv4 header.

Minimum:

```text
20 Bytes
```

Maximum:

```text
60 Bytes
```

Field Size:

```text
4 bits
```

---

### 3. Type of Service (ToS)

Used to specify packet priority and quality of service.

Modern networks use:

```text
DSCP (Differentiated Services Code Point)
```

Field Size:

```text
8 bits
```

---

### 4. Total Length

Defines the entire packet size including:

- Header
- Payload

Field Size:

```text
16 bits
```

Maximum Size:

```text
65,535 Bytes
```

---

### 5. Identification

Used to uniquely identify fragmented packets.

Field Size:

```text
16 bits
```

Purpose:

```text
Helps reassemble fragments at the destination.
```

---

### 6. Flags

Controls packet fragmentation.

Field Size:

```text
3 bits
```

Flags:

```text
Bit 0 = Reserved
Bit 1 = DF (Don't Fragment)
Bit 2 = MF (More Fragments)
```

Example:

```text
DF = 1
Packet cannot be fragmented.
```

---

### 7. Fragment Offset

Indicates the position of a fragment in the original packet.

Field Size:

```text
13 bits
```

Used during packet reassembly.

---

### 8. Time To Live (TTL)

Prevents packets from looping indefinitely.

Field Size:

```text
8 bits
```

Example:

```text
TTL = 64
```

Each router:

```text
Decrements TTL by 1
```

When TTL reaches:

```text
0
```

the packet is discarded.

---

### 9. Protocol

Identifies the upper-layer protocol.

Field Size:

```text
8 bits
```

Common Values:

```text
1  = ICMP
6  = TCP
17 = UDP
89 = OSPF
```

---

### 10. Header Checksum

Used to detect errors in the IPv4 header.

Field Size:

```text
16 bits
```

Routers recalculate the checksum after modifying the TTL value.

---

### 11. Source IP Address

Identifies the sender's IPv4 address.

Example:

```text
192.168.1.10
```

Field Size:

```text
32 bits
```

---

### 12. Destination IP Address

Identifies the receiver's IPv4 address.

Example:

```text
8.8.8.8
```

Field Size:

```text
32 bits
```

---

### 13. Options

Optional field used for additional networking features.

Examples:

- Security
- Timestamp
- Record Route

Field Size:

```text
0–40 Bytes
```

Rarely used in modern networks.

---

## 🔬 Packet Example

Source:

```text
192.168.1.100
```

Destination:

```text
8.8.8.8
```

Protocol:

```text
ICMP
```

TTL:

```text
64
```

Packet Flow:

```text
Host → Router → ISP → Internet → Destination
```

Each router decreases TTL until the packet reaches its destination.

---
Observe:

- Version
- Header Length
- TTL
- Protocol
- Source IP
- Destination IP

---

## 📚 Fragmentation Example

Suppose:

```text
Packet Size = 3000 Bytes
```

Network MTU:

```text
1500 Bytes
```

Result:

```text
Packet is fragmented
```

Fragments:

```text
Fragment 1
Fragment 2
Fragment 3
```

Identification and Fragment Offset fields help rebuild the packet at the destination.

---

## 🖥️ Cisco Verification Commands

Display routing information:

```bash
show ip route
```

View interface information:

```bash
show ip interface brief
```

Check packet forwarding:

```bash
traceroute 8.8.8.8
```

---

## ✅ Expected Outcome

After completing this project, you should be able to:

- Identify all IPv4 header fields.
- Explain the purpose of each field.
- Understand packet forwarding.
- Analyze IPv4 packets using Wireshark.
- Understand fragmentation and reassembly.
- Recognize how routers process IPv4 headers.

---

## 📚 Key Concepts

- IPv4 Packet
- IPv4 Header
- TTL
- Checksum
- Protocol Field
- Fragmentation
- Fragment Offset
- Source IP
- Destination IP
- MTU

---
