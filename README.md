# Secure Small Enterprise Network Simulation

A secure multi-VLAN network infrastructure design and simulation for a small enterprise using Cisco Packet Tracer. The project implements network segmentation, dynamic IP addressing via a dedicated DHCP server, Inter-VLAN routing, and network security policies using Access Control Lists (ACLs).

## 🏢 Network Architecture & Design
The network is segmented into three departments to optimize performance and security:
*   **VLAN 10 (HR Department):** Subnet `192.168.1.0/24` (Gateway: `192.168.1.1`)
*   **VLAN 20 (IT Department):** Subnet `192.168.2.0/24` (Gateway: `192.168.2.1`)
*   **VLAN 30 (Finance Department):** Subnet `192.168.3.0/24` (Gateway: `192.168.3.1`)

## 🛠️ Key Features Implemented
1.  **VLAN Segmentation & Trunking:** Configured IEEE 802.1Q trunking between the core Switch and Router to separate department traffic.
2.  **Dedicated DHCP Server Routing:** Deployed a centralized DHCP Server in VLAN 20. Configured `ip helper-address` on the Router sub-interfaces to relay DHCP requests across different broadcast domains securely.
3.  **Inter-VLAN Routing:** Configured Router-on-a-Stick (ROAS) using sub-interfaces to manage communication between departments.
4.  **Network Security (ACL):** Implemented an Extended Access Control List (ACL 100) on the Finance gateway to restrict the HR department from accessing confidential Finance resources while ensuring IT access remains uninterrupted.

## 🚀 Verification and Testing
*   **DHCP Verification:** All endpoint devices successfully lease IP addresses dynamically from the central server.
*   **Security Policy Enforcement:** Pings from the HR network to the Finance network are successfully blocked with `Destination host unreachable`. Pings from IT to Finance are fully permitted.
