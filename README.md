# 🛡️ Daniel Widal — Cybersecurity

### SOC N1 | Blue Team | SIEM | Threat Detection | Incident Response

<p align="left">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/🌐_Portfólio-pendragon711.github.io-00ff88?style=for-the-badge&labelColor=05070a" alt="Portfólio" />
  </a>
</p>

Profissional de **Cibersegurança** com foco em **SOC N1, Blue Team, SIEM, Security Monitoring, análise de logs, detecção de ameaças e investigação de incidentes**.

Possuo experiência prática em atividades de **SOC**, incluindo monitoramento e triagem de eventos de segurança, análise preliminar de alertas, classificação e escalonamento de incidentes, investigação inicial de eventos relacionados a redes, endpoints e acessos, além de apoio à documentação de procedimentos e playbooks.

Também desenvolvo laboratórios e ferramentas próprias para simular ataques em ambientes controlados, gerar eventos de segurança e validar mecanismos de detecção.

Minha stack combina **Wazuh, Linux, Python, Bash, MITRE ATT&CK, redes, AWS e ferramentas de segurança ofensiva utilizadas em ambientes controlados**.

> 🎯 **Objetivo:** atuar como **SOC Analyst N1 / Analista de Cibersegurança Jr.**, contribuindo com monitoramento, análise de alertas, detecção de ameaças, investigação e resposta a incidentes.

---

## 🌐 Portfólio

> 🔗 **[pendragon711.github.io](https://pendragon711.github.io)**
>
> Site pessoal com labs de cybersecurity, estudos de caso e documentação técnica.

---

# 🛡️ Cybersecurity Stack

### 🔵 Blue Team / SOC

<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-3C8CBE?style=for-the-badge&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/SIEM-4B0082?style=for-the-badge" alt="SIEM" />
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-000000?style=for-the-badge&logo=mitre&logoColor=white" alt="MITRE ATT&CK" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash" />
</p>

**Foco:** Security Monitoring • Log Analysis • Threat Detection • Alert Investigation • Event Correlation • Incident Analysis • Detection Engineering • Incident Response

---

### 🌐 Network Security

<p align="left">
  <img src="https://img.shields.io/badge/Nmap-4682B4?style=for-the-badge" alt="Nmap" />
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
  <img src="https://img.shields.io/badge/TCP%2FIP-005571?style=for-the-badge" alt="TCP/IP" />
</p>

**Foco:** TCP/IP • Network Analysis • Traffic Analysis • Network Troubleshooting • Network Security

---

### 🔴 Security Testing

<p align="left">
  <img src="https://img.shields.io/badge/Burp%20Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white" alt="Burp Suite" />
  <img src="https://img.shields.io/badge/Metasploit-2596CD?style=for-the-badge" alt="Metasploit" />
  <img src="https://img.shields.io/badge/Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" alt="Kali Linux" />
  <img src="https://img.shields.io/badge/OWASP-000000?style=for-the-badge&logo=owasp&logoColor=white" alt="OWASP" />
</p>

Uso essas ferramentas em **ambientes controlados**, principalmente para simular técnicas de ataque, gerar eventos e validar mecanismos de detecção.

---

### ☁️ Cloud & Infrastructure

<p align="left">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
</p>

**AWS:** EC2 • S3 • VPC • Security Groups • EBS

---

# 🚨 Cybersecurity Projects

## 🍯 SSH Honeypot Lab — Detection Engine & Live Dashboard

**Laboratório de honeypot SSH + Web com motor de detecção próprio, deduplicação por baseline e dashboard em tempo real.**

**Tecnologias:**

`Python` `Flask` `Socket` `HTTP Server` `JSONL` `VirtualBox` `Linux` `Blue Team` `Detection Engineering`

### O que foi realizado

* Construção de honeypot SSH e Web do zero, sem dependências externas.
* Motor de detecção próprio com **4 regras independentes** baseadas em janelas deslizantes.
* **Deduplicação por baseline** para reduzir alert fatigue.
* Persistência de eventos em **JSONL estruturado**.
* Dashboard Flask atualizado em tempo real via API JSON.
* Simulador de ataques controlado para geração de eventos.
* Laboratório isolado em rede **host-only**.

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

**Laboratório de SOC / Blue Team para monitoramento, detecção e investigação de eventos de segurança.**

**Tecnologias:**

`Wazuh` `SIEM` `Linux` `Kali Linux` `Metasploitable 2` `VirtualBox` `MITRE ATT&CK`

### O que foi realizado

* Construção de ambiente controlado para simulação de ataques.
* Coleta e análise de logs de segurança.
* Criação e ajuste de regras de detecção.
* Correlação de eventos.
* Investigação de comportamentos suspeitos.
* Mapeamento de eventos para **MITRE ATT&CK**.
* Simulação de **brute force SSH**.
* Detecção do cenário de brute force em aproximadamente **10 segundos** no laboratório.

🔗 **[Ver projeto →](https://github.com/Pendragon711/soc-lab-wazuh)**

---

## 👻 GHOST — Security Testing Framework

**Framework modular desenvolvido em Python para simular técnicas de ataque em ambientes controlados e gerar eventos utilizados na validação de mecanismos de detecção.**

**Tecnologias:**

`Python` `Security Testing` `Web Security` `Nmap` `Burp Suite` `Metasploit` `CVSS` `CWE`

### Objetivos

* Simular técnicas de reconhecimento.
* Executar cenários de scanning.
* Simular técnicas de exploração em ambiente controlado.
* Gerar eventos para investigação no SOC Lab.
* Validar e ajustar mecanismos de detecção.
* Classificar achados utilizando **CVSS e CWE**.

🔗 **[Ver projeto →](https://github.com/Pendragon711/GHOST---Web-Pentest-Framework)**

---

## ☁️ AWS Security Lab — EC2, S3 & VPC

**Projeto prático de infraestrutura Cloud com foco em fundamentos de segurança e configuração de recursos AWS.**

**Tecnologias:**

`AWS` `EC2` `S3` `VPC` `Security Groups` `EBS` `User Data` `Git`

### Conceitos praticados

* Provisionamento de instâncias EC2.
* Configuração de VPC.
* Controle de acesso através de Security Groups.
* Armazenamento utilizando S3.
* Utilização de volumes EBS.
* Automação inicial utilizando User Data.
* Documentação da infraestrutura.

🔗 **[Ver projeto →](https://github.com/Pendragon711/projeto-aws-s3-ec2)**

---

# 🔎 Áreas de Interesse

```text
SOC N1
Blue Team
Security Operations
SIEM
Security Monitoring
Threat Detection
Log Analysis
Alert Investigation
Incident Investigation
Incident Response
MITRE ATT&CK
Network Security
Cloud Security
Detection Engineering
Security Automation
```

---

# 🧰 Ferramentas

| Área                  | Tecnologias                                  |
| --------------------- | -------------------------------------------- |
| **SIEM / SOC**        | Wazuh                                        |
| **Blue Team**         | Log Analysis, Threat Detection, MITRE ATT&CK |
| **Security Testing**  | Burp Suite, Nmap, Metasploit, OWASP          |
| **Networks**          | TCP/IP, Wireshark, Nmap                      |
| **Operating Systems** | Linux, Kali Linux                            |
| **Programming**       | Python, Bash                                 |
| **Cloud**             | AWS, EC2, S3, VPC, Security Groups           |
| **Infrastructure**    | Docker, VirtualBox                           |
| **Version Control**   | Git, GitHub                                  |

---

# 🎓 Formação & Certificações

🎓 **Graduação em Cibersegurança**
UniCesumar — Em andamento

📜 **Google Cybersecurity Professional Certificate**

📜 **Cisco — Junior Cybersecurity Analyst**

📜 **AWS Cloud Practitioner Essentials**

📜 **FIAP — Nano Course Cybersecurity**

📜 **Be Safe.inc — SOC N1**

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
  🛡️ <strong>Building practical cybersecurity skills through SOC operations, detection engineering and security automation.</strong>
</p>
