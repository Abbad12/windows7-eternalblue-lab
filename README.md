# MS17-010 (EternalBlue) Exploitation Lab
Hands-on penetration testing lab demonstrating the complete exploitation workflow of the MS17-010 (EternalBlue) vulnerability against Windows 7 using Kali Linux, Nmap, and Metasploit.

## Overview

This lab demonstrates the complete penetration testing workflow against a vulnerable Windows 7 SP1 virtual machine using Kali Linux and Metasploit Framework.

The assessment was performed in an isolated VMware Host-Only network for educational purposes.

---

## Lab Environment

### Attacker

- Kali Linux

### Target

- Windows 7 Professional SP1 x64

### Virtualization

- VMware Workstation

### Network

- Host-Only

---

## Objectives

- Verify network connectivity
- Enumerate exposed services
- Identify vulnerabilities
- Validate the MS17-010 vulnerability
- Exploit the target using Metasploit
- Obtain a Meterpreter session
- Perform basic post-exploitation enumeration

---

## Methodology

1. Reconnaissance
2. Service Enumeration
3. Vulnerability Identification
4. Exploitation
5. Post-Exploitation
6. Documentation

---

## Tools

- Nmap
- Metasploit Framework
- Meterpreter
- VMware Workstation

---

## Key Findings

| Finding | Result |
|----------|--------|
| Operating System | Windows 7 Professional SP1 x64 |
| SMB Service | TCP/445 |
| Vulnerability | MS17-010 (EternalBlue) |
| CVE | CVE-2017-0143 |
| Risk | High |
| Exploitation | Successful |
| Meterpreter Session | Established |
| Privilege Level | NT AUTHORITY\SYSTEM |

---

## Skills Demonstrated

- Network Discovery
- Service Enumeration
- SMB Enumeration
- Vulnerability Assessment
- Remote Code Execution
- Meterpreter Usage
- Post-Exploitation Enumeration
- Technical Documentation

---

## Disclaimer

This project was performed in a controlled laboratory environment using systems owned by the researcher. It is intended solely for educational and defensive cybersecurity purposes.
