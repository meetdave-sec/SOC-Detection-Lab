# SOC Detection Lab

## Overview

This project simulates a Security Operations Center (SOC) workflow by detecting and analyzing network-based attacks using Suricata IDS.

The lab demonstrates how an attacker performs reconnaissance and how a defender detects, analyzes, and reports the activity.

---

## Scenario: Port Scan Detection

A TCP SYN scan was performed using Nmap from an attacker machine targeting a victim system.

The activity was detected using a custom Suricata rule.

---

## Lab Setup

- Attacker: Kali Linux
- Target: Ubuntu
- IDS: Suricata
- Network: Internal VM network

---

## Detection Workflow

1. Attack simulation using Nmap  
2. Packet capture and analysis via Suricata  
3. Custom rule creation for SYN detection  
4. Log analysis using fast.log  
5. Incident reporting  

---

## Key Features

- Custom Suricata rule for SYN scan detection  
- Real-time alert monitoring  
- Log-based threat analysis  
- SOC-style incident report  

---

## Evidence

### Nmap Scan
![Scan](assets/nmap-scan.png)

### Suricata Alerts
![Alerts](assets/syn-alerts.png)

---

## Project Structure

SOC-Detection-Lab/
├── lab-setup/
├── configs/
├── logs/
├── attacks/
├── reports/
└── assets/

---

## Skills Demonstrated

- Network traffic analysis  
- Intrusion detection (IDS)  
- Threat detection engineering  
- Incident analysis and reporting  
- Blue team fundamentals  

---

## Conclusion

This project demonstrates practical blue team capabilities, including detection of reconnaissance activity, log analysis, and structured incident reporting.