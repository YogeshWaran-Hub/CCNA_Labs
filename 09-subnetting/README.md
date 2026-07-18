# 09 - Subnetting

## 📖 Overview

This project covers **Subnetting**, one of the most important topics in the CCNA curriculum. Subnetting is the process of dividing a large network into smaller, manageable networks called **subnets**. It helps improve network efficiency, security, and address utilization.

## 🎯 Objectives

- Understand the concept of subnetting.
- Learn how subnet masks work.
- Calculate network and broadcast addresses.
- Determine valid host ranges.
- Calculate the number of subnets and hosts.
- Practice CIDR notation and VLSM concepts.

---

## 🌐 What is Subnetting?

Subnetting is the process of splitting a network into smaller logical networks.

### Benefits

- Efficient IP address utilization
- Reduced broadcast traffic
- Improved network performance
- Enhanced security
- Easier network management

Example:

```text
Network: 192.168.1.0/24
```

Can be divided into:

```text
192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26
```

---

## 📏 Subnet Mask Basics

A subnet mask separates the network portion from the host portion.

Example:

```text
IP Address : 192.168.1.10
Subnet Mask: 255.255.255.0
CIDR       : /24
```

Binary:

```text
11111111.11111111.11111111.00000000
```

---

## 🔢 CIDR Notation

CIDR (Classless Inter-Domain Routing) indicates the number of network bits.

| CIDR | Subnet Mask |
|--------|-------------|
| /24 | 255.255.255.0 |
| /25 | 255.255.255.128 |
| /26 | 255.255.255.192 |
| /27 | 255.255.255.224 |
| /28 | 255.255.255.240 |
| /29 | 255.255.255.248 |
| /30 | 255.255.255.252 |

---

## 🧮 Subnetting Formula

### Number of Subnets

```text
2^n
```

Where:

```text
n = borrowed bits
```

---

### Number of Hosts

```text
2^h - 2
```

Where:

```text
h = host bits
```

The subtraction of 2 accounts for:

- Network Address
- Broadcast Address

---

## 📚 Example 1

### Network

```text
192.168.1.0/26
```

### Subnet Mask

```text
255.255.255.192
```

### Calculations

```text
Host Bits = 6
Hosts per Subnet = 2^6 - 2
                  = 62 Hosts
```

Subnet Increment:

```text
256 - 192 = 64
```

Subnets:

```text
192.168.1.0
192.168.1.64
192.168.1.128
192.168.1.192
```

---

## 📚 Example 2

### Network

```text
192.168.10.0/27
```

### Subnet Mask

```text
255.255.255.224
```

Increment:

```text
256 - 224 = 32
```

Subnets:

```text
192.168.10.0
192.168.10.32
192.168.10.64
192.168.10.96
192.168.10.128
192.168.10.160
192.168.10.192
192.168.10.224
```

Hosts per subnet:

```text
2^5 - 2 = 30 Hosts
```

---

## 🎯 Finding Subnet Information

Example:

```text
IP Address: 192.168.1.70/26
```

Subnet Range:

```text
192.168.1.64 - 192.168.1.127
```

Results:

```text
Network Address   : 192.168.1.64
First Host        : 192.168.1.65
Last Host         : 192.168.1.126
Broadcast Address : 192.168.1.127
```

---

## 🖥️ Cisco Configuration Example

Assign an IP address to a router interface:

```bash
Router(config)# interface g0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
```

Verify:

```bash
show ip interface brief
```

---

## 🔬 Lab Activity

### Task 1

Subnet:

```text
192.168.1.0/24
```

into

```text
4 subnets
```

Answer:

```text
Borrow 2 bits
New Prefix = /26
```

Subnets:

```text
192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26
```

---

### Task 2

Determine:

```text
IP Address: 10.10.10.50/27
```

Find:

- Network Address
- Broadcast Address
- First Host
- Last Host

Answer:

```text
Network Address   : 10.10.10.32
First Host        : 10.10.10.33
Last Host         : 10.10.10.62
Broadcast Address : 10.10.10.63
```

---

## 🌟 Variable Length Subnet Masking (VLSM)

VLSM allows subnetting based on actual host requirements.

Example:

```text
Department A = 100 Hosts
Department B = 50 Hosts
Department C = 20 Hosts
```

Possible allocation:

```text
A → /25
B → /26
C → /27
```

Benefits:

- Efficient IP utilization
- Less address wastage
- Scalable network design

---

## ✅ Expected Outcome

After completing this project, you should be able to:

- Calculate subnet masks.
- Determine network and broadcast addresses.
- Identify valid host ranges.
- Use CIDR notation effectively.
- Design subnetted networks for different requirements.
- Apply subnetting concepts in Cisco environments.

---

## 📚 Key Concepts

- IPv4 Subnetting
- CIDR
- Subnet Mask
- Network Address
- Broadcast Address
- Host Range
- VLSM
- Address Planning

---

