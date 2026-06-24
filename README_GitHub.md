# README — Junior SOC Analyst Portfolio
## Yamga Younta Yvan

> **Status:** Building | **Target:** SOC Analyst Tier 1 | **Location:** Germany / Remote EU

---

## About This Portfolio

This repository documents my journey from zero to SOC Analyst Tier 1. Every file, screenshot, and script here is a proof of hands-on practice. I built this portfolio with the discipline of 2 hours every night, because I believe mastery comes from repetition, not surface knowledge.

**What you will find here:**
- A fully documented Home Lab (SIEM, agents, network)
- Network analysis with Wireshark
- Windows and Linux log analysis
- SIEM detection rules (Wazuh)
- CyberDefenders write-ups
- Incident response playbooks
- Python scripts for SOC automation
- A complete SOC Analyst Survival Guide

---

## Home Lab Architecture

```
Internet
    │
    ▼
┌─────────┐
│ pfSense │  ← Firewall / Router
│  192.168.1.1  │
└────┬────┘
     │
     ├──────► Ubuntu Server 22.04  ← Wazuh SIEM (192.168.1.10)
     │
     └──────► Windows 10 Pro       ← Agent / Victim (192.168.1.20)
```

**Tools in the lab:**
- VirtualBox (virtualization)
- pfSense (firewall)
- Ubuntu Server (Wazuh SIEM, logs)
- Windows 10 (Sysmon, Event Viewer, agent)
- Wireshark (network analysis)
- Nmap (port scanning)

---

## Repository Structure

```
├── 01-Network-Fundamentals/
│   ├── W1_Network_Fundamentals.md
│   └── screenshots/
├── 02-Home-Lab-Setup/
│   ├── W2_Lab_Setup.md
│   ├── network-diagram.png
│   └── screenshots/
├── 03-Windows-Logs/
│   ├── W3_Windows_Logs.md
│   └── screenshots/
├── 04-Linux-Logs/
│   ├── W4_Linux_Logs.md
│   └── screenshots/
├── 05-Cheat-Sheets/
│   ├── Cheat_Sheet_Linux.md
│   └── Cheat_Sheet_Windows_Event_IDs.md
├── 06-SIEM-Wazuh/
│   ├── W6_Wazuh_Setup.md
│   ├── W8_Custom_Rules.md
│   └── screenshots/
├── 07-Splunk/
│   ├── W10_Splunk_Notes.md
│   └── Cheat_Sheet_Splunk.md
├── 08-Writeups/
│   ├── W12_Writeup_TryHackMe.md
│   ├── CD_Lab1_Investigation.md
│   └── CD_Lab2_Investigation.md
├── 09-Playbooks/
│   ├── Playbook_01_BruteForce_RDP.md
│   ├── Playbook_02_Phishing.md
│   └── Playbook_03_Suspect_Process.md
├── 10-Threat-Intel/
│   └── TI_Brief_Campagne.md
├── 11-Scripts/
│   ├── README.md
│   ├── log_parser.py
│   ├── ip_checker.py
│   └── alert_reporter.py
├── 12-Cloud-Security/
│   └── Cloud_Security_Basics.md
├── 13-Survival-Guide/
│   └── SOC_Analyst_Survival_Guide.pdf
└── 14-Interview-Prep/
    └── Interview_QA.md
```

---

## Key Skills Demonstrated

| Skill | Evidence |
|-------|----------|
| Network Analysis | Wireshark captures, TCP handshake analysis, port scanning |
| Log Analysis | Windows Event Logs, Linux auth logs, Sysmon |
| SIEM Operations | Wazuh installation, custom rules, alert generation |
| Threat Detection | MITRE ATT&CK mapping, CyberDefenders labs |
| Incident Response | 3 playbooks (Brute Force, Phishing, Suspect Process) |
| Automation | Python scripts for log parsing and IP checking |
| Cloud Security | AWS CloudTrail basics |
| Documentation | All write-ups follow professional structure |

---

## Timeline

- **June – July 2026:** Foundations & Home Lab
- **August – September 2026:** SIEM & Detection
- **October – November 2026:** Attack & Response
- **December 2026 – January 2027:** Automation & Threat Intelligence
- **February – March 2027:** Certification & Job Preparation

---

## Certification

- [ ] ISC2 CC (Certified in Cybersecurity) — *In Progress*
- [ ] OR: Splunk Core Certified User — *Planned*

---

## Contact

- **LinkedIn:** [linkedin.com/in/yamga-younta-yvan]
- **Location:** Germany (Open to remote EU)
- **Languages:** French (native), English (technical A2+), German (A2, learning)

---

> This portfolio is a living document. I update it weekly. Last update: [DATE].
