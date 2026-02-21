# Vulnerability Assessment and OWASP Web Testing Lab

This is my cybersecurity homelab project using Kali Linux and Metasploitable.
I built this lab to practice penetration testing, vulnerability assessment, and basic web security testing.

Everything was done locally on my laptop using virtual machines.

## Lab Setup

Attacker:
- Kali Linux
  
Victim:
- Metasploitable2

Virtualization:
- VirtualBox

Network:
- Host-only adapter

## What I Did

### 1. Network Reconnaissance
- Used Nmap to scan the target
- Discovered open ports and services

Example:
- FTP
- Telnet
- HTTP
- SMB
- MySQL

### 2. Initial Access

- Connected using Telnet with default credentials
- Logged in as msfadmin

### 3. Privilege Escalation

- Used sudo to become root

### 4. User Enumeration

- Read /etc/passwd to list users
- Identified real login accounts

### 5. Password Hash Extraction

- Dumped /etc/shadow
- Collected password hashes
- Prepared hashes for offline cracking

### 6. Web Application Testing (DVWA)

Tested common OWASP vulnerabilities:

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection

Each test was done manually from the browser.

## Vulnerabilities Found

### SQL Injection (High)
- Payload: 1' OR '1'='1
- Result: dumped all users

Fix:
- Use parameterized queries

### XSS (Medium)
- Payload: <script>alert('xss')</script>

Fix:
- Input validation and output encoding

### Command Injection (Critical)
- Payload: ; whoami
- Result: executed system commands

Fix:
- Sanitize system calls

## Skills Practiced

- Network scanning
- Service enumeration
- Manual exploitation
- Privilege escalation
- Password harvesting
- Web application security testing
- Basic incident understanding

## Disclaimer

This lab was created for learning purposes only.

All testing was done on intentionally vulnerable virtual machines that I own.
