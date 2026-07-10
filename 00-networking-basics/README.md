# 00 - Networking Basics

## What is a Network?

A **network** is simply two or more devices connected together so they can 
share information and resources. That's it at its core — computers, phones, 
printers, servers, all "talking" to each other.

Examples of things a network lets you do:
- Send an email
- Browse a website
- Print a document from your laptop to a shared printer
- Stream a video
- Video call someone on the other side of the world

## Why Do Networks Exist?

- **Resource sharing** — one printer can serve an entire office
- **Communication** — email, chat, video calls
- **Data sharing** — shared drives, cloud storage
- **Centralized management** — servers manage data, security, backups

## Basic Networking Terms

| Term | Meaning |
|------|---------|
| **Node** | Any device connected to a network (PC, phone, printer, server, router) |
| **Host** | A device that sends/receives data (usually an end-user device) |
| **Link** | The physical or wireless connection between two nodes |
| **Bandwidth** | The maximum amount of data that can be transferred per second |
| **Packet** | A small unit of data sent across a network |
| **Protocol** | A set of rules devices follow to communicate (e.g., HTTP, TCP) |
| **IP Address** | A unique logical address identifying a device on a network |
| **MAC Address** | A unique physical/hardware address burned into a network card |

## Types of Networks (by Size)

| Type | Full Name | Coverage Area | Example |
|------|-----------|----------------|---------|
| **PAN** | Personal Area Network | A few meters | Bluetooth between phone and headphones |
| **LAN** | Local Area Network | A single building/office | Home Wi-Fi, office network |
| **MAN** | Metropolitan Area Network | A city | City-wide ISP network |
| **WAN** | Wide Area Network | Countries/continents | The Internet |

## Network Topologies (How Devices Are Physically/Logically Arranged)

- **Bus** — all devices share a single cable (old, rarely used now)
- **Star** — all devices connect to a central switch/hub (most common today)
- **Ring** — devices connected in a circular fashion (legacy, e.g. Token Ring)
- **Mesh** — every device connects to every other device (very redundant, used in critical networks)
- **Hybrid** — a mix of the above (common in real-world enterprise networks)

*(Star topology is what you'll build in almost every Packet Tracer lab.)*

## Basic Network Devices

| Device | Function | OSI Layer |
|--------|----------|-----------|
| **Hub** | Broadcasts data to all ports (dumb device, outdated) | Layer 1 |
| **Switch** | Forwards data intelligently using MAC addresses | Layer 2 |
| **Router** | Connects different networks, forwards data using IP addresses | Layer 3 |
| **Firewall** | Filters traffic for security | Layer 3/4 (sometimes higher) |
| **Access Point (AP)** | Provides wireless connectivity | Layer 1/2 |

## LAN vs WAN (Important Distinction)

- **LAN** — your home or office network (private, usually fast, no ISP involved directly)
- **WAN** — connects LANs together over long distances (e.g. the Internet connects millions of LANs worldwide)

**Simple way to think of it:**
> Your home network = LAN.  
> Your home network connecting to the Internet through your ISP = WAN.

## IP Address vs MAC Address (Quick Preview)

| | IP Address | MAC Address |
|---|------------|--------------|
| **Type** | Logical | Physical |
| **Assigned by** | Software/DHCP/manually | Manufacturer (burned-in) |
| **Can change?** | Yes | No (normally) |
| **Used for** | Routing between networks | Communication within same network |
| **Example** | 192.168.1.10 | 00:1A:2B:3C:4D:5E |

*(We'll go deeper into both of these in later topics.)*

## Client-Server vs Peer-to-Peer

- **Client-Server** — dedicated servers provide services (files, email, web pages) 
  to client devices. Most business networks work this way.
- **Peer-to-Peer (P2P)** — devices share resources directly with each other, no 
  central server (e.g. small home networks, torrenting).

## Key Takeaways
- A network = devices connected to share data/resources
- Networks are categorized by size (PAN, LAN, MAN, WAN)
- Switches operate at Layer 2, Routers at Layer 3
- IP addresses are logical, MAC addresses are physical
- Most real-world networks use Star topology + Client-Server model

## Practice Exercise
- Identify what type of network you have at home (LAN)
- List every device connected to your home network and guess what "node type" 
  it is (host, AP, router, etc.)
- Try to find your PC's IP address and MAC address (Windows: `ipconfig /all`, 
  Mac/Linux: `ifconfig` or `ip a`)

## Next Steps
Now that you understand what a network is, move to the OSI Model to learn 
**how** data actually travels across that network → [01 - OSI Model](../01-osi-model)
