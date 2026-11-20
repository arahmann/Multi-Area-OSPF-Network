# Multi-Area OSPF Network Design & Implementation

## Project Overview

This project demonstrates the design, configuration, and verification of a multi-area OSPF (Open Shortest Path First) network using Cisco routers and switches in Cisco Packet Tracer.

The network uses three routers connected in a hub-and-spoke topology. OSPF Area 0 acts as the backbone, while two additional areas provide separate LAN segments. The routers exchange routing information dynamically, enabling communication between all three LANs.

## Network Topology

**Topology:** Three routers (R1, R2, R3), three switches, and six PCs.

- R1 connects to R2 and R3.
- Each router connects to its own LAN through a switch.
- R1 operates in OSPF Area 0.
- R2 connects Area 10 to Area 0.
- R3 connects Area 20 to Area 0.

**Topology Screenshot:** `Screenshots/Topology.png` *(to be added)*

## Network Addressing

| Network | IP Address | Purpose |
|---|---|---|
| R1 LAN | 192.168.10.0/24 | Area 0 |
| R2 LAN | 192.168.20.0/24 | Area 10 |
| R3 LAN | 192.168.30.0/24 | Area 20 |
| R1–R2 Link | 10.0.12.0/30 | OSPF Backbone |
| R1–R3 Link | 10.0.13.0/30 | OSPF Backbone |

### Router Interfaces

| Router | Interface | IP Address |
|---|---|---|
| R1 | G0/0 | 192.168.10.1/24 |
| R1 | G0/1 | 10.0.12.1/30 |
| R1 | G0/2 | 10.0.13.1/30 |
| R2 | G0/0 | 192.168.20.1/24 |
| R2 | G0/1 | 10.0.12.2/30 |
| R3 | G0/0 | 192.168.30.1/24 |
| R3 | G0/1 | 10.0.13.2/30 |

## OSPF Configuration

The project uses OSPF Process ID 1 with manually configured Router IDs.

| Router | Router ID | OSPF Areas |
|---|---|---|
| R1 | 1.1.1.1 | Area 0 |
| R2 | 2.2.2.2 | Areas 0 and 10 |
| R3 | 3.3.3.3 | Areas 0 and 20 |

R2 and R3 function as Area Border Routers (ABRs), connecting their respective non-backbone areas to Area 0.

## Technologies & Concepts

- Cisco Packet Tracer
- Cisco IOS CLI
- OSPF Dynamic Routing
- Multi-Area OSPF
- OSPF Router IDs
- OSPF Neighbor Adjacencies
- Backbone Area (Area 0)
- Area Border Routers (ABRs)
- Inter-Area Route Advertisement
- IPv4 Addressing and Subnetting
- /30 Point-to-Point Networks
- Routing Table Analysis

## Verification & Testing

The following checks were performed:

- Verified OSPF neighbor adjacencies on R1.
- Confirmed FULL neighbor states with R2 and R3.
- Verified OSPF-learned routes on all three routers.
- Confirmed inter-area routes using the `O IA` route designation.
- Tested connectivity between PCs on different LANs.
- Confirmed successful communication between all three LAN segments.

### Verification Commands

```text
show ip ospf
show ip ospf neighbor
show ip route ospf
show ip route
show ip interface brief
```

## Screenshots

The `Screenshots` folder contains the following verification evidence:

1. `R1-show ip ospf neighbor & show ip route ospf`
2. `R2-show ip route ospf`
3. `R3-show ip route ospf`
4. PC1 successful connectivity tests to the R2 and R3 LANs.
5. PC3 successful connectivity test to the R3 LAN.

The network topology screenshot will also be added to this folder.

## Project Files

- `Multi_Area_OSPF_Network_Design.pkt` — Cisco Packet Tracer project file.
- `README.md` — Project documentation.
- `Screenshots/` — Network topology and verification screenshots.

## Learning Outcomes

Through this project, I practiced configuring multi-area OSPF, establishing neighbor adjacencies, understanding Area Border Routers, analyzing routing tables, and verifying end-to-end connectivity across multiple network areas.

**Tools:** Cisco Packet Tracer | Cisco IOS CLI
