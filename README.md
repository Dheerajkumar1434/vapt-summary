# 🔒 Vulnerability Assessment and Penetration Testing (VAPT) Summary

## 📌 Project Overview
This repository documents a basic VAPT (Vulnerability Assessment and Penetration Testing) process using widely recognized open-source and commercial tools. The objective is to identify, analyze, and report security vulnerabilities in a target system using ethical hacking techniques.

---

## 🎯 Scope
- **Target Type**: Web Applications, Network Infrastructure, APIs  
- **Test Environment**: Staging / Internal Network  
- **Methodology**: **PTES (Penetration Testing Execution Standard)**

---

## 🕒 Timeline
- **Reconnaissance**: 2 days  
- **Scanning & Enumeration**: 1 day  
- **Vulnerability Analysis**: 1 day  
- **Exploitation**: 2 days  
- **Post-Exploitation & Reporting**: 1 day

---

## 📊 Risk Rating Matrix

| **Impact** | **Likelihood** | **Resulting Severity** |
|------------|----------------|-------------------------|
| High       | High           | Critical                |
| High       | Medium         | High                    |
| Medium     | Medium         | Medium                  |
| Low        | Medium         | Low                     |

---

## 🛠️ Tools Used

| Tool         | Category               | Description |
|--------------|------------------------|-------------|
| OpenVAS      | Vulnerability Scanner  | Network-level vulnerability scanner |
| Acunetix     | Web Vulnerability Scanner | Detects SQLi, XSS, etc. |
| Nmap         | Port Scanner           | Port and service discovery |
| Legion       | Reconnaissance Tool    | Enumeration and brute-force |
| Nessus       | Vulnerability Scanner  | Advanced CVE scanning with CVSS scoring |
| Nikto        | Web Server Scanner     | Finds insecure server configurations |
| OWASP ZAP    | Web Application Proxy  | Manual & automated web app testing |
| Metasploit   | Exploitation Framework | Exploit known vulnerabilities |
| Hydra        | Brute-force Tool       | Cracks login credentials for various protocols |
| SQLmap       | SQL Injection Tool     | Automates database exploitation |

---

## 🔍 Tool-to-Vulnerability Mapping

- **SQLmap** → Detected SQL Injection on `/login.php`
- **Nikto** → Identified outdated Apache server with vulnerable modules
- **Nmap + Legion** → Found SSH port 22 open with default banners, brute-forced valid usernames
- **OWASP ZAP** → Detected verbose HTTP headers and session ID exposure
- **Metasploit** → Exploited unpatched Samba share (CVE-2017-7494)

---

## 📋 Summary of Findings

| **Severity** | **Example Vulnerability**        | **Tool Used**     |
|--------------|----------------------------------|-------------------|
| Critical     | SQL Injection                    | SQLmap            |
| High         | Outdated Web Server              | Nikto             |
| Medium       | Open SSH Port with Default Banner| Nmap / Legion     |
| Low          | Verbose HTTP Headers             | OWASP-ZAP         |

---

## ✅ Recommendations
- Sanitize user inputs and use prepared SQL statements
- Update outdated software and patch known vulnerabilities
- Implement proper firewall, IDS, and logging rules
- Disable unnecessary services and restrict port access
- Enforce strong password policies and multifactor authentication

---

## 📁 Folder Structure

```bash
.
├── README.md
├── tools/
│   ├── nmap_scan.txt
│   ├── zap_report.md
│   └── sqlmap_log.txt
├── findings/
│   ├── critical.md
│   ├── high.md
│   └── medium_low.md
├── remediation/
│   └── checklist.md
└── appendix/
    ├── screenshots/
    └── raw_logs/
