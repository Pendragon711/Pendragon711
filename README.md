# 🛡️ Daniel Widal — SOC & DFIR

### Analista de SOC N1 | DFIR | Resposta a Incidentes | Detection Engineering

<p align="left">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/🌐_Portfólio-pendragon711.github.io-6cc7ff?style=for-the-badge&labelColor=0a1016" alt="Portfólio" />
  </a>
</p>

Profissional de **Cibersegurança** direcionando a carreira para **SOC (Security Operations Center), DFIR e Resposta a Incidentes**, com experiência em triagem de alertas em SIEM e uma base de suporte técnico em redes.

Experiencia pratica em estágio de Segurança da Informação, fiz a **triagem e a investigação de alertas em SIEM** (malware, phishing e acessos suspeitos), a **análise de logs e evidências**, o apoio a firewalls e ferramentas de detecção e a criação de **playbooks de resposta a incidentes**, relatórios e dashboards.

Fora do trabalho, mantenho laboratórios próprios de detecção com **Wazuh** e um **honeypot** com motor de detecção em Python. Minha base em **pentest** me ajuda a pensar como o atacante e a escrever detecções melhores.

🎓 **Cibersegurança — UniCesumar | Em andamento**

---

# 🔎 Como eu trabalho

Do alerta à decisão, com tudo documentado.

| Etapa | O que eu faço |
| ----- | ------------- |
| **Identificar** | Entender o que foi afetado e qual o escopo |
| **Preservar** | Evitar a perda de evidências antes de qualquer limpeza |
| **Coletar** | Capturar logs e arquivos registrando quem, quando e como |
| **Analisar** | Correlacionar as fontes e montar a linha do tempo |
| **Reportar** | Fatos, evidências e recomendações em linguagem clara |

### Princípios de coleta de evidências

*   Trabalhar sempre em cópia, nunca no original.
*   Calcular o hash antes e depois da coleta.
*   Coletar do mais volátil ao menos volátil.
*   Registrar quem coletou, quando (UTC) e como.

<details>
<summary><strong>📋 Meus playbooks de triagem (clique para abrir)</strong></summary>

<br>

**Phishing**

1. Identificar o que chegou: remetente, assunto, anexos e links.
2. Analisar os cabeçalhos: SPF, DKIM, DMARC e o caminho de entrega.
3. Abrir links e anexos só em ambiente isolado.
4. Medir o alcance: quem mais recebeu, abriu e clicou.
5. Conter: bloquear remetente e URL, remover o e-mail e redefinir senhas de quem digitou credenciais.
6. Registrar o caso com as evidências e os indicadores.

*Escalo quando:* houve credenciais digitadas, anexo executado ou o alvo está na diretoria, financeiro ou TI.

**Acesso suspeito**

1. Confirmar o que disparou: conta, horário, origem e método de autenticação.
2. Comparar com o histórico do usuário: local, dispositivo e horário habituais.
3. Procurar falhas seguidas de sucesso (Windows: evento 4625 seguido de 4624).
4. Validar com o usuário ou o gestor por um canal confiável.
5. Se for suspeito: encerrar sessões, redefinir credenciais, revisar o MFA e as ações feitas na sessão.
6. Registrar o caso com a linha do tempo dos acessos.

*Escalo quando:* há login bem-sucedido que o usuário não reconhece, conta privilegiada ou sinal de movimentação lateral.

**Malware**

1. Ler o alerta: arquivo, caminho, hash e a ação tomada.
2. Consultar hash e URL em bases de reputação.
3. Reconstruir a árvore de processos (criação de processo, evento 4688).
4. Verificar conexões de saída e persistência.
5. Buscar o mesmo hash em outras estações.
6. Se houve execução: isolar a estação e preservar as evidências antes de limpar.

*Escalo quando:* a execução foi confirmada, há persistência ou comunicação com IP externo suspeito.

</details>

---

# 🛡️ SOC & Detection Engineering

Projetos voltados para **Security Monitoring, SIEM, Threat Detection, Detection Engineering e Incident Investigation**.

## 🛡️ SOC Lab — Wazuh SIEM

**Laboratório de SOC para simulação de ataques, coleta de eventos, detecção e investigação de incidentes.**

**Tecnologias:**

`Wazuh` `SIEM` `Kali Linux` `Metasploitable 2` `VirtualBox` `MITRE ATT&CK`

### O que foi desenvolvido

*   Ambiente virtual isolado para simulação de ataques.
*   Coleta e análise de logs de segurança.
*   Criação e ajuste de regras de detecção.
*   Correlação de eventos.
*   Investigação de comportamentos suspeitos.
*   Mapeamento de eventos para **MITRE ATT&CK**.
*   Simulação de **brute force SSH**.
*   Validação da detecção do cenário em aproximadamente **10 segundos** no laboratório.

🔗 **[Ver projeto →](https://github.com/Pendragon711/soc-lab-wazuh)**

---

## 🍯 SSH Honeypot Lab — Detection Engine & Live Dashboard

**Honeypot SSH/Web desenvolvido em Python com motor de detecção próprio e dashboard em tempo real.**

**Tecnologias:**

`Python` `Flask` `Socket` `HTTP` `JSONL` `Linux` `VirtualBox`

### O que foi desenvolvido

*   Honeypot SSH e Web construído do zero.
*   Motor de detecção baseado em **janelas deslizantes**.
*   Quatro regras independentes para identificação de comportamentos suspeitos.
*   Deduplicação baseada em baseline para redução de **alert fatigue**.
*   Persistência estruturada de eventos em **JSONL**.
*   Dashboard em Flask com atualização em tempo real através de API JSON.
*   Simulador de ataques para geração controlada de eventos.
*   Laboratório isolado em rede **Host-Only**.

### Regras de detecção

| Regra                  | Severidade | Gatilho                            |
| ---------------------- | ---------- | ---------------------------------- |
| `connection_burst`     | MEDIUM     | 5+ conexões do mesmo IP em 60s     |
| `repeated_ssh_banner`  | LOW        | 3+ banners SSH do mesmo IP em 60s  |
| `suspicious_payload`   | HIGH       | Payload contendo padrões suspeitos |
| `http_suspicious_path` | MEDIUM     | Requisições para paths sensíveis   |

🔗 **[Ver projeto →](https://github.com/Pendragon711/ssh-honeypot-lab)**

---

# 🔬 DFIR — em aprofundamento

Estou estudando a parte forense: preservar evidências com cuidado, correlacionar logs de várias fontes e reconstruir a linha do tempo de um incidente.

*   **Em prática:** análise de logs, correlação de eventos no Wazuh e documentação de evidências.
*   **Em estudo:** `Sysmon` `Autopsy` `Volatility` `MITRE ATT&CK`

---

# ⚔️ Visão ofensiva

Conhecer o ataque ajuda a escrever detecções melhores e a entender o rastro que ele deixa. Estes são meus projetos da área ofensiva.

*   👁️ **[ODIN](https://github.com/Pendragon711/odin-recon)** — Pipeline de reconhecimento web em Go (Subfinder, Naabu, HTTPX e Katana), com detecção de WAF e um banco SQLite por alvo.
*   👻 **[GHOST](https://github.com/Pendragon711/GHOST---Web-Pentest-Framework)** — Framework de pentest web em Python e Playwright, com classificação **CWE**, severidade **CVSS v3.1** e integração com o laboratório Wazuh.
*   🔎 **[Bug Bounty](https://hackerone.com/)** — Pesquisa de vulnerabilidades em programas autorizados no HackerOne.
*   🧪 **Pentest & Exploitation Lab** — Kali Linux, Metasploit, Metasploitable 2, Nmap e Burp Suite em ambiente isolado.

---

# ☁️ Cloud & Infrastructure

## AWS Security Lab — EC2, S3 & VPC

**Laboratório prático de infraestrutura AWS com foco em fundamentos de cloud e segurança.**

**Tecnologias:**

`AWS` `EC2` `S3` `VPC` `Security Groups` `EBS` `Git`

🔗 **[Ver projeto →](https://github.com/Pendragon711/projeto-aws-s3-ec2)**

---

# 🧰 Security Stack

### 🔵 SOC / Blue Team

<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-3C8CBE?style=for-the-badge&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/SIEM-4B0082?style=for-the-badge" alt="SIEM" />
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-000000?style=for-the-badge&logo=mitre&logoColor=white" alt="MITRE ATT&CK" />
</p>

**Foco:** Security Monitoring • Alert Triage • Log Analysis • Threat Detection • Event Correlation • Detection Engineering • Incident Investigation • Playbooks de resposta

---

### 🌐 Networks & Systems

<p align="left">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
  <img src="https://img.shields.io/badge/TCP%2FIP-005571?style=for-the-badge" alt="TCP/IP" />
  <img src="https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white" alt="VirtualBox" />
</p>

**Foco:** TCP/IP • Network Analysis • Traffic Analysis • Network Troubleshooting • Firewalls • Linux • Virtualization

---

### 🐍 Development & Automation

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
</p>

---

### 🔴 Offensive Security (complemento)

<p align="left">
  <img src="https://img.shields.io/badge/Burp%20Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white" alt="Burp Suite" />
  <img src="https://img.shields.io/badge/Nmap-4682B4?style=for-the-badge" alt="Nmap" />
  <img src="https://img.shields.io/badge/Metasploit-2596CD?style=for-the-badge" alt="Metasploit" />
  <img src="https://img.shields.io/badge/Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" alt="Kali Linux" />
  <img src="https://img.shields.io/badge/OWASP-000000?style=for-the-badge&logo=owasp&logoColor=white" alt="OWASP" />
</p>

**Standards:** OWASP Top 10 • CWE • CVSS v3.1

---

# 🎯 Áreas de Interesse

### 🔵 Defensive Security

`SOC` `SIEM` `Threat Detection` `Detection Engineering` `Log Analysis` `Incident Response` `DFIR` `MITRE ATT&CK`


---

# 🎓 Formação & Certificações

🎓 **Graduação em Cibersegurança**
UniCesumar — Em andamento

📜 **Fundamentos de SOC N1** — Be Safe Inc.

📜 **Analista de SOC na Era da IA** — IBSEC

📜 **Google Cybersecurity Professional Certificate** — Coursera

📜 **Cisco Junior Cybersecurity Analyst** — Cisco Networking Academy

📜 **Nano Course Cybersecurity** — FIAP

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
  🛡️ <strong>Building practical defensive security skills through SOC operations, detection engineering and incident response.</strong>
</p>
