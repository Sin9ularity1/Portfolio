---
layout: default
title: 2nd Semester Project - System Security
---

# 2nd Semester Project: Hardening & Monitoring

[<- Back to Projects]({{ '/projects.html' | relative_url }})

## 1. SIEM Deployment (Wazuh)
Centralized visibility was a core requirement. I deployed a Wazuh manager to provide real-time threat detection across the entire server environment.

### Monitoring Capabilities
*   **Authentication Tracking:** Monitoring for brute-force attempts and suspicious login patterns.
*   **File Integrity Monitoring (FIM):** Detecting unauthorized changes to critical configuration files in `/etc/` and `/bin/`.
*   **Vulnerability Scanning:** Automated detection of missing patches and insecure system configurations.

**Placeholder: Wazuh Security Dashboard**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_wazuh_alerts.png`*

---

## 2. System Hardening
I performed deep hardening on the internal Ubuntu Server environment to reduce the local attack surface.

### Hardening Actions
*   **SSH Security:** Disabled password authentication, enforced SSH keys, and restricted root login.
*   **Service Minimization:** Audited and disabled all unnecessary background services and network listeners.
*   **Kernel Hardening:** Applied `sysctl` security tweaks to mitigate common network-based attacks.

**Placeholder: Hardening Verification Audit**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_hardening_audit.png`*

---

## 3. Logging & Telemetry
Beyond the SIEM, I configured system-level logging to ensure a durable audit trail for forensic analysis. This involved consolidating logs from multiple distributed agents into the central manager.

**Placeholder: Log Inventory Overview**
*File: `C:\Users\Reuben\Desktop\Portfolio\assets\images\2nd_sem_log_telemetry.png`*

---
[<- Back to Projects]({{ '/projects.html' | relative_url }})
