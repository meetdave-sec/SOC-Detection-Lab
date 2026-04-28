# SSH Brute Force Analysis

## Overview

This analysis focuses on SSH authentication logs generated during a simulated brute-force attack.

---

## Log Source

- File: /var/log/auth.log
- Service: SSH (sshd)

---

## Sample Log Entries

Failed password for testuser from 192.168.100.5 port 41350 ssh2
PAM service(sshd) ignoring max retries
error: maximum authentication attempts exceeded

📸 Log Evidence:
![Auth Logs](../assets/auth-log-bruteforce.png)

---

## Key Indicators

- **Source IP:** 192.168.100.5 (Attacker)
- **Target User:** testuser
- **Service:** SSH
- **Behavior:** Repeated failed authentication attempts

---

## Detection Pattern

Indicators of brute-force attack:

- Multiple failed login attempts in short time
- Same source IP targeting same user
- Authentication retry limits exceeded

---

## Evidence of Compromise

session opened for user testuser

---

## Analysis

- The attacker attempted multiple password guesses
- Authentication failures indicate brute-force activity
- Eventually, correct credentials were discovered
- Successful login confirms account compromise

---

## Conclusion

The log data clearly indicates a brute-force attack leading to successful authentication.

This highlights the risk of weak credentials and the importance of monitoring authentication logs.

---

## Security Insight

Brute-force attacks can be detected by analyzing authentication logs for repeated failures followed by successful login.

