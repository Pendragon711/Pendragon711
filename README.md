# 🛡️ Daniel Widal — Cyber Threat Intelligence & Threat Hunting

### Analista de Segurança da Informação | Cyber Threat Intelligence (CTI) | Threat Hunting | Detection Engineering

<p align="left">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/🌐_Portfólio-pendragon711.github.io-6cc7ff?style=for-the-badge&labelColor=0a1016" alt="Portfólio" />
  </a>
</p>

Profissional de **Segurança da Informação** com atuação focada em **Cyber Threat Intelligence (CTI)**, **Threat Hunting** e **Detection Engineering**. Atuo na coleta, enriquecimento e operacionalização de dados de ameaças — correlacionando **IOCs, TTPs e comportamentos adversários** para antecipar vetores de ataque, criar regras de detecção proativas e orientar a resposta a incidentes.

Minha abordagem conecta **análise técnica de artefatos** (tráfego PCAP, malwares e logs de aplicação/rede) com **mapeamento via MITRE ATT&CK**, transformando telemetria bruta em inteligência acionável para defesas em **Cloudflare WAF, SIEM (Wazuh) e ambientes de observabilidade (Grafana)**.

No meu laboratório de pesquisa, mantenho um **honeypot com motor próprio de detecção em Python** como fonte primária de telemetria para threat hunting, gerencio um ambiente **Wazuh** para correlação de eventos e documento análises de campanhas maliciosas com foco em extração de IOCs e reconstrução de Kill Chain.

🎓 **Cibersegurança — UniCesumar | Em andamento**

---

# 🎯 Ciclo de Inteligência Aplicada (Intelligence-Driven Defense)

Como transformo telemetria e artefatos maliciosos em defesa proativa:

| Fase | Execução Técnica |
| :--- | :--- |
| **Coleta & Telemetria** | Captura de tráfego malicioso via honeypots, logs de WAF/SIEM, feeds OSINT e amostras de rede (PCAP). |
| **Enriquecimento** | Extração, validação e higienização (*defang*) de IOCs (hashes, domínios, IPs, C2) via VirusTotal, ANY.RUN e análise estática/dinâmica. |
| **Análise de TTPs** | Reconstrução da Kill Chain, identificação de abuso de binários nativos (*LOLBins*) e mapeamento no **MITRE ATT&CK**. |
| **Operacionalização** | Conversão da inteligência em regras de bloqueio e detecção (WAF, SIEM/Wazuh, YARA/Sigma) e hunts proativos. |

---

# 🔬 Threat Intelligence & Malware/Network Analysis

Investigações técnicas focadas em **extração de payloads, análise comportamental de ameaças, mapeamento de TTPs e geração de IOCs acionáveis**.

## 🕸️ Threat Analysis: DanaBot — Network Traffic & Kill Chain

**Investigação de tráfego de rede (PCAP) de uma infecção multi-estágio do malware DanaBot, isolando payloads disfarçados, infraestrutura de C2 e TTPs do adversário.**

`Wireshark` `Network Analysis` `VirusTotal` `ANY.RUN` `PowerShell` `MITRE ATT&CK` `OSINT`

* **Deep Packet Inspection:** Identificação da origem do ataque e do vetor inicial via requisições HTTP GET.
* **Payload Extraction:** Reconstrução de fluxos HTTP para isolar artefatos maliciosos (`.js` disfarçado de `.php`) e payloads secundários (`.dll`).
* **Behavioral & LOLBins Mapping:** Análise da árvore de execução em sandbox, identificando o abuso de `wscript.exe` para execução furtiva.
* **IOC Reporting:** Geração de assinaturas (SHA-256/MD5) e documentação de indicadores (*defanged*) para alimentação de regras defensivas.

🔗 **[Ver investigação →](https://github.com/Pendragon711/danabot-dfir-investigation)**

---

## 🔎 Threat Analysis: XLMRat — Delivery Chain & Malware Triage

**Análise da cadeia de entrega e execução do AsyncRAT (cenário XLMRat), correlacionando artefatos de rede e sistema para extração de indicadores e mapeamento MITRE ATT&CK.**

`Wireshark` `CyberChef` `VirusTotal` `Python` `MITRE ATT&CK`

* **Traffic & Artifact Analysis:** Identificação do download inicial via HTTP contendo um arquivo `.jpg` com cabeçalho adulterado.
* **Deobfuscation:** Desofuscação de payload e extração de metadados/timestamp de compilação do executável malicioso.
* **Defense Evasion Tracking:** Mapeamento do abuso do LOLBin `RegSvcs.exe` para injeção e evasão de defesa.
* **MITRE ATT&CK Mapping:** Classificação completa das técnicas observadas (`T1105`, `T1059.001`, `T1218.009`, `T1620`) e entrega de relatório de IOCs.

🔗 **[Ver investigação →](https://github.com/Pendragon711/xlmrat-dfir-investigation)**

---

# ⚔️ Attack Surface & Recon (Visão Ofensiva)

Mapear a superfície de ataque exposta é essencial para antecipar vetores de exploração e priorizar defesas.

* 👁️ **[ODIN](https://github.com/Pendragon711/odin-recon)** — Pipeline automatizado de reconhecimento e Attack Surface Management (ASM) em Go (`Subfinder`, `Naabu`, `HTTPX`) para descoberta de ativos e detecção de WAF.

---

# 🧰 Security Stack & Tools

### 🎯 Threat Intelligence & Analysis
<p align="left">
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-000000?style=for-the-badge&logo=mitre&logoColor=white" alt="MITRE ATT&CK" />
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
  <img src="https://img.shields.io/badge/CyberChef-C8391B?style=for-the-badge&logo=cyberchef&logoColor=white" alt="CyberChef" />
  <img src="https://img.shields.io/badge/VirusTotal-394EFF?style=for-the-badge&logo=virustotal&logoColor=white" alt="VirusTotal" />
</p>

**Foco:** IOC Enrichment • TTP Mapping • PCAP & Payload Analysis • Malware Triage • Attack Surface Recon

---

### 🛡️ Detection Engineering, SIEM & AppSec
<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-3C8CBE?style=for-the-badge&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/Cloudflare%20WAF-F38020?style=for-the-badge&logo=cloudflare&logoColor=white" alt="Cloudflare WAF" />
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" alt="Grafana" />
  <img src="https://img.shields.io/badge/SIEM-4B0082?style=for-the-badge&logo=elasticstack&logoColor=white" alt="SIEM" />
</p>

**Foco:** Threat Hunting • Log Correlation • Custom Detection Rules • WAF Mitigation • Traffic Anomaly Analysis

---

### ⚙️ Automação & Infraestrutura
<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash" />
</p>

---

# 🎓 Formação & Certificações

* 🎓 **Graduação em Cibersegurança** — UniCesumar *(Em andamento)*
* 📜 **Google Cybersecurity Professional Certificate** — Coursera
* 📜 **Cisco Junior Cybersecurity Analyst** — Cisco Networking Academy
* 📜 **Analista de SOC na Era da IA** — IBSEC
* 📜 **Fundamentos de SOC** — Be Safe Inc.
* 📜 **AWS Cloud Practitioner Essentials** — Amazon Web Services
* 📜 **Nano Course Cybersecurity** — FIAP

---

# 📊 GitHub Stats

<div align="center">
  <img height="175em" src="https://github-readme-streak-stats.herokuapp.com/?user=Pendragon711&theme=dark&hide_border=true"/>
  <img height="175em" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Pendragon711&theme=dark"/>
</div>

---

# 📫 Conecte-se comigo

<div align="center">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/Portfólio-6cc7ff?style=for-the-badge&logo=googlechrome&logoColor=black" alt="Portfólio"/>
  </a>
  <a href="https://www.linkedin.com/in/danielwidal">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:daniels2live666@gmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
</div>

---

<p align="center">
  🛡️ <strong>"Turn raw threat data into actionable defense."</strong>
</p>
