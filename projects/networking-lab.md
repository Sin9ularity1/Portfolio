---
layout: default
title: Networking Lab – VLAN Segmentation and Trunking
---

## 1. Objective
This lab demonstrates how VLANs segment broadcast domains to improve network security and efficiency, and how 802.1Q trunking allows multiple VLANs to traverse a single physical link.

## 2. Topology Diagram
*(Placeholder for GNS3 Screenshot or LucidChart Diagram)*

**Physical Layout:** 
Two Cisco Switches (SW1, SW2) connected via a GigabitEthernet trunk link, supporting multiple client VLANs (Sales, Engineering).

## 3. Theory
*   **VLAN:** Logical segmentation of a Layer 2 network to reduce broadcast traffic.
*   **802.1Q:** The industry standard for frame tagging on trunks.
*   **Trunk Port:** A port configured to carry traffic for multiple VLANs simultaneously.

## 4. Configuration
Example Cisco IOS CLI for creating VLANs and configuring trunks:

```ios
! Configure VLANs
vlan 10
 name SALES
vlan 20
 name ENG

! Access Port Configuration
interface g0/1
 switchport mode access
 switchport access vlan 10

! Trunk Port Configuration
interface g0/0
 description TRUNK-TO-SW2
 switchport trunk encapsulation dot1q
 switchport mode trunk
```

## 5. Verification & Testing
To ensure the configuration is operational, use the following commands:
*   `show vlan brief` – Verifies VLAN assignment to ports.
*   `show interfaces trunk` – Confirms the status and allowed VLANs on the trunk.
*   **Ping Test:** Successful ICMP echo between devices in the same VLAN across switches.

## 6. Troubleshooting Scenario
*   **Issue:** Devices in the same VLAN on different switches could not communicate.
*   **Discovery:** `show interfaces trunk` revealed the interconnecting link was mistakenly set to `access` mode.
*   **Resolution:** Applied `switchport mode trunk` to both ends of the link. Connectivity was immediately restored.

## 7. Real-World Use Case
*   **Guest Network Separation:** Keeping visitor traffic completely isolated from the corporate LAN.
*   **VoIP VLAN:** Segregating voice traffic to apply Quality of Service (QoS) policies.
