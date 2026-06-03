---
layout: default
title: Active Directory Infrastructure Overview
---

## Project Overview
This project simulates the identity and access infrastructure for a regional Danish hospital (similar to OUH). It demonstrates a "Security-First" approach to enterprise administration using Windows Server 2022 Core, focusing on automation, least privilege, and strict regulatory compliance.

### 🛠️ Technical Deep-Dives
*   **[OU & Group Policy Design]({{ '/projects/ad-deep-dives/ou-and-gpo.html' | relative_url }})**
    *Hierarchy, inheritance, and policy enforcement.*
*   **[Security & Hardening]({{ '/projects/ad-deep-dives/security-hardening.html' | relative_url }})**
    *Administrative tiering, auditing, and account security.*
*   **[Network Services]({{ '/projects/ad-project.html' | relative_url }})**
    *DNS and DHCP configuration.*

---

## 1. Objective
The goal was to build a fully functioning hospital domain from scratch that supports hundreds of shift-workers (Doctors, Nurses, Admin) while protecting sensitive patient data. Key focuses include:
*   **Automated Onboarding:** Using PowerShell to handle mass staff rotations.
*   **Zero-Trust Access:** Implementing the AGDLP model for all file resources.
*   **Compliance:** Advanced security auditing for healthcare standards.

## 2. Access Control Model (RBAC)
I implemented a Role-Based Access Control system using the **AGDLP** (Accounts, Global, Domain Local, Permissions) methodology.

| Department | Role | Global Group (Who) | Domain Local Group (What) | Access Level |
| :--- | :--- | :--- | :--- | :--- |
| **Clinical** | Nurse / Doctor | `G_Clinical_Staff` | `DL_Clinical_Folder_Modify` | Read/Write |
| **Admin** | HR / Secretary | `G_Administration_Staff` | `DL_Administration_Folder_Modify` | Read/Write |
| **IT** | System Admin | `G_IT_Staff` | *(Inherited Full Control)* | Full Control |
| **Hospital** | All Staff | `Domain Users` | `DL_Public_Read` | Read-Only |

## 3. Infrastructure Diagram
![Logical OU Tree]({{ '/assets/images/00_ad_ou_hierarchy_diagram.png' | relative_url }})

---
*Choose a module above to see the full configuration and proof of work.*
