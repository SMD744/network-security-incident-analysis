# network-security-incident-analysis
Wireshark analysis of NetSupport RAT malware infection

# 🔍 Network Security Incident Analysis: NetSupport RAT Malware


## 📋 Overview

This repository contains a comprehensive incident report documenting the forensic analysis of suspicious network activity within an internal enterprise environment. The investigation identified a workstation compromised with **NetSupport RAT** through systematic packet analysis using Wireshark.

### 🎯 Key Findings

| Compromised Asset | Details |
|-------------------|---------|
| **Hostname** | `DESKTOP-TEYQ2NR` |
| **IP Address** | `10.2.28.28` |
| **Domain User** | Becka Rolf (`brolf`) |
| **Malicious C2 Server** | `45.131.214.85:443` |
| **Detection Method** | HTTP POST traffic analysis |

## 🔬 Investigation Methodology

### Phase 1: Traffic Collection
- Network packets captured using Wireshark
- Full packet capture preserved for analysis

### Phase 2: Malicious Traffic Identification
- HTTP filter `http.request` revealed suspicious POST requests
- Identified communication with external IP `45.131.214.85`

### Phase 3: Host Attribution
- NBNS protocol analysis mapped IP `10.2.28.28` to `DESKTOP-TEYQ2NR`
- Kerberos traffic revealed username `brolf`

### Phase 4: User Identification
- Deep packet inspection identified full user identity: **Becka Rolf**

## 🚨 Indicators of Compromise (IOCs)

| IOC Type | Value |
|----------|-------|
| 🖥️ Victim IP | 10.2.28.28 |
| ☠️ Malicious IP | 45.131.214.85 |
| 🔌 Source Port | 51912 |
| 🚪 Destination Port | 443 |
| 💻 Hostname | DESKTOP-TEYQ2NR |
| 🌐 Domain | EASYAS123 |
| 👤 Username | brolf |
| 🆔 Full Name | Becka Rolf |

## 📊 MITRE ATT&CK Mapping

| Tactic | Technique | ID | Evidence |
|--------|-----------|----|----------|
| Initial Access | Phishing | T1566 | User system initiated connection to suspicious external server |
| Command and Control | Web Protocols | T1071.001 | HTTP POST communication to external IP `45.131.214.85` |
| Discovery | System Information Discovery | T1082 | Internal system information discovered via NBNS |

## 🛡️ Recommended Remediation Steps

1. **Isolate** - Immediately disconnect `DESKTOP-TEYQ2NR` from the network
2. **Scan** - Perform full malware analysis using updated EDR tools
3. **Reset** - Force password reset for user `Becka Rolf` and review recent authentication logs
4. **Block** - Add `45.131.214.85` to firewall deny list at perimeter
5. **Hunt** - Search for similar communication patterns across the enterprise
6. **Monitor** - Enhance logging for HTTP/S traffic to external destinations

## 📁 Repository Structure


📦 network-security-incident-analysis

├── 📄 Incident-Report-NetSupport-RAT.md # Complete forensic report

├── 📄 README.md # This overview

├── 📂 images/ # Supporting evidence

│ ├── wireshark-capture.png

│ ├── http-post-traffic-1.png

│ ├── http-post-traffic-2.png

│ ├── nbns-query.png

│ ├── kerberos-auth.png

│ └── user-identification.png

└── 📄 LICENSE # MIT License


## 🔗 Related Resources

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [NetSupport RAT Analysis](https://malpedia.caad.fkie.fraunhofer.de/details/win.netsupport_manager_rat)

## 👨‍💻 Author

**OYEWOLE SAMAD OLUWASANJO**  
*Network Security Analyst*  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat-square&logo=linkedin)](https://linkedin.com/in/yourprofile)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=flat-square&logo=gmail)](mailto:oyewolesamadoluwasanjo@gmail.com)

---

<div align="center">
  <sub>This investigation was conducted as part of network security monitoring and incident response procedures.</sub>
  <br>
  <sub>© 2026 - All analysis and documentation original work</sub>
</div>
