# SOC Detection Lab

## Overview

This project simulates real-world Security Operations Center (SOC) workflows by detecting, analyzing, and reporting security events across network, host, and web layers.

It demonstrates how attackers perform reconnaissance and credential attacks, and how defenders detect and investigate these activities using Suricata IDS and system logs.

---

## Lab Environment

- **Attacker:** Kali Linux (192.168.100.5)
- **Target:** Ubuntu Server (192.168.100.4)
- **Services:** SSH, Apache Web Server
- **Tools:** Suricata, Nmap, Hydra, Gobuster
- **Logs:**
  - Network: `/var/log/suricata/fast.log`
  - Host: `/var/log/auth.log`
  - Web: `/var/log/apache2/access.log`

---

## Scenarios Implemented

### 1. Port Scan Detection (Network-Based)

- **Attack:** Nmap TCP SYN Scan  
- **Detection:** Custom Suricata rule  
- **Insight:** Default rules failed → custom rule improved visibility  

📸 Nmap Scan  
![Nmap](assets/nmap-scan.png)

📸 Suricata Detection  
![Alerts](assets/syn-alerts.png)

---

### 2. SSH Brute Force Attack (Host-Based)

- **Attack:** Hydra password brute force  
- **Detection:** Authentication logs (`auth.log`)  
- **Result:** Successful credential compromise  

📸 Hydra Attack  
![Hydra](assets/hydra-attack.png)

📸 Auth Logs  
![Auth](assets/auth-log-bruteforce.png)

---

### 3. Web Enumeration Attack (Application Layer)

- **Attack:** Gobuster directory brute force  
- **Detection:** Apache access logs  
- **Result:** Discovery of hidden directories (`/admin`, `/backup`)  

📸 Gobuster Scan  
![Gobuster](assets/gobuster-attack.png)

📸 Apache Logs  
![Logs](assets/apache-enum-logs.png)

---

## Detection Approach

This project demonstrates layered detection:

- **Network-level:** Suricata IDS for packet analysis  
- **Host-level:** Authentication log monitoring  
- **Application-level:** Web access log analysis  

It also highlights a key reality:

> Detection is not tool-dependent — it requires understanding behavior patterns across multiple data sources.

---

## Project Structure

SOC-Detection-Lab/
├── attacks/ # Attack execution documentation
├── logs/ # Log analysis
├── reports/ # Incident reports
├── assets/ # Screenshots (evidence)
├── configs/ # IDS rules/configuration
└── lab-setup/ # Environment setup

---

## Skills Demonstrated

- Intrusion Detection (Suricata IDS)
- Network Traffic Analysis
- Log Analysis (auth.log, access.log, fast.log)
- Threat Detection & Investigation
- Incident Reporting (SOC workflow)
- Understanding attacker techniques (Nmap, Hydra, Gobuster)

---

## Key Takeaways

- Default IDS rules may miss real attack patterns  
- Custom detection improves visibility  
- Authentication logs are critical for detecting brute-force attacks  
- Web logs reveal reconnaissance behavior  
- Weak credentials lead to account compromise  

---

## Conclusion

This project demonstrates end-to-end SOC capabilities:

- Attack simulation  
- Detection engineering  
- Log analysis  
- Incident reporting  

It reflects practical blue team skills aligned with real-world security operations.
