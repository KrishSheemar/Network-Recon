# Network Reconnaissance & Service Enumeration

A hands-on cybersecurity lab project focused on network discovery, TCP port scanning, service identification and FTP enumeration using Kali Linux and Metasploitable 2.

## Project Overview

This project involved performing network reconnaissance against a deliberately vulnerable Metasploitable 2 virtual machine in an isolated Oracle VirtualBox lab environment.

The objective was to identify exposed network services, examine service versions, test anonymous FTP access and document potential security risks.

## Tools & Technologies

- Kali Linux
- Nmap
- Metasploitable 2
- Oracle VirtualBox
- TCP/IP
- FTP, SSH and Telnet

## Lab Environment

| Component | Configuration |
|---|---|
| Attacker | Kali Linux |
| Target | Metasploitable 2 |
| Virtualisation | Oracle VirtualBox |
| Target IP | 192.168.56.103 |
| Assessment | Network reconnaissance |

## Tasks Performed

1. Identified the target machine and verified network connectivity.
2. Conducted TCP port scanning and service version detection.
3. Enumerated FTP, SSH and Telnet services.
4. Tested anonymous FTP authentication.
5. Established a manual FTP connection and inspected the remote directory listing.
6. Documented security findings and recommendations.

## Key Findings

- Identified 23 TCP ports listed in the service enumeration report.
- Detected legacy services, including vsFTPd 2.3.4 and OpenSSH 4.7p1.
- Confirmed anonymous FTP authentication was enabled.
- Identified plaintext FTP communication.
- Identified Telnet exposure.
- Documented security hardening recommendations.

## Example Commands

```bash
# Service and version detection
nmap -sV 192.168.56.103

# Focused FTP, SSH and Telnet enumeration
nmap -sC -sV -p 21,22,23 192.168.56.103

# Check anonymous FTP access
nmap -p 21 --script ftp-anon 192.168.56.103

# Manual FTP connection
ftp 192.168.56.103
```

## Security Recommendations

- Disable anonymous FTP unless explicitly required.
- Replace plaintext FTP with SFTP or FTPS.
- Disable Telnet and use SSH.
- Update outdated services.
- Restrict unnecessary exposed ports using firewall rules.

## Project Documentation

See the `report/` directory for the complete reconnaissance report and the `screenshots/` directory for supporting evidence.

## Scope & Disclaimer

This project was conducted in an isolated, authorised virtual lab using Metasploitable 2.

The assessment covered reconnaissance and service enumeration only. No successful exploitation, privilege escalation or root access is claimed.

Educational purposes only.
