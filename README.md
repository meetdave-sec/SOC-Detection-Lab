# SOC Detection Lab

## Overview

This project simulates real-world Security Operations Center (SOC) workflows by detecting, analyzing, and reporting network and host-based attacks.

The lab demonstrates both attacker techniques and defensive monitoring using Suricata IDS and system logs.

---

## Lab Environment

- **Attacker:** Kali Linux (192.168.100.5)
- **Target:** Ubuntu Server (192.168.100.4)
- **Tools:** Suricata, Nmap, Hydra
- **Logs:** Suricata (fast.log), Linux auth.log

---

## Scenarios Implemented

### 1. Port Scan Detection (Network-Based)

- Attack: Nmap TCP SYN Scan
- Detection: Custom Suricata rule
- Evidence: Packet-level alerts

📸 Nmap Scan  
![Nmap](assets/nmap-scan.png)

📸 Suricata Detection  
![Alerts](assets/syn-alerts.png)

---

### 2. SSH Brute Force Attack (Host-Based)

- Attack: Hydra password brute force
- Detection: Authentication logs
- Result: Successful account compromise

📸 Hydra Attack  
![Hydra](assets/hydra-attack.png)

📸 Auth Logs  
![Auth](assets/auth-log-bruteforce.png)

---

## Detection Approach

This project demonstrates two key detection strategies:

- **Network-based detection** (Suricata IDS)
- **Host-based detection** (Linux authentication logs)

It also highlights limitations of default IDS rules and the need for custom detection tuning.

---

## Project Structure

SOC-Detection-Lab/
├── attacks/ # Attack execution documentation
├── logs/ # Log analysis
├── reports/ # Incident reports
├── assets/ # Screenshots (evidence)
├── configs/ # IDS rules/configs
└── lab-setup/ # Environment setup

---

## Skills Demonstrated

- Intrusion Detection (IDS)
- Network Traffic Analysis
- Log Analysis (auth.log, Suricata)
- Threat Detection & Investigation
- Incident Reporting (SOC workflow)
- Understanding attacker techniques (Nmap, Hydra)

---

## Key Takeaways

- Default IDS rules may not detect all attack patterns
- Custom detection rules improve visibility
- Authentication logs are critical for detecting credential attacks
- Weak passwords lead to account compromise

---

## Conclusion

This lab demonstrates end-to-end SOC capabilities, from attack simulation to detection, analysis, and reporting.

It reflects practical blue team skills required in real-world security operations environments.