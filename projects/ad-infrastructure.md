---
layout: default
title: Active Directory Infrastructure
---

## 1. Objective
This project demonstrates the design and implementation of a scalable Active Directory Domain Services (AD DS) infrastructure, focusing on organizational unit (OU) structure, Group Policy management, and secure user authentication.

## 2. Infrastructure Overview
*   **Domain Controller:** Windows Server 2022.
*   **Forest Level:** Windows Server 2016 or higher.
*   **Clients:** Windows 10/11 Enterprise.

## 3. Key Configurations
### OU Structure
A logical hierarchy designed for delegated administration:
*   `Standard-Users`
*   `Admin-Accounts`
*   `Workstations`
*   `Servers`

### Group Policy Objects (GPOs)
*   **Default Domain Policy:** Password complexity and lockout requirements.
*   **Workstation Hardening:** Disabling USB storage and enforcing screen lock timeouts.
*   **Drive Mapping:** Automated mapping of department-specific network shares via GPP.

## 4. Security Implementation
*   **Privileged Access:** Implementation of "Least Privilege" using separate administrative accounts.
*   **DNS Security:** Secure dynamic updates and scavenging configurations.

## 5. Verification
*   Successful domain join for client workstations.
*   `gpresult /r` verification of applied policies on target machines.
*   Active Directory Administrative Center (ADAC) health checks.

---
*(Documentation for this project is ongoing. Screenshots of the OU structure and GPO settings will be added soon.)*
