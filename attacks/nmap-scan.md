# Nmap Port Scan Detection

## Objective
Simulate a port scanning attack from an attacker machine and analyze detection using Suricata IDS.

---

## Environment

- Attacker: Kali Linux (192.168.100.5)
- Target: Ubuntu (192.168.100.4)
- IDS: Suricata running on target
- Interface: enp0s3

---

## Attack Execution

The following command was used to perform a TCP SYN scan:

nmap -sS -p- -T4 192.168.100.4

📸 Attack Execution:
![Nmap Scan](../assets/nmap-scan.png)

---

## Detection

A custom Suricata rule was created to detect SYN packet activity:

alert tcp any any -> any any (msg:"SOC LAB: SYN Packet Detected"; flags:S; sid:1000001; rev:1;)


During the scan, multiple alerts were generated indicating SYN packet activity.

📸 Detection Evidence:
![Suricata Alerts](../assets/syn-alerts.png)

---

## Analysis

- Multiple SYN packets were observed in a short period
- Source IP: 192.168.100.5 (Attacker)
- Destination IP: 192.168.100.4 (Target)
- Behavior consistent with port scanning activity

---

## Conclusion

The simulated port scan successfully triggered detection in Suricata using a custom rule.

This demonstrates how network-based reconnaissance activity can be identified through packet-level monitoring.

---

## Key Takeaway

Default detection rules did not clearly identify the scan.  
A custom rule was implemented to detect SYN-based scanning behavior.