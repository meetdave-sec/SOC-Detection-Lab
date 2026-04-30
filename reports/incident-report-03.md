# Incident Report – Web Directory Enumeration

## Summary

A web directory enumeration attack was detected against the target web server.  
The activity involved automated HTTP requests attempting to discover hidden directories and resources.

---

## Incident Details

- **Date/Time:** 30/April/2026: 12:51:55
- **Source IP:** 192.168.100.5
- **Destination IP:** 192.168.100.4
- **Service:** HTTP (Apache)
- **Attack Type:** Directory Enumeration (Gobuster)
- **Detection Source:** Apache access logs

---

## Description

The web server received a high volume of HTTP GET requests targeting various endpoints in a short time frame.

The request pattern indicates automated scanning behavior consistent with directory brute-force tools such as Gobuster.

---

## Evidence

📸 Gobuster Scan  
![Gobuster](../assets/gobuster-attack.png)

📸 Apache Access Logs  
![Logs](../assets/apache-enum-logs.png)

---

## Analysis

- Multiple HTTP requests sent rapidly from a single source IP
- Large number of `404 Not Found` responses
- Valid directories discovered (`/admin`, `/backup`)
- User-Agent identified as `gobuster/3.x`

These indicators confirm automated enumeration activity rather than normal user browsing.

---

## Impact

- Exposure of hidden directories
- Increased attack surface
- Potential access to sensitive resources
- Precursor to further exploitation

---

## Mitigation

- Restrict access to sensitive directories
- Implement rate limiting for HTTP requests
- Use Web Application Firewall (WAF)
- Monitor and alert on abnormal request patterns
- Disable directory listing where unnecessary

---

## Conclusion

The activity represents a directory enumeration attack aimed at identifying hidden web resources.

Monitoring access logs allowed detection of abnormal request patterns and identification of reconnaissance behavior.

---

## Analyst Notes

This scenario demonstrates:
- Detection through web server logs
- Identification of automated scanning behavior
- Understanding of reconnaissance techniques used before exploitation