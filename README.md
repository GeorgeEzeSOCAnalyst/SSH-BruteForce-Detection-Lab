# SSH-BruteForce-Detection-Lab
SSH brute force simulation using Hydra - detected by Wazuh SIEM - NIST SP 800-61
# 🔴 SSH Brute Force Detection Lab

## Incident ID: INC-2026-0512-001 | May 12, 2026

## 🎯 Objective
Simulate a real-world SSH brute force attack using Hydra,
detect it with Wazuh SIEM, respond following NIST SP 800-61
IR methodology, and map to MITRE ATT&CK framework.

## 🏗️ Lab Architecture
| Component | Details |
|-----------|---------|
| Wazuh Manager | Docker on Kali Linux — v4.10.3 |
| Ubuntu Agent | IP: 192.168.0.138 — Agent: ICONIC |
| Suricata IDS | Network intrusion detection |
| VirusTotal API | Malware file scanning |
| Hydra v9.6 | Brute force simulation tool |

## ⚔️ Attack Details
| Parameter | Value |
|-----------|-------|
| Tool | Hydra v9.6 |
| Wordlist | rockyou.txt (14,344,399 passwords) |
| Speed | 104 attempts per minute |
| Target | SSH port 22 — marlinspike@192.168.0.138 |
| Duration | ~3 minutes |

## 🔍 Detection Results
| Metric | Value |
|--------|-------|
| Total Wazuh Alerts | 609 alerts |
| Detection Time | < 30 seconds |
| Rule Triggered | Rule 40111 — Level 10 |
| MTTC | 6 minutes |
| MTTR | 16 minutes |
| Breach | NONE — Attack Failed |

## 🧠 MITRE ATT&CK Mapping
| Technique | ID | Tactic |
|-----------|-----|--------|
| Brute Force | T1110 | Credential Access |
| Password Guessing | T1110.001 | Credential Access |
| Remote Services: SSH | T1021.004 | Lateral Movement |
| Valid Accounts | T1078 | Initial Access |

## 🛡️ Response Actions
- ✅ Blocked attacker IP via iptables
- ✅ Disabled SSH password authentication
- ✅ Set MaxAuthTries to 3
- ✅ Installed fail2ban
- ✅ Followed NIST SP 800-61 all 4 phases

## 📂 Files in This Repo
- 📄 SOC_Playbook_NIST_GeorgeEze.pdf
- 📄 SOC_Incident_Report_1Page_GeorgeEze.pdf
- 📸 Screenshots — Wazuh dashboard, MITRE ATT&CK map, alerts

## 🔗 References
- NIST SP 800-61 Rev.2
- MITRE ATT&CK T1110
- CIS Controls v8

## 👤 Analyst
George Eze | SOC Analyst
github.com/GeorgeEzeSOCAnalyst
