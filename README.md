# Saturn Network Security Analysis

## Overview
This project simulates a real-world internal network security assessment using Kali Linux to identify, exploit, detect, and mitigate vulnerabilities within a controlled lab environment.

## Objectives
- Perform network reconnaissance and service enumeration
- Identify vulnerabilities on target systems
- Conduct password cracking and exploitation
- Analyze network traffic and attacker behavior
- Implement intrusion detection using Snort
- Apply defensive measures using iptables

## Network Setup
- Attacker: Kali Linux (172.16.0.11)
- Targets:
  - 172.16.0.13 (OpenSSH 5.9)
  - 172.16.0.14 (Apache 2.4.18, Samba 3.6.25)

## Tools Used
- Nmap / Zenmap
- Nessus
- Hydra
- Metasploit
- Wireshark
- Snort IDS

## Key Activities

### Reconnaissance
Network scanning identified active hosts and open ports including SSH, HTTP, and SMB services.

### Exploitation
- Performed password cracking using Hydra
- Gained access to target system via FTP
- Navigated directories and identified sensitive files

### Post-Exploitation
- Used `ls -la` to identify hidden files
- Located relevant files within the system

### Detection
Custom Snort rules were created to detect:
- Suspicious HTTP requests (e.g., `/root`)
- SMB traffic on port 445

### Mitigation
- Implemented iptables rules to block malicious traffic
- Prevented further exploitation attempts

## Key Takeaways
- Weak credentials can lead to full system compromise
- Network visibility is critical for detecting attacks
- Intrusion detection systems provide early warning of malicious activity
- Layered defense (detection + prevention) is essential

## Project Structure
- `/report` – full project documentation
- `/screenshots` – evidence of scans, attacks, and detections
- `/snort-rules` – custom detection rules
- `/exploitation` – password cracking and attack steps
