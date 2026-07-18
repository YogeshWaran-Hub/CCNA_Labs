# 07 - MAC Address and ARP

## 📌 Experiment Title
**Study of MAC Address and Address Resolution Protocol (ARP)**

---

## 📖 Introduction

In computer networks, devices communicate using both **IP addresses** and **MAC addresses**. While IP addresses are used for identifying devices across networks, MAC addresses are used to identify devices within a local network. The **Address Resolution Protocol (ARP)** acts as a bridge between Layer 3 (Network Layer) and Layer 2 (Data Link Layer) by resolving an IP address into its corresponding MAC address.

This experiment demonstrates how to identify MAC addresses, examine ARP tables, and understand the process of ARP requests and replies in a Local Area Network (LAN).

---

## 🎯 Objectives

- To understand the concept of MAC addresses.
- To identify the MAC address of a network interface.
- To study the working of the Address Resolution Protocol (ARP).
- To view and analyze ARP cache entries.
- To observe the relationship between IP addresses and MAC addresses.
- To understand how devices communicate within a LAN.

---

## 🧠 Theory

### What is a MAC Address?

A **MAC (Media Access Control) Address** is a unique hardware address assigned to a network interface card (NIC) by the manufacturer. It is used for communication within a local network.

#### Characteristics of a MAC Address

- Operates at **Layer 2 (Data Link Layer)** of the OSI model.
- Consists of **48 bits (6 bytes)**.
- Represented in hexadecimal format.
- Intended to be unique for every network device.
- Used for local network communication.

#### Example

```text
00:1A:2B:3C:4D:5E
```

The first 24 bits represent the manufacturer identifier (OUI), and the remaining 24 bits identify the specific device.

---

### What is ARP?

**Address Resolution Protocol (ARP)** is used to map an IP address to a MAC address within the same local network.

When a device wants to communicate with another device using an IP address, it first needs the destination MAC address. ARP helps in finding that MAC address.

---

## 🔄 Working of ARP

Consider the following example:

```text
Device A
IP Address  : 192.168.1.10
MAC Address : 00:1A:2B:3C:4D:5E

Device B
IP Address  : 192.168.1.20
MAC Address : AA:BB:CC:DD:EE:FF
```

### Step-by-Step Process

#### Step 1: ARP Cache Check

Device A checks its ARP table to see whether the MAC address of Device B is already stored.

#### Step 2: ARP Request

If the MAC address is not found, Device A sends a broadcast ARP request.

```text
Who has IP 192.168.1.20?
Tell 192.168.1.10
```

#### Step 3: ARP Reply

Device B responds with its MAC address.

```text
192.168.1.20 is at AA:BB:CC:DD:EE:FF
```

#### Step 4: ARP Table Update

Device A stores the mapping in its ARP cache.

```text
192.168.1.20 → AA:BB:CC:DD:EE:FF
```

#### Step 5: Communication

Data frames can now be sent directly to Device B using its MAC address.

---

## 🏗️ OSI Layer Involvement

| Layer | Protocol/Address |
|---------|----------------|
| Application Layer | User Applications |
| Transport Layer | TCP/UDP |
| Network Layer | IP Address |
| Data Link Layer | MAC Address, ARP |
| Physical Layer | Network Medium |

ARP operates between the Network Layer and Data Link Layer.

---

## 🛠️ Requirements

### Hardware

- Computer/Laptop
- Network Interface Card (NIC)

### Software

- Windows/Linux/macOS
- Command Prompt or Terminal
- Wireshark (Optional)

---

## 📂 Commands Used

### Display MAC Address

#### Windows

```bash
ipconfig /all
```

#### Linux

```bash
ifconfig
```

or

```bash
ip link show
```

#### macOS

```bash
ifconfig
```

---

### Display ARP Table

#### Windows

```bash
arp -a
```

#### Linux

```bash
arp -n
```

or

```bash
ip neigh
```

#### macOS

```bash
arp -a
```

---

### Test Network Connectivity

```bash
ping <IP_Address>
```

Example:

```bash
ping 192.168.1.1
```

---

## 🧪 Procedure

### Part A – Finding MAC Address

1. Open Command Prompt or Terminal.
2. Execute the appropriate command:
   ```bash
   ipconfig /all
   ```
   or
   ```bash
   ifconfig
   ```
3. Locate the Physical Address (MAC Address).
4. Record the MAC address.

### Sample Output

```text
Ethernet Adapter

Physical Address : 00-1A-2B-3C-4D-5E
```

---

### Part B – Viewing ARP Cache

1. Open Command Prompt or Terminal.
2. Execute:

```bash
arp -a
```

3. Observe existing ARP entries.

### Sample Output

```text
Internet Address      Physical Address      Type
192.168.1.1           aa-bb-cc-dd-ee-ff     dynamic
192.168.1.20          11-22-33-44-55-66     dynamic
```

---

### Part C – Generating ARP Entries

1. Ping another device in the network.

```bash
ping 192.168.1.20
```

2. Execute:

```bash
arp -a
```

3. Observe the newly added entry in the ARP table.

---

## 📊 Sample ARP Table Analysis

| IP Address | MAC Address | Type |
|------------|------------|--------|
| 192.168.1.1 | AA-BB-CC-DD-EE-FF | Dynamic |
| 192.168.1.20 | 11-22-33-44-55-66 | Dynamic |
| 192.168.1.50 | 22-33-44-55-66-77 | Static |

### Types of Entries

#### Dynamic Entry

- Automatically created through ARP.
- Removed after a timeout period.

#### Static Entry

- Manually configured.
- Remains until deleted.

---

## 📈 ARP Request and Reply Flow Diagram

```text
+------------+                          +------------+
|  Device A  |                          |  Device B  |
|192.168.1.10|                          |192.168.1.20|
+------------+                          +------------+
       |                                       |
       | ARP Request (Broadcast)               |
       |-------------------------------------->|
       | Who has 192.168.1.20 ?                |
       |                                       |
       |<--------------------------------------|
       | ARP Reply                             |
       | MAC = AA:BB:CC:DD:EE:FF               |
       |                                       |
       |---- Data Communication Begins ------->|
```

---

## ✅ Observations

- Every network interface has a unique MAC address.
- ARP resolves IP addresses into MAC addresses.
- ARP requests are broadcast messages.
- ARP replies are unicast messages.
- ARP cache stores recently resolved IP-MAC mappings.
- Communication in a LAN depends on MAC addresses.

---

## 📋 Result

The MAC address of the system was successfully identified. The ARP table was examined, and the mapping between IP addresses and MAC addresses was observed. The functioning of the Address Resolution Protocol (ARP) and its role in local network communication were successfully studied and understood.

---

# 🚀 Next Step

Now that you understand **MAC Addressing** and the **Address Resolution Protocol (ARP)**, you know how devices on a Local Area Network (LAN) identify each other and resolve IP addresses into MAC addresses for successful frame delivery.

In the next lab, you'll explore **IPv4 Addressing**. You'll learn how IPv4 addresses are structured, how subnet masks define networks and hosts, and how devices use IP addressing to communicate within and across networks.

**➡️ Next Lab:**
[**08 - IPv4 Addressing**](../08-IPv4-addresing/README.md)


