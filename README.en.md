<div align="right">
  <a href="./README.md"><img src="./assets/btn-pt-inactive.svg" height="32" alt="PT · Português" /></a>
  <a href="./README.en.md"><img src="./assets/btn-en-active.svg" height="32" alt="EN · English" /></a>
  <a href="./README.static.md"><img src="./assets/btn-static.svg" height="32" alt="No motion" /></a>
</div>

<p align="center">
  <img src="./assets/hero-banner.svg" width="100%" alt="Daniel Widal - Cyber Threat Intelligence & Threat Hunting" />
</p>

## 🛡️ Daniel Widal

**Information Security Analyst · Cyber Threat Intelligence (CTI) · Threat Hunting · Detection Engineering**

Focused on the collection, enrichment, and operationalization of threat data — correlating **IOCs, TTPs, and adversary behaviors** to anticipate attack vectors, build proactive detection rules, and guide incident response.

My approach bridges **technical artifact analysis** (PCAP network traffic, malware samples, and application/network logs) with **MITRE ATT&CK mapping**, turning raw telemetry into actionable intelligence for **Cloudflare WAF, SIEM (Wazuh), and observability pipelines (Grafana)**. In my research lab, I operate a **custom Python-powered honeypot** as a primary telemetry source for threat hunting and Kill Chain reconstruction.

<p align="left">
  <a href="#-applied-intelligence-lifecycle"><img src="./assets/nav-cycle-en.svg" height="34" alt="CTI Lifecycle" /></a>
  <a href="#-threat-intelligence--malwarenetwork-analysis"><img src="./assets/nav-cases-en.svg" height="34" alt="Investigations" /></a>
  <a href="#-security-stack--tools"><img src="./assets/nav-stack-en.svg" height="34" alt="Stack & Tools" /></a>
  <a href="#-connect-with-me"><img src="./assets/nav-contact-en.svg" height="34" alt="Contact" /></a>
  <a href="https://pendragon711.github.io"><img src="https://img.shields.io/badge/WEB_PORTFOLIO-pendragon711.github.io-D4AF37?style=for-the-badge&labelColor=0a0b0e" alt="Web Portfolio" /></a>
</p>

---

## 🎯 Applied Intelligence Lifecycle

How I transform telemetry and malicious artifacts into proactive defense:

| Phase | Technical Execution |
| :--- | :--- |
| **01 · Collection & Telemetry** | Capturing malicious traffic via honeypots, WAF/SIEM logs, OSINT feeds, and network captures (PCAP). |
| **02 · Enrichment** | Extraction, validation, and defanging of IOCs (hashes, domains, IPs, C2) via VirusTotal, ANY.RUN, and static/dynamic analysis. |
| **03 · TTP Analysis** | Kill Chain reconstruction, identification of native binary abuse (*LOLBins*), and **MITRE ATT&CK** mapping. |
| **04 · Operationalization** | Translating intelligence into blocking and detection rules (WAF, SIEM/Wazuh, YARA/Sigma) and proactive hunts. |

---

## 🔬 Threat Intelligence & Malware/Network Analysis

Technical investigations focused on **payload extraction, behavioral threat analysis, TTP mapping, and actionable IOC generation**.

### 🕸️ Dossier 01: DanaBot — Network Traffic & Kill Chain

> **Network traffic (PCAP) investigation of a multi-stage DanaBot malware infection, isolating disguised payloads, C2 infrastructure, and adversary TTPs.**

`Wireshark` `Network Analysis` `VirusTotal` `ANY.RUN` `PowerShell` `MITRE ATT&CK` `OSINT`

- **Deep Packet Inspection:** Identified attack origin and initial vector via HTTP GET requests.
- **Payload Extraction:** Reconstructed HTTP streams to isolate malicious artifacts (`.js` disguised as `.php`) and secondary payloads (`.dll`).
- **Behavioral & LOLBins Mapping:** Analyzed sandbox execution tree, identifying `wscript.exe` abuse for stealthy execution.
- **IOC Reporting:** Generated file hashes (SHA-256/MD5) and defanged indicators to feed defensive rules.

🔗 **[Access Full Dossier →](https://github.com/Pendragon711/danabot-dfir-investigation)**

---

### 🔎 Dossier 02: XLMRat — Delivery Chain & Malware Triage

> **Analysis of the delivery and execution chain of AsyncRAT (XLMRat scenario), correlating network and host artifacts for IOC extraction and MITRE ATT&CK mapping.**

`Wireshark` `CyberChef` `VirusTotal` `Python` `MITRE ATT&CK`

- **Traffic & Artifact Analysis:** Identified initial HTTP download containing a `.jpg` file with a spoofed header.
- **Deobfuscation:** Payload deobfuscation and extraction of compilation metadata/timestamps from the malicious binary.
- **Defense Evasion Tracking:** Mapped abuse of the `RegSvcs.exe` LOLBin for process injection and defense evasion.
- **MITRE ATT&CK Mapping:** Full classification of observed techniques (`T1105`, `T1059.001`, `T1218.009`, `T1620`) and IOC report delivery.

🔗 **[Access Full Dossier →](https://github.com/Pendragon711/xlmrat-dfir-investigation)**

---

### 🛡️ CTI Workbench: ARGOS CTI — Threat Intelligence Platform

> **Local-first cyber threat intelligence platform in Go with SQLite persistence, embedded 5-step Web UI (`127.0.0.1:8080`), concurrent multi-provider enrichment, SHA-256 evidence tracking, depth-bounded graph pivoting, and STIX 2.1 / Markdown / CSV / JSON export.**

`Go` `SQLite` `Web UI` `STIX 2.1` `AbuseIPDB` `VirusTotal` `OTX` `CrowdSec`

- **Ingestion, Triage & Multi-Provider Enrichment:** Extracts and normalizes IPs, domains, URLs, hashes, and emails (including defanged indicators and `key=value` log fields) with concurrent lookups across AbuseIPDB, VirusTotal, AlienVault OTX, and CrowdSec CTI.
- **Guided 5-Step Workflow & Export:** Covers Case & Scope, Ingestion & Triage, Evidence (with certainty levels and automatic SHA-256 digests), Relationships & Pivot, and Case Assessment with Markdown, STIX 2.1, CSV, and JSON exports.

🔗 **[Explore ARGOS Repository →](https://github.com/Pendragon711/argos-cti)**

---

## ⚔️ Attack Surface & Recon (Offensive Perspective)

Mapping exposed attack surfaces is critical to anticipate exploitation vectors and prioritize defenses.

- 👁️ **[ODIN](https://github.com/Pendragon711/odin-recon)** — Automated reconnaissance and Attack Surface Management (ASM) pipeline written in Go (`Subfinder`, `Naabu`, `HTTPX`) for asset discovery and WAF detection.

---

## 🧰 Security Stack & Tools

### 🎯 Threat Intelligence & Analysis
<p align="left">
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-0a0b0e?style=for-the-badge&logo=mitre&logoColor=D4AF37" alt="MITRE ATT&CK" />
  <img src="https://img.shields.io/badge/Wireshark-0a0b0e?style=for-the-badge&logo=wireshark&logoColor=D4AF37" alt="Wireshark" />
  <img src="https://img.shields.io/badge/CyberChef-0a0b0e?style=for-the-badge&logo=cyberchef&logoColor=D4AF37" alt="CyberChef" />
  <img src="https://img.shields.io/badge/VirusTotal-0a0b0e?style=for-the-badge&logo=virustotal&logoColor=D4AF37" alt="VirusTotal" />
</p>

**Focus:** IOC Enrichment • TTP Mapping • PCAP & Payload Analysis • Malware Triage • Attack Surface Recon

### 🛡️ Detection Engineering, SIEM & AppSec
<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-0a0b0e?style=for-the-badge&logo=wazuh&logoColor=D4AF37" alt="Wazuh" />
  <img src="https://img.shields.io/badge/Cloudflare%20WAF-0a0b0e?style=for-the-badge&logo=cloudflare&logoColor=D4AF37" alt="Cloudflare WAF" />
  <img src="https://img.shields.io/badge/Grafana-0a0b0e?style=for-the-badge&logo=grafana&logoColor=D4AF37" alt="Grafana" />
  <img src="https://img.shields.io/badge/SIEM-0a0b0e?style=for-the-badge&logo=elasticstack&logoColor=D4AF37" alt="SIEM" />
</p>

**Focus:** Threat Hunting • Log Correlation • Custom Detection Rules • WAF Mitigation • Traffic Anomaly Analysis

### ⚙️ Automation & Infrastructure
<p align="left">
  <img src="https://img.shields.io/badge/Python-0a0b0e?style=for-the-badge&logo=python&logoColor=D4AF37" alt="Python" />
  <img src="https://img.shields.io/badge/Go-0a0b0e?style=for-the-badge&logo=go&logoColor=D4AF37" alt="Go" />
  <img src="https://img.shields.io/badge/Linux-0a0b0e?style=for-the-badge&logo=linux&logoColor=D4AF37" alt="Linux" />
  <img src="https://img.shields.io/badge/Bash-0a0b0e?style=for-the-badge&logo=gnubash&logoColor=D4AF37" alt="Bash" />
</p>

---

## 🎓 Education & Certifications

- 🎓 **B.Tech in Cybersecurity** — UniCesumar *(In progress)*
- 📜 **Google Cybersecurity Professional Certificate** — Coursera
- 📜 **Cisco Junior Cybersecurity Analyst** — Cisco Networking Academy
- 📜 **SOC Analyst in the AI Era** — IBSEC
- 📜 **SOC Fundamentals** — Be Safe Inc.
- 📜 **AWS Cloud Practitioner Essentials** — Amazon Web Services
- 📜 **Nano Course Cybersecurity** — FIAP

---

## 📊 Telemetry & GitHub Stats

<div align="center">
  <img height="175em" src="https://github-readme-streak-stats.herokuapp.com/?user=Pendragon711&background=0a0b0e&border=3d3112&stroke=3d3112&ring=D4AF37&fire=F5D77F&currStreakNum=F9FAFB&sideNums=F9FAFB&currStreakLabel=D4AF37&sideLabels=9CA3AF&dates=6B7280"/>
  <img height="175em" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Pendragon711&theme=github_dark"/>
</div>

---

## 📫 Connect with me

<div align="center">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/Portfolio-0a0b0e?style=for-the-badge&logo=googlechrome&logoColor=D4AF37" alt="Portfolio"/>
  </a>
  <a href="https://www.linkedin.com/in/danielwidal">
    <img src="https://img.shields.io/badge/LinkedIn-0a0b0e?style=for-the-badge&logo=linkedin&logoColor=D4AF37" alt="LinkedIn"/>
  </a>
  <a href="mailto:daniels2live666@gmail.com">
    <img src="https://img.shields.io/badge/Email-0a0b0e?style=for-the-badge&logo=gmail&logoColor=D4AF37" alt="Email"/>
  </a>
</div>

---

<p align="center">
  ◈ <strong>"Turn raw threat data into actionable defense."</strong> ◈
</p>
