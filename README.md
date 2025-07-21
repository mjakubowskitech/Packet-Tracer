# Cisco Packet Tracer Project – Multi-VLAN Small Office Network

Welcome to my Cisco Packet Tracer project! This project demonstrates the design and configuration of a **multi-VLAN small office network** with inter-VLAN routing, DHCP, and ACL-based security using Router-on-a-Stick.



##  Overview

This project simulates a small office environment with:

- Segregated VLANs for Sales, HR, and Servers
- Inter-VLAN routing via a single router
- Dynamic IP addressing using DHCP
- ACLs to enforce department-level security
- A multi-role server with web and file services

---

## Network Topology

Below is the network topology designed in Cisco Packet Tracer:

<img width="1827" height="1434" alt="obraz" src="https://github.com/user-attachments/assets/2404b8ee-5144-4557-9829-371a94fbb9e7" />


---

## Requirements

- 1 × Cisco Router (2811 or 2901)
- 1 × Cisco Switch (2960 or 3560)
- 8 × PCs (4 Sales, 4 HR)
- 1 × Multi-role Server
- Straight-through and cross-over cables

---

## IP Addressing Table

| VLAN Name   | VLAN ID | Subnet              | Example Devices                 |
|-------------|---------|---------------------|---------------------------------|
| Sales       | 10      | 192.168.10.0/24     | PCs: 192.168.10.11–.14         |
| HR          | 20      | 192.168.20.0/24     | PCs: 192.168.20.11–.14         |
| Servers     | 30      | 192.168.30.0/24     | Server: 192.168.30.10          |
| Management  | 99      | 192.168.99.0/24     | Reserved for management use    |

---

## Design Summary

- **Router-on-a-Stick** is used for inter-VLAN routing with sub-interfaces for each VLAN.
- **Switch** is configured with multiple VLANs and a trunk port to the router.
- **DHCP** is served by the router with separate pools for each VLAN.
- **Server** in VLAN 30 acts as a multi-role server providing HTTP/HTTPS and FTP services.
- **ACLs** control inter-VLAN communication to enforce departmental security policies.

---

## Access Control Lists (ACLs)

- Sales VLAN (10) can only access the Servers VLAN (30) for:
  - HTTP (port 80)
  - HTTPS (port 443)
  - FTP (port 21)
  - Blocked from accessing HR VLAN (20)

- HR VLAN (20) can only access Servers VLAN (30) for:
  - HTTP (port 80)
  - HTTPS (port 443)
  - Blocked from accessing Sales VLAN (10)

---

## Server Configuration

- Static IP: 192.168.30.10
- Services enabled:
- HTTP / HTTPS (Web Server)
- FTP / TFTP (File Server)
- DNS (optional)
- Default Gateway: 192.168.30.1


## Conclusion

This project demonstrates:

- VLAN segmentation for department isolation
- Router-on-a-Stick for inter-VLAN routing
- DHCP configuration on router for dynamic addressing
- ACL-based security between departments
- Integration of a multi-role server
---

## ✨ Author

Michał Jakubowski 
www.linkedin.com/in/michał-jakubowski-430465217
