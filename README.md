# 🛡️ Daniel Widal — DFIR & Incident Response

### Analista de Segurança | Digital Forensics | Resposta a Incidentes | Detection Engineering

<p align="left">
  <a href="https://pendragon711.github.io">
    <img src="https://img.shields.io/badge/🌐_Portfólio-pendragon711.github.io-6cc7ff?style=for-the-badge&labelColor=0a1016" alt="Portfólio" />
  </a>
</p>

Profissional de **Cibersegurança** focado em **Digital Forensics, Incident Response (DFIR)** e **Detection Engineering**, com experiência sólida na investigação e contenção de ameaças, além de base estruturada em infraestrutura e redes.

Com experiência prática no ecossistema de Segurança da Informação, atuo na **investigação profunda de incidentes** (malware, phishing avançado e movimentação lateral), **forense de rede (PCAP)**, **análise de artefatos maliciosos** e criação de **playbooks de resposta**. 

Fora do trabalho, construo e mantenho laboratórios avançados: desenvolvi um **honeypot** com motor próprio de detecção em Python, gerencio um ambiente **SIEM (Wazuh)** para threat hunting e documento minuciosamente write-ups de **Network Forensics e Malware Analysis**. Minha base em **pentest** e visão ofensiva me permite mapear o comportamento do adversário (Kill Chain/MITRE ATT&CK) para desenvolver detecções mais resilientes.

🎓 **Cibersegurança — UniCesumar | Em andamento**

---

# 🔎 Metodologia de Investigação

Do alerta à contenção, guiado por evidências e rastreabilidade.

| Etapa | O que eu faço |
| ----- | ------------- |
| **Identificar** | Dimensionar o escopo do comprometimento e os vetores de ataque. |
| **Preservar** | Garantir a integridade das evidências (isolamento, memória, disco) antes de qualquer ação mitigatória. |
| **Coletar** | Extrair artefatos do mais volátil ao menos volátil, registrando a cadeia de custódia. |
| **Analisar** | Correlacionar logs, extrair payloads de PCAPs, realizar engenharia reversa básica e montar a linha do tempo (Timeline). |
| **Reportar** | Documentar IOCs, táticas usadas (MITRE ATT&CK) e recomendações de remediação estruturada. |

### Princípios Forenses Aplicados
*   Trabalhar sempre em cópias forenses ou sandboxes, nunca no sistema original.
*   Garantir a integridade através do cálculo de hashes (MD5/SHA-256) antes e depois da extração.
*   Mapear comportamentos nativos (Living off the Land / LOLBins) para distinguir atividades legítimas de ofuscação.

<details>
<summary><strong>📋 Meus playbooks de Resposta a Incidentes (clique para abrir)</strong></summary>

<br>

**Infecção por Malware / Ransomware**
1. Identificar o processo suspeito: arquivo, caminho de execução, hash e comportamento.
2. Isolar a estação comprometida da rede (mantendo a máquina ligada para possível dump de memória).
3. Reconstruir a árvore de processos (Event ID 4688) para achar o processo pai (ex: wscript.exe, powershell.exe).
4. Verificar persistência (chaves de registro, tarefas agendadas) e conexões de C2 (Command & Control).
5. Extrair e validar o hash em plataformas de Threat Intel (VirusTotal, ANY.RUN).
6. Preservar evidências, realizar limpeza, documentar IOCs e implementar regras de bloqueio preventivo.

**Comprometimento de Credenciais e Acesso Anômalo**
1. Confirmar o evento: conta, horário (UTC), origem (IP/Geo) e método de autenticação.
2. Comparar com o baseline do usuário (Impossible Travel, horários atípicos).
3. Procurar varreduras de força bruta (Eventos 4625 repetidos seguidos por 4624 de sucesso).
4. Se confirmado: encerrar sessões ativas imediatamente, invalidar tokens, forçar reset de credenciais e revisar logs do MFA.
5. Iniciar varredura na rede buscando sinais de movimentação lateral iniciados por esta conta.

**Phishing Direcionado (Spear-Phishing)**
1. Analisar cabeçalhos de e-mail originais: falhas em SPF, DKIM, DMARC e roteamento de SMTP.
2. Extrair anexos ou links em ambiente isolado (Sandbox) para análise dinâmica.
3. Dimensionar o impacto: buscar nos logs do servidor de e-mail quem mais recebeu, abriu e clicou.
4. Conter a ameaça: expurgar os e-mails das caixas de entrada e bloquear domínios/IPs nos firewalls e proxies.
5. Auditar contas de usuários que interagiram com a carga maliciosa.

</details>

---

# 🔬 DFIR — Forense Digital & Análise de Malware

Projetos de investigação focados em **preservar evidências, extrair payloads de rede, analisar comportamento de ameaças e reconstruir a Kill Chain**.

## 🕸️ DFIR Investigation: DanaBot — Network Forensics & Kill Chain Analysis

**Análise forense de tráfego de rede (PCAP) para investigar uma infecção em múltiplos estágios do malware DanaBot, extraindo payloads disfarçados e mapeando o comportamento do atacante.**

**Tecnologias:**
`Wireshark` `Network Forensics` `VirusTotal` `ANY.RUN` `PowerShell` `OSINT`

### O que foi desenvolvido
*   **Deep Packet Inspection:** Identificação do IP do atacante e do acesso inicial via requisições HTTP GET.
*   **Payload Extraction:** Reconstrução de fluxos HTTP (HTTP Streams) para isolar e extrair arquivos maliciosos forçados no download (`.js` disfarçado de `.php`).
*   **Hash Investigation:** Geração segura de assinaturas criptográficas (SHA-256) via PowerShell para análise em Threat Intel.
*   **Behavioral Analysis:** Mapeamento da árvore de execução do malware utilizando sandboxes, identificando o abuso de utilitários nativos do Windows (`wscript.exe` / *Living off the Land*).
*   **Multi-Stage Tracking:** Identificação do download secundário e isolamento do hash MD5 do segundo estágio da infecção (`.dll`).

🔗 **[Ver projeto →](https://github.com/Pendragon711/danabot-dfir-investigation)**

---

## 🔎 DFIR Investigation: XLMRat — Network Forensics & Malware Triage

**Investigação completa de uma cadeia de entrega e execução do AsyncRAT (lab XLMRat, CyberDefenders), correlacionando artefatos de rede e sistema.**

**Tecnologias:**
`Wireshark` `CyberChef` `VirusTotal` `Python` `MITRE ATT&CK`

### O que foi desenvolvido
*   Análise do tráfego HTTP e identificação do download do primeiro estágio (um arquivo `.jpg` com cabeçalho adulterado).
*   Desofuscação do payload e identificação do timestamp de compilação do arquivo PE malicioso.
*   Investigação forense sobre o abuso do LOLBin **RegSvcs.exe** para execução furtiva e evasão de defesa.
*   Extração de **IOCs** (defanged) e documentação de todos os artefatos dropados pelo script.
*   Mapeamento de técnicas e táticas no **MITRE ATT&CK** (T1105, T1059.001, T1218.009, T1620).

🔗 **[Ver projeto →](https://github.com/Pendragon711/xlmrat-dfir-investigation)**

---

# 🛡️ SOC & Detection Engineering

Projetos voltados para engenharia de detecção personalizada, monitoramento ativo e mitigação de fadiga de alertas.

## 🍯 SSH Honeypot Lab — Detection Engine & Live Dashboard

**Honeypot interativo desenvolvido em Python com motor de detecção focado em comportamento e dashboard em tempo real.**

**Tecnologias:**
`Python` `Flask` `Socket` `Linux` `VirtualBox` `JSONL`

### O que foi desenvolvido
*   Honeypot corporativo construído do zero com motor de detecção baseado em **janelas deslizantes**.
*   Deduplicação avançada baseada em baseline para redução de **alert fatigue** no SOC.
*   Regras independentes de detecção: `connection_burst` (força bruta), `repeated_ssh_banner` (reconhecimento) e `suspicious_payload` (injeção).
*   Persistência estruturada em **JSONL** pronta para ingestão em SIEM.

🔗 **[Ver projeto →](https://github.com/Pendragon711/ssh-honeypot-lab)**

---

## 🛡️ SOC Lab — Wazuh SIEM & Threat Hunting

**Ambiente corporativo de SOC para simulação de APTs, coleta de eventos e engenharia de detecção.**

**Tecnologias:**
`Wazuh` `SIEM` `Kali Linux` `MITRE ATT&CK`

### O que foi desenvolvido
*   Coleta, normalização e análise de logs de segurança em endpoints críticos.
*   Criação e ajuste fino (tuning) de regras de detecção para comportamentos anômalos.
*   Detecção de ataques de **brute force e movimentação lateral** em under 10 segundos.

🔗 **[Ver projeto →](https://github.com/Pendragon711/soc-lab-wazuh)**

---

# ⚔️ Visão Ofensiva (Red Team Awareness)

Entender o comportamento do atacante é o principal pilar para investigar e detectar ameaças reais.

*   👁️ **[ODIN](https://github.com/Pendragon711/odin-recon)** — Pipeline de reconhecimento em Go (Subfinder, Naabu, HTTPX) para mapeamento de superfície de ataque e detecção de WAF.
*   👻 **[GHOST](https://github.com/Pendragon711/GHOST---Web-Pentest-Framework)** — Framework de automação em Python e Playwright, com classificação **CWE** e **CVSS v3.1**, integrado a alertas do Wazuh.

---

# ☁️ Cloud & Infrastructure

## AWS Security Lab — EC2, S3 & VPC
**Laboratório prático de arquitetura segura em infraestrutura Cloud AWS.**

**Tecnologias:** `AWS` `EC2` `S3` `VPC` `Security Groups` `IAM`

🔗 **[Ver projeto →](https://github.com/Pendragon711/projeto-aws-s3-ec2)**

---

# 🧰 Security Stack & Tools

### 🔬 DFIR & Malware Analysis
<p align="left">
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark" />
  <img src="https://img.shields.io/badge/CyberChef-C8391B?style=for-the-badge" alt="CyberChef" />
  <img src="https://img.shields.io/badge/VirusTotal-394EFF?style=for-the-badge&logo=virustotal&logoColor=white" alt="VirusTotal" />
  <img src="https://img.shields.io/badge/Sysinternals-0078D4?style=for-the-badge&logo=windows&logoColor=white" alt="Sysinternals" />
</p>

**Expertise:** Network Forensics • PCAP Analysis • Process Tree Analysis • Payload Extraction • Hash-based Investigation • Chain of Custody

---

### 🔵 SOC / Detection Engineering
<p align="left">
  <img src="https://img.shields.io/badge/Wazuh-3C8CBE?style=for-the-badge&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/SIEM-4B0082?style=for-the-badge" alt="SIEM" />
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-000000?style=for-the-badge&logo=mitre&logoColor=white" alt="MITRE ATT&CK" />
</p>

**Expertise:** Threat Hunting • Alert Triage • Log Correlation • Custom Rule Creation • Incident Playbooks

---

### 🌐 IT / Scripting
<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Bash-121011?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash" />
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS" />
</p>

---

# 🎓 Formação & Certificações

🎓 **Graduação em Cibersegurança** — UniCesumar (Em andamento)
📜 **Google Cybersecurity Professional Certificate** — Coursera
📜 **Fundamentos de SOC** — Be Safe Inc.
📜 **Analista de SOC na Era da IA** — IBSEC
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
  🛡️ <strong>"Think like an attacker, investigate like an analyst."</strong>
</p>
