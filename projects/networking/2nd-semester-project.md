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

![Original Flat Network]({{ '/assets/images/2nd_sem_network_before.png' | relative_url }})

### After: Segmented Infrastructure
I implemented 802.1Q VLAN tagging to isolate departments and sensitive assets into distinct security zones.

*   **VLAN 10:** Network Infrastructure
*   **VLAN 20:** On-prem Servers
*   **VLAN 30:** Management & Finance (Sensitive Data)
*   **VLAN 50:** Guest Network (Isolated)
*   **VLAN 60:** IT Administration

![Segmented Network Diagram]({{ '/assets/images/2nd_sem_network_after.png' | relative_url }})

---

## 2. Firewall Orchestration (OPNsense)
I configured an OPNsense firewall to act as the core gateway and inter-VLAN router. 

### Implementation Details
*   **Implicit Deny:** Configured a "Default Deny" posture where all inter-VLAN traffic is blocked unless explicitly permitted.
*   **Stateful Inspection:** Leveraged OPNsense's stateful inspection to monitor active handshakes and session integrity.
*   **NAT & WAN Security:** Hardened the perimeter against external probes while allowing secure outbound traffic.

![Firewall Rules]({{ '/assets/images/2nd_sem_firewall_config.png' | relative_url }})

---

## 3. Remote Administration (Jump Host)
To allow for secure remote management, I implemented a dedicated Jump Host server. This setup allows me to SSH into the internal network from home without exposing management interfaces (like the OPNsense WebGUI or internal server SSH ports) directly to the public internet. 

This follows security best practices by providing a single, hardened entry point for administrative tasks.

---
[<- Back to Projects]({{ '/projects.html' | relative_url }})
