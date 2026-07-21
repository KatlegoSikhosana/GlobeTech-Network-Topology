# GlobeTech-Network-Topology
# GlobeTech Multi-Site Network Topology

A Cisco Packet Tracer network design project simulating a multi-branch enterprise network for a company (GlobeTech) with three sites: **Johannesburg (JHB)**, **Cape Town (CPT)**, and **Potchefstroom (POT)**. The project covers full IP addressing design, routing, VLAN segmentation, high availability, and wireless infrastructure across all locations.

## File

- `GlobeTech-Multi-Site-Network.pkt` — open with [Cisco Packet Tracer](https://www.netacad.com) to view and interact with the topology

## Network Design

### WAN Links (Point-to-Point, /30 subnets)
- `R0_JHB ↔ Cloud_ISP`
- `R1_CPT ↔ Cloud_ISP`
- `R0_JHB ↔ R1_CPT`
- `R1_CPT ↔ R2_POT`

### Router-to-Switch Links
- `R0_JHB ↔ L3_JHB`
- `R1_CPT ↔ L3_CPT`

### VLAN Structure

| Site | VLAN | Purpose | Network |
|---|---|---|---|
| Shared | VLAN 99 | Management | 10.0.0.32/28 |
| JHB | VLAN 20 | Main Data Network | 172.16.0.0/24 |
| JHB | VLAN 10 | GlobeTech-WIFI | 172.16.1.0/25 |
| JHB | VLAN 100 | Guest-WIFI | 172.16.1.128/25 |
| CPT | VLAN 30 | Main Data Network | 172.16.2.0/26 |
| CPT | VLAN 10 | GlobeTech-WIFI | 172.16.3.0/25 |
| CPT | VLAN 100 | Guest-WIFI | 172.16.3.128/25 |
| POT | VLAN 40 | Main Data Network | 172.16.2.64/27 |
| POT | VLAN 10 | GlobeTech-WIFI | 172.16.4.0/25 |
| POT | VLAN 100 | Guest-WIFI | 172.16.4.128/25 |
| Shared | VLAN 60 | Printers | 172.16.2.96/27 |

## Features Implemented

- **IP Addressing & Subnetting** — Custom VLSM design across WAN links, management, and access-layer VLANs
- **VLAN Segmentation** — Separate VLANs per site for data, staff wireless, guest wireless, and printers
- **Inter-VLAN Routing** — Configured via multilayer switches at each site
- **DHCP** — Centralized DHCP configuration for Johannesburg and Cape Town
- **Routing** — Site-to-site routing across all three locations
- **Access Control Lists (ACLs)** — Applied per site for traffic control
- **NAT** — Configured at each site for internet-bound traffic
- **HSRP** — High availability gateway redundancy on Johannesburg router and multilayer switch
- **Wireless LAN Controllers (WLC)** — Deployed at Johannesburg and Cape Town for centralized wireless management
- **Trunking & Access Ports** — Configured across multilayer switches at all three sites

## Tools Used

- Cisco Packet Tracer
- IPv4 subnetting / VLSM
- OSPF-based routing concepts

## Notes

This project was completed as part of coursework covering enterprise network design, addressing, and Cisco device configuration.
