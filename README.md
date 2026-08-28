# Lesika-Surveying-Engineering-Computer-Network
Enterprise network design and implementation project for Lesika Surveying &amp; Engineering, developed in Cisco Packet Tracer with VLAN segmentation, VLSM addressing, Inter-VLAN routing, guest network isolation, and comprehensive network documentation.

# CMPG 325 — Computer Networks
## Enterprise Network Design & Implementation

![Project Status](https://img.shields.io/badge/Status-Milestone%201-blue)
![Cisco Packet Tracer](https://img.shields.io/badge/Tool-Cisco%20Packet%20Tracer-blue)
![Networking](https://img.shields.io/badge/Module-CMPG%20325-green)

---

## Project Overview

This repository contains the design, implementation, testing, troubleshooting, and documentation of an enterprise computer network developed for **Lesika Surveying & Engineering (Lichtenburg)** as part of the CMPG 325 Computer Networks project.

The project focuses on developing a scalable, secure, and maintainable network infrastructure that addresses the client's current networking requirements while allowing for future expansion.

The network design incorporates:

- VLAN segmentation
- VLSM-based IP addressing
- Inter-VLAN Routing
- Layer 3 switching
- Guest Wi-Fi isolation
- Server network segmentation
- Network infrastructure management
- Future network expansion
- Network testing and troubleshooting
- Technical documentation

---

## Client Information

| Item | Details |
|---|---|
| Client | Lesika Surveying & Engineering |
| Location | Lichtenburg |
| Industry | Engineering |
| Project | Enterprise Network Design & Implementation |
| Module | CMPG 325 — Computer Networks |
| Project ID | CMPG325-2026-069 |
| Assigned Network | 10.29.0.0/16 |

---

## Project Objectives

The main objectives of this project are to:

1. Design an appropriate enterprise network topology for the client.
2. Segment network traffic using VLANs.
3. Develop an efficient VLSM-based IP addressing scheme.
4. Implement Inter-VLAN Routing using a Layer 3 switch.
5. Provide a secure Guest Wi-Fi network isolated from internal resources.
6. Provide a dedicated network for servers.
7. Allow for the planned addition of a future application/file server.
8. Implement and test the proposed network using Cisco Packet Tracer.
9. Document configuration, testing and troubleshooting activities.

---

## Network Architecture

The proposed network consists of:

- Edge Router
- Layer 3 Core Switch
- Access Switches
- Engineering workstations
- Management workstations
- Staff workstations
- Server infrastructure
- Guest Wireless Access Point
- Guest devices
- Network management infrastructure

The **Layer 3 Core Switch** acts as the central routing device for the internal VLANs through Switch Virtual Interfaces (SVIs).

Access switches connect end-user devices to the appropriate VLANs, while trunk links are used between the core and access switching infrastructure where required.

---

## VLAN Structure

| VLAN | Name | Purpose | Network |
|---:|---|---|---|
| 10 | MANAGEMENT | Management users | 10.29.0.80/28 |
| 20 | ENGINEERING | Engineering users | 10.29.0.0/27 |
| 30 | STAFF | General staff | 10.29.0.64/28 |
| 40 | SERVERS | Current and future servers | 10.29.0.112/28 |
| 50 | GUEST | Guest wireless users | 10.29.0.32/27 |
| 99 | NET-MGMT | Network infrastructure management | 10.29.0.96/28 |

VLAN segmentation is used to separate different categories of users and services, improve network organisation, reduce unnecessary broadcast traffic, and provide a foundation for security policies.

---

## IP Addressing

The project uses the assigned **10.29.0.0/16** address block.

VLSM is used to allocate subnet sizes according to the estimated requirements of each network segment.

### Default Gateways

| VLAN | Gateway / SVI |
|---:|---|
| 10 | 10.29.0.81 |
| 20 | 10.29.0.1 |
| 30 | 10.29.0.65 |
| 40 | 10.29.0.113 |
| 50 | 10.29.0.33 |
| 99 | 10.29.0.97 |

The addressing scheme also reserves capacity for future network growth.

---

## Inter-VLAN Routing

Inter-VLAN Routing is implemented through the Layer 3 Core Switch.

Each VLAN is assigned a Switch Virtual Interface (SVI), which acts as the default gateway for devices within that VLAN.

The design allows authorised communication between internal VLANs while providing a central point at which security policies can be applied.

---

## Guest Wi-Fi

A dedicated **Guest VLAN (VLAN 50)** is provided for visitors.

The Guest network uses:

```text
Network: 10.29.0.32/27
Gateway: 10.29.0.33
