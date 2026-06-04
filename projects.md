---
layout: default
title: Projects Overview
---

# My Engineering Labs

Welcome to my technical portfolio. These projects document my hands-on experience in building, securing, and analyzing enterprise infrastructures.

<div class="projects-grid">
    <div class="project-card">
        <h3>Active Directory</h3>
        <p>Enterprise identity management and forest security.</p>
        <a href="{{ '/projects/active-directory/hospital-ad-project.html' | relative_url }}" class="btn-card">Hospital AD Lab</a>
    </div>

    <div class="project-card">
        <h3>Networking</h3>
        <p>Core infrastructure, VLAN segmentation, and perimeter defense.</p>
        <a href="{{ '/projects/networking/2nd-semester-project.html' | relative_url }}" class="btn-card">2nd Sem Project</a>
    </div>

    <div class="project-card">
        <h3>Systems Admin</h3>
        <p>Server hardening, centralized logging, and SIEM monitoring.</p>
        <a href="{{ '/projects/systems/2nd-semester-project.html' | relative_url }}" class="btn-card">2nd Sem Project</a>
    </div>

    <div class="project-card">
        <h3>AI Security</h3>
        <p>Researching vulnerabilities and mitigations for Generative AI.</p>
        <a href="{{ '/projects/ai-security/generative-ai-misuse.html' | relative_url }}" class="btn-card">AI Misuse Lab</a>
    </div>
</div>

<style>
.projects-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
    margin-top: 3rem;
}

.project-card {
    background: var(--card-bg);
    padding: 2rem;
    border-radius: 12px;
    border: 1px solid var(--border-color);
    transition: all 0.2s ease-in-out;
    display: flex;
    flex-direction: column;
}

.project-card:hover {
    border-color: var(--accent-color);
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

.project-card h3 {
    margin-top: 0;
    color: var(--accent-color);
    font-size: 1.4rem;
}

.project-card p {
    font-size: 0.95rem;
    color: var(--text-secondary);
    line-height: 1.6;
    margin-bottom: 2rem;
    flex-grow: 1;
}

.btn-card {
    display: inline-block;
    padding: 0.6rem 1.2rem;
    background: transparent;
    border: 1px solid var(--accent-color);
    color: var(--accent-color);
    text-decoration: none;
    border-radius: 6px;
    font-weight: 600;
    text-align: center;
    font-size: 0.9rem;
    transition: all 0.2s;
}

.btn-card:hover {
    background: var(--accent-color);
    color: var(--bg-color);
    text-decoration: none;
}

@media (max-width: 768px) {
    .projects-grid {
        grid-template-columns: 1fr;
    }
}
</style>
