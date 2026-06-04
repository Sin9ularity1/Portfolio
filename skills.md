---
layout: default
title: Technical Skills
---

# Technical Skills

I focus on the intersection of infrastructure management and defensive security. My technical journey is built on four core pillars:

<div class="skills-grid">
    <div class="skill-card">
        <h3>Active Directory</h3>
        <ul>
            <li>Forest & OU Design</li>
            <li>Group Policy (GPOs)</li>
            <li>AGDLP RBAC Model</li>
            <li>Automated Onboarding</li>
        </ul>
    </div>

    <div class="skill-card">
        <h3>Networking</h3>
        <ul>
            <li>VLAN Segmentation</li>
            <li>OPNsense Firewalls</li>
            <li>Traffic Analysis</li>
            <li>VPN Configuration</li>
        </ul>
    </div>

    <div class="skill-card">
        <h3>Systems</h3>
        <ul>
            <li>Linux Hardening</li>
            <li>Wazuh SIEM</li>
            <li>Proxmox / Virtualization</li>
            <li>Centralized Logging</li>
        </ul>
    </div>

    <div class="skill-card">
        <h3>Security & Tools</h3>
        <ul>
            <li>Nmap & Wireshark</li>
            <li>LLM Vulnerability Research</li>
            <li>Incident Response Labs</li>
            <li>Security Documentation</li>
        </ul>
    </div>
</div>

<style>
.skills-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
    margin-top: 2rem;
}

.skill-card {
    background: var(--card-bg);
    padding: 1.5rem;
    border-radius: 8px;
    border: 1px solid var(--border-color);
}

.skill-card h3 {
    margin-top: 0;
    color: var(--accent-color);
    font-size: 1.2rem;
    border-bottom: 1px solid var(--border-color);
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
}

.skill-card ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.skill-card li {
    font-size: 0.9rem;
    margin-bottom: 0.5rem;
    color: var(--text-secondary);
}

@media (max-width: 768px) {
    .skills-grid {
        grid-template-columns: 1fr;
    }
}
</style>
