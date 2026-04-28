# Scan Analysis – Suricata Logs

## Overview

This analysis focuses on alerts generated during a simulated Nmap TCP SYN scan against the target system.

---

## Log Source

- File: /var/log/suricata/fast.log
- IDS: Suricata
- Detection Rule: Custom SYN packet detection rule

---

## Observations

Sample alert:

SOC LAB: SYN Packet Detected [TCP] 192.168.100.5:55158 -> 192.168.100.4:26313

---

## Key Indicators

- **Source IP:** 192.168.100.5 (Attacker)
- **Destination IP:** 192.168.100.4 (Target)
- **Protocol:** TCP
- **Flag:** SYN
- **Behavior:** Multiple SYN packets in rapid succession

---

## Analysis

- High volume of SYN packets observed
- Packets targeting multiple ports
- No completed TCP handshake observed
- Behavior matches reconnaissance activity (port scanning)

---

## Detection Logic

The custom Suricata rule detects SYN packets:

alert tcp any any -> any any (msg:"SOC LAB: SYN Packet Detected"; flags:S; sid:1000001; rev:1;)


Repeated alerts indicate abnormal traffic patterns.

---

📸 Log Evidence:
![Scan Logs](../assets/scan-logs.png)

---

## Conclusion

The traffic pattern strongly indicates a TCP SYN scan performed using Nmap.

The IDS successfully detected the scanning activity using a custom rule.

---

## Security Insight

SYN scans are commonly used by attackers to:
- Identify open ports
- Map exposed services
- Prepare for further exploitation