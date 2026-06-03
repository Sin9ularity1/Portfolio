---
layout: default
title: Hospital Active Directory Environment
---

# 🏥 Regional Hospital: Identity & Access Infrastructure

[← Back to Projects]({{ '/projects.html' | relative_url }})

## 1. Project Overview
This project demonstrates the design and implementation of a secure enterprise Active Directory environment for a medium-sized Danish hospital (simulated). The focus was on building a zero-trust architecture that supports clinical operations while strictly enforcing data privacy and security.

### Key Features
*   **Infrastructure:** Windows Server 2022 Core (DC, DNS, DHCP).
*   **Automation:** PowerShell-driven onboarding and emergency offboarding.
*   **Access Control:** Full implementation of the AGDLP methodology.
*   **Compliance:** Advanced security auditing and GPO hardening.

---

## 2. Architectural Design
Before any implementation, the environment was mapped physically and logically.

### Physical Network Topology
This diagram shows the core server infrastructure and the isolated workstation segments for Clinical and Administrative staff.
![Physical Network Topology]({{ '/assets/images/00_physical_network_topology.png' | relative_url }})

### Logical OU Hierarchy
A department-centric OU structure was chosen to allow for granular GPO application (e.g., stricter lockouts for nurses than administrators).
![Logical OU Hierarchy]({{ '/assets/images/00_ad_ou_hierarchy_diagram.png' | relative_url }})

---

## 3. Implementation Phases

### Phase 1: Foundation & AD Promotion
The server was configured with a static identity before being promoted to a Domain Controller for the `lab.hospital.dk` forest.
![Server Config]({{ '/assets/images/01_server_prep_config.png' | relative_url }})
![Domain Verification]({{ '/assets/images/04_domain_verification.png' | relative_url }})

### Phase 2: RBAC & AGDLP Model
I implemented a Role-Based Access Control system to ensure "Least Privilege" across the hospital.

| Department | Role | Global Group | Domain Local Group | Access Level |
| :--- | :--- | :--- | :--- | :--- |
| **Clinical** | Medical Staff | `G_Clinical_Staff` | `DL_Clinical_Folder_Modify` | Read/Write |
| **Admin** | HR/Finance | `G_Administration_Staff` | `DL_Administration_Folder_Modify` | Read/Write |
| **IT** | SysAdmin | `G_IT_Staff` | *(Full Control)* | Full Control |

![Security Groups]({{ '/assets/images/06_rbac_groups_list.png' | relative_url }})

### Phase 3: Automated Identity Management
Using PowerShell, I automated the creation of staff accounts and their immediate assignment to security groups. This allows for rapid onboarding of shift-workers.
![Bulk Onboarding]({{ '/assets/images/08_bulk_user_creation.png' | relative_url }})
![User Inventory]({{ '/assets/images/09_user_inventory_list.png' | relative_url }})

### Phase 4: Security Hardening (GPO)
Specific policies were enforced to protect patient data, including USB blocking on clinical PCs and forced screen lockouts.
![GPO Inventory]({{ '/assets/images/07_gpo_security_hardening.png' | relative_url }})
![Security Auditing]({{ '/assets/images/11_advanced_auditing_policy.png' | relative_url }})

---

## 4. Resource Security
Final verification of the file system shows that the AGDLP model successfully restricts access to departmental data.
![File Share Permissions]({{ '/assets/images/10_file_shares_permissions.png' | relative_url }})

---

## 5. Incident Response Simulation
To test the environment's responsiveness, I simulated an emergency termination of a compromised account. The account was disabled, quarantined, and audited in under 5 seconds via PowerShell.
![Emergency Offboarding]({{ '/assets/images/14_emergency_offboarding.png' | relative_url }})

---
[← Back to Projects]({{ '/projects.html' | relative_url }})
