# MS17-010 (EternalBlue) Exploitation Lab

A hands-on penetration testing lab demonstrating the complete exploitation lifecycle of the MS17-010 (EternalBlue) vulnerability against a vulnerable Windows 7 SP1 virtual machine.

> **Disclaimer**
>
> This project was conducted entirely inside an isolated VMware lab environment for educational and authorized penetration testing purposes.

---

## Lab Overview

This lab follows a structured penetration testing methodology rather than simply executing an exploit.

The assessment included:

- Reconnaissance
- Service Enumeration
- Vulnerability Identification
- Exploitation
- Post-Exploitation
- Documentation

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Attacker | Kali Linux |
| Target | Windows 7 Professional SP1 x64 |
| Virtualization | VMware Workstation |
| Network | Host-Only |
| Framework | Metasploit Framework |
| Scanner | Nmap |

---

## Target Information

| Item | Value |
|------|-------|
| Target IP | 192.168.243.131 |
| Attacker IP | 192.168.243.128 |
| Operating System | Windows 7 Professional SP1 x64 |
| Vulnerable Service | SMBv1 |
| Port | 445/TCP |
| Vulnerability | MS17-010 (EternalBlue) |
| CVE | CVE-2017-0143 |

---

## Assessment Summary

### Reconnaissance

- Verified connectivity between Kali Linux and Windows 7.
- Confirmed target availability.

### Enumeration

- Identified SMB service on TCP port 445.
- Detected Windows 7 Professional SP1.

### Vulnerability Assessment

- Confirmed the presence of MS17-010 using Nmap NSE scripts.

### Exploitation

- Successfully exploited MS17-010 using Metasploit.
- Obtained a Meterpreter session.

### Post-Exploitation

- Confirmed SYSTEM-level privileges.
- Collected operating system information.

---

## Skills Demonstrated

- Network Reconnaissance
- Service Enumeration
- SMB Enumeration
- Vulnerability Assessment
- Metasploit
- EternalBlue Exploitation
- Meterpreter
- Post-Exploitation
- Technical Documentation

---

## Project Structure

```
ms17-010-eternalblue-lab/
│
├── README.md
├── REPORT.md
├── LICENSE
│
└──  screenshots/
```

---

## Disclaimer

This project is intended solely for educational purposes inside an isolated laboratory environment.

Do not attempt these techniques against systems without explicit authorization.
