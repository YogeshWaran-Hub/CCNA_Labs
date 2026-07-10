# 01 - Networking Devices

## Overview
Before diving deeper into protocols and configurations, it's important to 
know the physical/logical devices that make up a network — what each one 
does, and where it fits (OSI layer, LAN vs WAN, etc).

---

## Hub


**What it does:** A basic device that receives data on one port and 
broadcasts it out to **every other port**, regardless of the destination.

- **OSI Layer:** 1 (Physical)
- **Intelligence:** None — doesn't know MAC or IP addresses
- **Use case today:** Rarely used — replaced by switches. Mentioned mainly 
  for exam/historical purposes.
- **Downside:** Causes collisions, wastes bandwidth, no security (everyone sees everything)

---

## Switch

**What it does:** Connects multiple devices within the same LAN. Learns 
MAC addresses of connected devices and forwards frames **only** to the 
correct destination port (instead of broadcasting to everyone like a hub).

- **OSI Layer:** 2 (Data Link)
- **Intelligence:** Builds and uses a MAC address table
- **Use case:** Core of any LAN — connects PCs, printers, APs, servers within 
  the same office/building
- **Types:** Unmanaged (plug-and-play) vs Managed (configurable, supports VLANs, trunking, etc — used in CCNA labs)

---

## Router


**What it does:** Connects **different networks** together (e.g. your LAN to 
the Internet/WAN) and decides the best path for data using IP addresses.

- **OSI Layer:** 3 (Network)
- **Intelligence:** Maintains a routing table, runs routing protocols (OSPF, EIGRP, etc.)
- **Use case:** Connecting your home/office network to your ISP; connecting 
  multiple LANs together; inter-VLAN routing

---

## Access Point (AP)


**What it does:** Provides **wireless connectivity**, allowing Wi-Fi devices 
to join a wired network.

- **OSI Layer:** 1/2
- **Use case:** Extending network access wirelessly in an office/home
- **Note:** Different from a wireless router — an AP alone doesn't route traffic, just bridges wireless clients to the wired LAN

---

## Firewall


**What it does:** Filters incoming/outgoing traffic based on security rules, 
protecting the network from unauthorized access or attacks.

- **OSI Layer:** 3/4 (some modern firewalls inspect up to Layer 7 — "Next-Gen Firewalls")
- **Use case:** Sits at the network edge (between LAN and Internet), enforces ACL-like rules, VPN termination, intrusion prevention

---

## Modem


**What it does:** Converts digital signals from your network into a format 
that can travel over your ISP's medium (cable, DSL, fiber) — and back again.

- **OSI Layer:** 1
- **Use case:** The device that physically connects your home/office to your ISP
- **Note:** Often combined with a router in consumer devices ("modem/router combo")

---

## Server


**What it does:** A powerful computer that provides services/resources to 
other devices on the network (files, websites, email, DNS, DHCP, etc).

- **Use case:** Centralized services — file server, web server, DNS server, DHCP server

---

## Quick Comparison Table

| Device | OSI Layer | Purpose | Intelligence |
|--------|-----------|---------|----------------|
| Hub | 1 | Broadcasts to all ports | None |
| Switch | 2 | Forwards using MAC address | MAC address table |
| Router | 3 | Forwards using IP address, connects networks | Routing table |
| Access Point | 1/2 | Wireless connectivity | Minimal |
| Firewall | 3/4(+) | Security filtering | Rule-based |
| Modem | 1 | ISP signal conversion | None |
| Server | — | Provides network services | Depends on service |

---

## Real-World Example: A Small Office Network

```
Internet
   |
 Modem (ISP connection)
   |
 Router (connects LAN to Internet, assigns IPs via DHCP)
   |
 Firewall (filters traffic)
   |
 Switch (connects all internal devices)
   |
 -----------------------------
 |        |         |        |
PC1     Printer   Server   Access Point --- Wireless Laptop/Phone
```

This is a typical small office setup:
- The **modem** connects to the ISP
- The **router** connects the LAN to the internet and hands out IP addresses
- The **firewall** filters traffic in/out for security
- The **switch** connects all wired devices together
- The **access point** lets wireless devices join the same network

---

## Key Takeaways
- Hubs are outdated, switches replaced them for LAN connectivity
- Switches operate at Layer 2 (MAC), Routers at Layer 3 (IP)
- Firewalls protect the network edge
- Access Points extend wired networks wirelessly
- Real networks combine multiple devices working together, each with a specific job

## Practice Exercise
- Open Packet Tracer and place each device type (hub, switch, router, AP, 
  firewall, modem, server) on the canvas — take a screenshot for your `images/` folder
- Try connecting 2 PCs through a hub vs through a switch, and explain the 
  difference in behavior
- Draw your home network using these device types and label which OSI layer 
  each one operates at

## Next Steps
Now that you know the devices, learn **how data travels through them** → 
[02 - OSI Model](../02-osi-model)
