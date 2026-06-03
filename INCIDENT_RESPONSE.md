# 🚨 Incident Response Report: Unauthorized Data Access Simulation

## 1. Incident Overview
*   **Subject:** Lars Nielsen (Clinical Staff)
*   **Incident Type:** Unauthorized access attempt to sensitive patient data.
*   **Detection Method:** Advanced Security Auditing (Event ID 4625 - Failed Login / 4663 - Object Access).

## 2. Detection & Analysis
Using the **Advanced Security Auditing** policies implemented in Step 9:
1.  **Alert:** Multiple failed access attempts were recorded on the `C:\Hospital_Data\Administration` share.
2.  **Source:** Account `lnielsen` attempted to access HR payroll files.
3.  **Verification:** Logs confirmed that the user's role (`G_Clinical_Staff`) did not have the necessary permissions assigned via the AGDLP model.

## 3. Containment
The **Emergency Offboarding Procedure** was triggered:
*   Account `lnielsen` was disabled via PowerShell in under 5 seconds.
*   User was moved to the `OU=Terminated_Users` container to prevent any further network traversal.

## 4. Remediation & Recovery
*   **Permissions Audit:** Verified that no other accounts in the `G_Clinical_Staff` group had similar unauthorized access.
*   **Policy Review:** Confirmed the NTFS "Least Privilege" settings on the file server were functioning correctly.

## 5. Post-Incident Activity
*   Incident documented in the AD User Description for forensic tracking.
*   Reporting to Hospital Compliance Board (Simulation).
