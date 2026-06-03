# Advanced VAPT Project

## Overview

This project demonstrates the complete Vulnerability Assessment and Penetration Testing (VAPT) lifecycle using a controlled laboratory environment. The assessment was performed against the Metasploitable2 virtual machine and included reconnaissance, vulnerability identification, web application testing, reporting, and remediation recommendations.

---

## Objectives

* Perform network reconnaissance and service enumeration
* Identify vulnerable services
* Conduct web application security testing
* Analyze security weaknesses
* Document findings and remediation recommendations
* Produce professional penetration testing reports

---

## Lab Environment

### Attacker Machine

* Kali Linux
* IP Address: 192.168.56.103

### Target Machine

* Metasploitable2
* IP Address: 192.168.56.101

### Tools Used

* Nmap
* Burp Suite Community Edition
* OWASP ZAP
* Wireshark
* Metasploit Framework
* DVWA (Damn Vulnerable Web Application)

---

## Network Reconnaissance

### Nmap Scan

Command:

```bash
nmap -sV 192.168.56.101
```

Services Identified:

* FTP (vsftpd 2.3.4)
* SSH
* Telnet
* SMTP
* DNS
* Apache HTTP Server
* Samba
* MySQL
* PostgreSQL
* Apache Tomcat
* UnrealIRCd

---

## Web Application Testing

### Target Application

DVWA

URL:

http://192.168.56.101/dvwa

### Vulnerabilities Tested

#### SQL Injection

Severity: Critical

Description:
The application accepts unsanitized user input that may allow manipulation of database queries.

#### Cross-Site Scripting (XSS)

Severity: Medium

Description:
The application reflects user input without proper sanitization, allowing script execution within the browser.

---

## Traffic Analysis

### Wireshark

Traffic was captured and analyzed during interactions with the target web application.

Evidence Collected:

* HTTP Requests
* HTTP Responses
* ICMP Traffic
* TCP Sessions

---

## Burp Suite Assessment

Burp Suite was used to intercept and inspect HTTP requests exchanged between the client and the target application.

Activities:

* Request interception
* Parameter inspection
* HTTP traffic analysis

---

## Findings Summary

| Finding ID | Vulnerability                | Severity |
| ---------- | ---------------------------- | -------- |
| F001       | SQL Injection                | Critical |
| F002       | Reflected XSS                | Medium   |
| F003       | Exposed Management Interface | High     |

---

## Recommendations

1. Validate and sanitize all user inputs.
2. Implement parameterized database queries.
3. Restrict access to administrative interfaces.
4. Apply security patches regularly.
5. Conduct periodic vulnerability assessments.
6. Implement secure authentication mechanisms.

