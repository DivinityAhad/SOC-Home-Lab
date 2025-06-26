# Project Goals

##  What I an Trying to Learn

- How to set up and use a SIEM to detect common attack patterns  
- How cloud logging works (CloudTrail, CloudWatch)  
- How real-world logs are structured, analyzed, and triaged  
- How to secure and monitor basic web infrastructure (on-prem and cloud-hosted)

---

##  Core Components and Environments

### 1. Log Sources

- **Windows VM**  
  - Use Sysmon for detailed logging  
  - Log login events, PowerShell usage, file changes  

- **Linux VM**  
  - Use auditd or rsyslog  
  - Log web traffic, SSH attempts, system changes  

- **AWS Cloud Logs**  
  - CloudTrail (API events)  
  - GuardDuty (threat detection)  
  - CloudWatch (infrastructure monitoring)  

- **Web Application Logs**  
  - Host an app (HTML, Flask, or Node) locally and on AWS EC2  
  - Enable web server logging (Apache/nginx access/error logs)  

---

### 2. SIEM Platform

**Choose one:**

- **Wazuh** (recommended): Great dashboard, built-in rules, beginner-friendly  
- **Security Onion**: All-in-one but resource-heavy  
- **ELK Stack**: Full control and ideal for customization

**Log ingestion tools:**
- Filebeat / Winlogbeat / Logstash
- Sources: Windows Event Logs, Sysmon, Linux syslogs, AWS logs (via CloudWatch/CloudTrail)

---

### 3. Threat Simulation / Log Generation Tools

- **Atomic Red Team** – open-source attack simulation  
- **Invoke-AtomicRedTeam** – PowerShell-based simulation  
- **Manual Testing:**
  - Trigger failed logins (RDP, SSH)  
  - Browse malicious sites (in sandbox)  
  - Port scans, unauthorized file access  

- **Optional:** OWASP Juice Shop – vulnerable web app for generating logs

---

### 4. Monitoring, Detection & Alerting

Set up detection logic using:

- **MITRE ATT&CK Framework** to map techniques  
- **Sample detection rules:**
  - PowerShell execution with suspicious args  
  - SSH brute force attempts from Linux  
  - AWS root account login detection  
  - Access to `/etc/passwd` or restricted directories  
