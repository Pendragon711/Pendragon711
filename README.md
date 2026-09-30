# 🛡️ Daniel Widal — Cybersecurity

### Pentest Jr. | Offensive Security | Web Security | AppSec | Bug Bounty

<p align="left">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/🌐_Portfólio-pendragon711.github.io-00ff88?style=for-the-badge&labelColor=05070a" alt="Portfólio" />
  </a>
</p>

Profissional de **Cibersegurança** direcionando a carreira para **Offensive Security, Pentest e Web Application Security**, com experiência profissional em SOC, redes e troubleshooting.

Tenho prática em **reconhecimento, enumeração, análise de superfície de ataque e segurança de aplicações web**, utilizando ferramentas como **Burp Suite, Nmap, Python, Playwright, Kali Linux e Metasploit** em ambientes autorizados e controlados.

Também atuo com **Bug Bounty no HackerOne**, realizando pesquisa e investigação de vulnerabilidades em programas autorizados, utilizando referências como **OWASP Top 10, CWE e CVSS**.

Meu background em **SOC e Blue Team** complementa a atuação ofensiva, permitindo analisar também os eventos e evidências gerados durante atividades de segurança.

🎓 **Cibersegurança — UniCesumar | Em andamento**

---

# ⚔️ Offensive Security / Pentest

Projetos e estudos voltados para **Web Security, Pentest, Reconnaissance, Vulnerability Research e Security Testing**.

## 👻 GHOST — Web Pentest Framework

**Framework em Python para automação e simulação de testes de segurança em aplicações web em ambiente controlado.**

**Tecnologias:**

`Python` `Playwright` `Requests` `Web Security` `CWE` `CVSS`

### O que foi desenvolvido

* Crawler baseado em **Playwright** para mapeamento de aplicações web dinâmicas e SPAs.
* Automação de requisições e cenários de teste.
* Simulação controlada de vulnerabilidades como **XSS, SQL Injection, LFI/RFI, SSRF, SSTI, NoSQL Injection, Command Injection e IDOR**.
* Motor de classificação de achados utilizando **CWE**.
* Avaliação de severidade utilizando **CVSS v3.1**.
* Geração e documentação de evidências técnicas.
* Integração dos testes com laboratório de **Wazuh** para análise dos eventos gerados.

🔗 **[Ver projeto →](https://github.com/Pendragon711/GHOST---Web-Pentest-Framework)**

---

## 🔎 Bug Bounty & Vulnerability Research

Prática contínua de **Bug Bounty no HackerOne**, com foco em aplicações web e pesquisa de vulnerabilidades em programas autorizados.

### Prática

* Reconhecimento e enumeração de superfície de ataque.
* Identificação e análise de endpoints e funcionalidades.
* Testes manuais de segurança em aplicações web.
* Investigação de comportamentos anômalos.
* Validação de hipóteses e evidências.
* Classificação de vulnerabilidades utilizando **CWE**.
* Análise de impacto e severidade utilizando **CVSS**.
* Documentação técnica de achados.

🔗 **[HackerOne →](https://hackerone.com/)**

---

## 🧪 Pentest & Exploitation Lab

**Laboratório isolado para prática de reconhecimento, exploração e análise de vulnerabilidades.**

**Tecnologias:**

`Kali Linux` `Metasploit` `Metasploitable 2` `Nmap` `Burp Suite` `VirtualBox`

### Prática

* Reconhecimento e enumeração de serviços.
* Scanning de portas e serviços.
* Análise de aplicações e serviços vulneráveis.
* Exploração controlada utilizando **Metasploit**.
* Testes de segurança em aplicações web.
* Análise dos eventos gerados durante os testes.
* Documentação dos procedimentos e evidências.

---

# 🛡️ Blue Team / SOC

Projetos voltados para **Security Monitoring, SIEM, Threat Detection, Detection Engineering e Incident Investigation**.

## 🍯 SSH Honeypot Lab — Detection Engine & Live Dashboard

**Honeypot SSH/Web desenvolvido em Python com motor de detecção próprio e dashboard em tempo real.**

**Tecnologias:**

`Python` `Flask` `Socket` `HTTP` `JSONL` `Linux` `VirtualBox`

### O que foi desenvolvido

* Honeypot SSH e Web construído do zero.
* Motor de detecção baseado em **janelas deslizantes**.
* Quatro regras independentes para identificação de comportamentos suspeitos.
* Deduplicação baseada em baseline para redução de **alert fatigue**.
* Persistência estruturada de eventos em **JSONL**.
* Dashboard em Flask com atualização em tempo real através de API JSON.
* Simulador de ataques para geração controlada de eventos.
* Laboratório isolado em rede **Host-Only**.

### Regras de detecção

| Regra                  | Severidade | Gatilho                            |
| ---------------------- | ---------- | ---------------------------------- |
| `connection_burst`     | MEDIUM     | 5+ conexões do mesmo IP em 60s     |
| `repeated_ssh_banner`  | LOW        | 3+ banners SSH do mesmo IP em 60s  |
| `suspicious_payload`   | HIGH       | Payload contendo padrões suspeitos |
| `http_suspicious_path` | MEDIUM     | Requisições para paths sensíveis   |

🔗 **[Ver projeto →](https://github.com/Pendragon711/ssh-honeypot-lab)**

---

## 🛡️ SOC Lab — Wazuh SIEM

**Laboratório de SOC para simulação de ataques, coleta de eventos, detecção e investigação de incidentes.**

**Tecnologias:**

`Wazuh` `SIEM` `Kali Linux` `Metasploitable 2` `VirtualBox` `MITRE ATT&CK`

### O que foi desenvolvido

* Ambiente virtual isolado para simulação de ataques.
* Coleta e análise de logs de segurança.
* Criação e ajuste de regras de detecção.
* Correlação de eventos.
* Investigação de comportamentos suspeitos.
* Mapeamento de eventos para **MITRE ATT&CK**.
* Simulação de **brute force SSH**.
* Validação da detecção do cenário em aproximadamente **10 segundos** no laboratório.

🔗 **[Ver projeto →](https://github.com/Pendragon711/soc-lab-wazuh)**

---

# ☁️ Cloud & Infrastructure

## AWS Security Lab — EC2, S3 & VPC

**Laboratório prático de infraestrutura AWS com foco em fundamentos de cloud e segurança.**

**Tecnologias:**

`AWS` `EC2` `S3` `VPC` `Security Groups` `EBS` `Git`

### Conceitos praticados

* Provisionamento de instâncias EC2.
* Configuração de VPC.
* Controle de acesso com Security Groups.
* Armazenamento utilizando S3.
* Volumes EBS.
* Automação inicial com User Data.
* Documentação da infraestrutura.

🔗 **[Ver projeto →](https://github.com/Pendragon711/projeto-aws-s3-ec2)**

---

# 🧰 Security Stack

### 🔴 Offensive Security

<p align="left">
  <img src="https://img.shields.io/badge/Burp%20Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white" alt="Burp Suite" />
  <img src="https://img.shields.io/badge/Nmap-4682B4?style=for-the-badge" alt="Nmap" />
  <img src="https://img.shields.io/badge/Metasploit-2596CD?style=for-the-badge" alt="Metasploit" />
  <img src="https://img.shields.io/badge/Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" alt="Kali Linux" />
  <img src="https://img.shields.io/badge/OWASP-000000?style=for-the-badge&logo=owasp&logoColor=white" alt="OWASP" />
</p>

**Web Security:** OWASP Top 10 • XSS • SQL Injection • SSRF • IDOR • LFI/RFI • SSTI • NoSQL Injection • Command Injection

**Standards:** CWE • CVSS v3.1

---

### 🔵 Blue Team / SOC

<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-3C8CBE?style=for-the-badge&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/SIEM-4B0082?style=for-the-badge" alt="SIEM" />
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-000000?style=for-the-badge&logo=mitre&logoColor=white" alt="MITRE ATT&CK" />
</p>

**Foco:** Security Monitoring • Log Analysis • Threat Detection • Alert Investigation • Event Correlation • Detection Engineering • Incident Investigation

---

### 🌐 Networks & Systems

<p align="left">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
  <img src="https://img.shields.io/badge/TCP%2FIP-005571?style=for-the-badge" alt="TCP/IP" />
  <img src="https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white" alt="VirtualBox" />
</p>

**Foco:** TCP/IP • Network Analysis • Traffic Analysis • Network Troubleshooting • Linux • Virtualization

---

### 🐍 Development & Automation

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
</p>

---

# 🎯 Áreas de Interesse

### 🔴 Offensive Security

`Pentest` `Web Security` `AppSec` `Bug Bounty` `Vulnerability Research` `Reconnaissance` `Security Testing`

### 🔵 Defensive Security

`SOC` `SIEM` `Threat Detection` `Detection Engineering` `Log Analysis` `Incident Response` `MITRE ATT&CK`

### ☁️ Infrastructure

`Network Security` `Cloud Security` `Linux` `AWS` `Security Automation`

---

# 🎓 Formação & Certificações

🎓 **Graduação em Cibersegurança**
UniCesumar — Em andamento

📜 **Analista de SOC na Era da IA** — IBSEC

📜 **Google Cybersecurity Professional Certificate** — Coursera

📜 **Cisco Junior Cybersecurity Analyst** — Cisco Networking Academy

📜 **Nano Course Cybersecurity** — FIAP

📜 **Fundamentos de SOC N1** — Be Safe Inc.

📜 **AWS Cloud Practitioner Essentials** — Amazon Web Services

---

# 📊 GitHub Stats

<div align="center">

<img height="180em" src="https://github-readme-streak-stats.herokuapp.com/?user=Pendragon711&theme=dark&hide_border=true"/>

<img height="180em" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Pendragon711&theme=dark"/>

</div>

---

# 📫 Conecte-se comigo

<div align="center">

<a href="https://pendragon711.github.io">
  <img src="https://img.shields.io/badge/Portfólio-00ff88?style=for-the-badge&logo=googlechrome&logoColor=black" alt="Portfólio"/>
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
  ⚔️ <strong>Building practical offensive security skills through Pentest, Web Security, Bug Bounty and security research.</strong>
</p>
