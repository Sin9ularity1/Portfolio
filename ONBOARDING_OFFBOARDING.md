# 🏥 Hospital Infrastructure: Identity Lifecycle Procedure

## 1. Onboarding Procedure (New Hire)
When a new staff member joins the hospital, the IT department executes the `Bulk_Onboarding.ps1` script to ensure consistency and speed.

### Workflow:
1.  **Identity Verification:** HR provides the legal name, department, and job title.
2.  **Account Creation:** Account is created in the department-specific `OU=Users` (e.g., `OU=Clinical`).
3.  **Naming Convention:** `FirstInitial + LastName` (e.g., `kjensen`).
4.  **Role Assignment (AGDLP):**
    *   User added to a **Global Group** (e.g., `G_Clinical_Staff`).
    *   This provides automatic access to departmental shares via **Domain Local Groups**.
5.  **Security Default:** User is forced to change their password at first logon.

---

## 2. Offboarding Procedure (Standard)
For planned departures (resignation/retirement):
1.  **Account Disablement:** `Disable-ADAccount`.
2.  **Resource Cleanup:** Remove user from all Security Groups.
3.  **Data Preservation:** Move user to `OU=Terminated_Users` for a 30-day retention period.
4.  **Deletion:** Permanent deletion after 30 days of inactivity.

---

## 3. Emergency Offboarding (Security Incident)
In the event of a security breach or immediate termination (e.g., the Lars Nielsen incident):
1.  **Immediate Lockout:** Instantly disable the account to kill active sessions.
2.  **Audit Log:** Record the incident time/reason in the AD Description field.
3.  **Quarantine:** Move the object to the `Terminated_Users` OU immediately.
4.  **Access Revocation:** Ensure all Kerberos tickets are cleared (accomplished via account disablement).
