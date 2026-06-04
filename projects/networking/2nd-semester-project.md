---
layout: default
title: 2nd Semester Project - Networking
---

# 2nd Semester Project: Network Infrastructure & Segmentation

[<- Back to Projects]({{ '/projects.html' | relative_url }})

## 1. Network Segmentation (VLAN Design)
The primary objective was to move from a flat network to a segmented architecture to reduce the attack surface and enforce the principle of least privilege.

### Before: Flat Network
Initially, all devices (Servers, IT, Employees, Guests) were on a single subnet, allowing unrestricted lateral movement.

**Placeholder: Original Flat Network**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_network_before.png`*

### After: Segmented Infrastructure
I implemented 802.1Q VLAN tagging to isolate departments and sensitive assets into distinct security zones.

*   **VLAN 10:** Network Infrastructure
*   **VLAN 20:** On-prem Servers
*   **VLAN 30:** Management & Finance (Sensitive Data)
*   **VLAN 50:** Guest Network (Isolated)
*   **VLAN 60:** IT Administration

**Placeholder: Segmented Network Diagram**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_network_after.png`*

---

## 2. Firewall Orchestration (OPNsense)
I configured an OPNsense firewall to act as the core gateway and inter-VLAN router. 

### Implementation Details
*   **Implicit Deny:** Configured a "Default Deny" posture where all inter-VLAN traffic is blocked unless explicitly permitted.
*   **Stateful Inspection:** Leveraged OPNsense's stateful inspection to monitor active handshakes and session integrity.
*   **NAT & WAN Security:** Hardened the perimeter against external probes while allowing secure outbound traffic.

**Placeholder: Firewall Rule Inventory**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_firewall_config.png`*

---

## 3. Remote Access (VPN)
To allow for secure remote administration, I implemented a VPN gateway. This ensures that IT staff can manage the infrastructure without exposing management ports (SSH/WebGUI) directly to the internet.

**Placeholder: VPN Gateway Configuration**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_vpn_setup.png`*

---
[<- Back to Projects]({{ '/projects.html' | relative_url }})
