<div align="right">
  <a href="./README.md"><img src="./assets/btn-pt-inactive.svg" height="32" alt="PT · Português" /></a>
  <a href="./README.en.md"><img src="./assets/btn-en.svg" height="32" alt="EN · English" /></a>
  <a href="./README.static.md"><img src="./assets/btn-static-active.svg" height="32" alt="Sem movimento" /></a>
</div>

<p align="center">
  <img src="./assets/hero-banner-static.svg" width="100%" alt="Daniel Widal - Cyber Threat Intelligence & Threat Hunting" />
</p>

## 🛡️ Daniel Widal

**Analista de Segurança da Informação · Cyber Threat Intelligence (CTI) · Threat Hunting · Detection Engineering**

Atuo na coleta, enriquecimento e operacionalização de dados de ameaças — correlacionando **IOCs, TTPs e comportamentos adversários** para antecipar vetores de ataque, criar regras de detecção proativas e orientar a resposta a incidentes.

Minha abordagem conecta **análise técnica de artefatos** (tráfego PCAP, malwares e logs de aplicação/rede) com **mapeamento via MITRE ATT&CK**, transformando telemetria bruta em inteligência acionável para defesas em **Cloudflare WAF, SIEM (Wazuh) e ambientes de observabilidade (Grafana)**. No laboratório de pesquisa, mantenho um **honeypot com motor próprio de detecção em Python** como fonte primária de telemetria para threat hunting e reconstrução de Kill Chain.

<p align="left">
  <a href="#-ciclo-de-inteligência-aplicada"><img src="./assets/nav-ciclo.svg" height="34" alt="Ciclo CTI" /></a>
  <a href="#-threat-intelligence--malwarenetwork-analysis"><img src="./assets/nav-casos.svg" height="34" alt="Investigações" /></a>
  <a href="#-security-stack--tools"><img src="./assets/nav-stack.svg" height="34" alt="Stack & Tools" /></a>
  <a href="#-conecte-se-comigo"><img src="./assets/nav-contato.svg" height="34" alt="Contato" /></a>
  <a href="https://pendragon711.github.io"><img src="https://img.shields.io/badge/PORTFÓLIO_WEB-pendragon711.github.io-D4AF37?style=for-the-badge&labelColor=0a0b0e" alt="Portfólio Web" /></a>
</p>

---

## 🎯 Ciclo de Inteligência Aplicada

Como transformo telemetria e artefatos maliciosos em defesa proativa:

| Fase | Execução Técnica |
| :--- | :--- |
| **01 · Coleta & Telemetria** | Captura de tráfego malicioso via honeypots, logs de WAF/SIEM, feeds OSINT e amostras de rede (PCAP). |
| **02 · Enriquecimento** | Extração, validação e higienização (*defang*) de IOCs (hashes, domínios, IPs, C2) via VirusTotal, ANY.RUN e análise estática/dinâmica. |
| **03 · Análise de TTPs** | Reconstrução da Kill Chain, identificação de abuso de binários nativos (*LOLBins*) e mapeamento no **MITRE ATT&CK**. |
| **04 · Operacionalização** | Conversão da inteligência em regras de bloqueio e detecção (WAF, SIEM/Wazuh, YARA/Sigma) e hunts proativos. |

---

## 🔬 Threat Intelligence & Malware/Network Analysis

Investigações técnicas focadas em **extração de payloads, análise comportamental de ameaças, mapeamento de TTPs e geração de IOCs acionáveis**.

### 🕸️ Dossiê 01: DanaBot — Network Traffic & Kill Chain

> **Investigação de tráfego de rede (PCAP) de uma infecção multi-estágio do malware DanaBot, isolando payloads disfarçados, infraestrutura de C2 e TTPs do adversário.**

`Wireshark` `Network Analysis` `VirusTotal` `ANY.RUN` `PowerShell` `MITRE ATT&CK` `OSINT`

- **Deep Packet Inspection:** Identificação da origem do ataque e do vetor inicial via requisições HTTP GET.
- **Payload Extraction:** Reconstrução de fluxos HTTP para isolar artefatos maliciosos (`.js` disfarçado de `.php`) e payloads secundários (`.dll`).
- **Behavioral & LOLBins Mapping:** Análise da árvore de execução em sandbox, identificando o abuso de `wscript.exe` para execução furtiva.
- **IOC Reporting:** Geração de assinaturas (SHA-256/MD5) e documentação de indicadores (*defanged*) para alimentação de regras defensivas.

🔗 **[Acessar Dossiê Completo →](https://github.com/Pendragon711/danabot-dfir-investigation)**

---

### 🔎 Dossiê 02: XLMRat — Delivery Chain & Malware Triage

> **Análise da cadeia de entrega e execução do AsyncRAT (cenário XLMRat), correlacionando artefatos de rede e sistema para extração de indicadores e mapeamento MITRE ATT&CK.**

`Wireshark` `CyberChef` `VirusTotal` `Python` `MITRE ATT&CK`

- **Traffic & Artifact Analysis:** Identificação do download inicial via HTTP contendo um arquivo `.jpg` com cabeçalho adulterado.
- **Deobfuscation:** Desofuscação de payload e extração de metadados/timestamp de compilação do executável malicioso.
- **Defense Evasion Tracking:** Mapeamento do abuso do LOLBin `RegSvcs.exe` para injeção e evasão de defesa.
- **MITRE ATT&CK Mapping:** Classificação completa das técnicas observadas (`T1105`, `T1059.001`, `T1218.009`, `T1620`) e entrega de relatório de IOCs.

🔗 **[Acessar Dossiê Completo →](https://github.com/Pendragon711/xlmrat-dfir-investigation)**

---

## ⚔️ Attack Surface & Recon (Visão Ofensiva)

Mapear a superfície de ataque exposta é essencial para antecipar vetores de exploração e priorizar defesas.

- 👁️ **[ODIN](https://github.com/Pendragon711/odin-recon)** — Pipeline automatizado de reconhecimento e Attack Surface Management (ASM) em Go (`Subfinder`, `Naabu`, `HTTPX`) para descoberta de ativos e detecção de WAF.

---

## 🧰 Security Stack & Tools

### 🎯 Threat Intelligence & Analysis
<p align="left">
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-0a0b0e?style=for-the-badge&logo=mitre&logoColor=D4AF37" alt="MITRE ATT&CK" />
  <img src="https://img.shields.io/badge/Wireshark-0a0b0e?style=for-the-badge&logo=wireshark&logoColor=D4AF37" alt="Wireshark" />
  <img src="https://img.shields.io/badge/CyberChef-0a0b0e?style=for-the-badge&logo=cyberchef&logoColor=D4AF37" alt="CyberChef" />
  <img src="https://img.shields.io/badge/VirusTotal-0a0b0e?style=for-the-badge&logo=virustotal&logoColor=D4AF37" alt="VirusTotal" />
</p>

**Foco:** IOC Enrichment • TTP Mapping • PCAP & Payload Analysis • Malware Triage • Attack Surface Recon

### 🛡️ Detection Engineering, SIEM & AppSec
<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-0a0b0e?style=for-the-badge&logo=wazuh&logoColor=D4AF37" alt="Wazuh" />
  <img src="https://img.shields.io/badge/Cloudflare%20WAF-0a0b0e?style=for-the-badge&logo=cloudflare&logoColor=D4AF37" alt="Cloudflare WAF" />
  <img src="https://img.shields.io/badge/Grafana-0a0b0e?style=for-the-badge&logo=grafana&logoColor=D4AF37" alt="Grafana" />
  <img src="https://img.shields.io/badge/SIEM-0a0b0e?style=for-the-badge&logo=elasticstack&logoColor=D4AF37" alt="SIEM" />
</p>

**Foco:** Threat Hunting • Log Correlation • Custom Detection Rules • WAF Mitigation • Traffic Anomaly Analysis

### ⚙️ Automação & Infraestrutura
<p align="left">
  <img src="https://img.shields.io/badge/Python-0a0b0e?style=for-the-badge&logo=python&logoColor=D4AF37" alt="Python" />
  <img src="https://img.shields.io/badge/Go-0a0b0e?style=for-the-badge&logo=go&logoColor=D4AF37" alt="Go" />
  <img src="https://img.shields.io/badge/Linux-0a0b0e?style=for-the-badge&logo=linux&logoColor=D4AF37" alt="Linux" />
  <img src="https://img.shields.io/badge/Bash-0a0b0e?style=for-the-badge&logo=gnubash&logoColor=D4AF37" alt="Bash" />
</p>

---

## 🎓 Formação & Certificações

- 🎓 **Graduação em Cibersegurança** — UniCesumar *(Em andamento)*
- 📜 **Google Cybersecurity Professional Certificate** — Coursera
- 📜 **Cisco Junior Cybersecurity Analyst** — Cisco Networking Academy
- 📜 **Analista de SOC na Era da IA** — IBSEC
- 📜 **Fundamentos de SOC** — Be Safe Inc.
- 📜 **AWS Cloud Practitioner Essentials** — Amazon Web Services
- 📜 **Nano Course Cybersecurity** — FIAP

---

## 📊 Telemetria & GitHub Stats

<div align="center">
  <img height="175em" src="https://github-readme-streak-stats.herokuapp.com/?user=Pendragon711&background=0a0b0e&border=3d3112&stroke=3d3112&ring=D4AF37&fire=F5D77F&currStreakNum=F9FAFB&sideNums=F9FAFB&currStreakLabel=D4AF37&sideLabels=9CA3AF&dates=6B7280"/>
  <img height="175em" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Pendragon711&theme=github_dark"/>
</div>

---

## 📫 Conecte-se comigo

<div align="center">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/Portfólio-0a0b0e?style=for-the-badge&logo=googlechrome&logoColor=D4AF37" alt="Portfólio"/>
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
