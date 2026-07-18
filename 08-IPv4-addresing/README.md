# 08 - IPv4 Addressing

## 📖 Overview

This project focuses on **IPv4 (Internet Protocol Version 4) Addressing**, a fundamental concept in computer networking. IPv4 provides logical addressing for devices connected to a network, enabling communication between hosts across local and wide-area networks.

## 🎯 Objectives

- Understand the structure of an IPv4 address.
- Identify network and host portions of an IP address.
- Learn different IPv4 address classes.
- Understand public and private IP addresses.
- Explore special-purpose IPv4 addresses.
- Practice basic IP configuration and verification.

---

## 🌐 What is IPv4?

IPv4 (Internet Protocol Version 4) is a 32-bit logical addressing scheme used to identify devices on a network.

### Example IPv4 Address

```text
192.168.1.10
```

### Binary Representation

```text
11000000.10101000.00000001.00001010
```

Since IPv4 uses 32 bits, it can support approximately:

```text
2^32 = 4,294,967,296 addresses
```

---

## 🏗️ IPv4 Address Structure

An IPv4 address consists of:

```text
Network Portion + Host Portion
```

Example:

```text
192.168.1.10/24
```

```text
Network ID : 192.168.1.0
Host ID    : 0.0.0.10
```

---

## 📊 IPv4 Address Classes

### Class A

```text
Range: 1.0.0.0 – 126.255.255.255
Default Mask: 255.0.0.0 (/8)
```

Example:

```text
10.0.0.1
```

---

### Class B

```text
Range: 128.0.0.0 – 191.255.255.255
Default Mask: 255.255.0.0 (/16)
```

Example:

```text
172.16.0.1
```

---

### Class C

```text
Range: 192.0.0.0 – 223.255.255.255
Default Mask: 255.255.255.0 (/24)
```

Example:

```text
192.168.1.1
```

---

### Class D

```text
Range: 224.0.0.0 – 239.255.255.255
Purpose: Multicast
```

---

### Class E

```text
Range: 240.0.0.0 – 255.255.255.255
Purpose: Experimental
```

---

## 🔒 Private IPv4 Address Ranges

Private addresses are used within local networks and are not routable on the Internet.

| Range | CIDR |
|---------|---------|
| 10.0.0.0 – 10.255.255.255 | /8 |
| 172.16.0.0 – 172.31.255.255 | /12 |
| 192.168.0.0 – 192.168.255.255 | /16 |

### Example

```text
192.168.1.100
```

---

## 🌍 Public IPv4 Addresses

Public IP addresses are globally unique and assigned by Internet Service Providers (ISPs).

Example:

```text
8.8.8.8
```

---

## ⭐ Special IPv4 Addresses

### Loopback Address

```text
127.0.0.1
```

Used to test the local TCP/IP stack.

---

### Broadcast Address

```text
255.255.255.255
```

Used to send data to all devices on a network.

---

### Unspecified Address

```text
0.0.0.0
```

Represents an unknown or unavailable address.

---

## 📏 Subnet Mask

A subnet mask determines which part of an IP address belongs to the network and which part belongs to the host.

Example:

```text
IP Address : 192.168.1.10
Subnet Mask: 255.255.255.0
```

CIDR Notation:

```text
192.168.1.10/24
```

---

## 🖥️ Checking IP Configuration

### Windows

```bash
ipconfig
```

Detailed Information:

```bash
ipconfig /all
```

---

### Linux

```bash
ip addr show
```

or

```bash
ifconfig
```

---

### Cisco IOS

Display interface IP information:

```bash
show ip interface brief
```

---

## 🔬 Lab Activity

### Step 1: View Current IP Configuration

Use:

```bash
ipconfig
```

or

```bash
ip addr show
```

---

### Step 2: Identify

- IPv4 Address
- Subnet Mask
- Default Gateway

Example:

```text
IPv4 Address : 192.168.1.100
Subnet Mask  : 255.255.255.0
Gateway      : 192.168.1.1
```

---

### Step 3: Verify Connectivity

```bash
ping 8.8.8.8
```

Expected Result:

```text
Reply from 8.8.8.8
```

---

### Step 4: Display Routing Information

Windows:

```bash
route print
```

Linux:

```bash
ip route
```

---

## ✅ Expected Outcome

- Understand IPv4 address structure.
- Differentiate between public and private IP addresses.
- Identify network and host portions of an address.
- Interpret subnet masks and CIDR notation.
- Verify IP settings on a host device.

---

## 📚 Key Concepts

- IPv4
- Network ID
- Host ID
- Subnet Mask
- CIDR
- Public IP
- Private IP
- Loopback Address
- Broadcast Address
- Default Gateway

---
