# Saturn Network Security Analysis

## Overview
This project simulates a real-world internal network security assessment using Kali Linux to identify, exploit, detect, and mitigate vulnerabilities within a controlled lab environment.

---

## Attack Workflow Overview
![Attack Flowchart](screenshots/attack-flowchart-overview.png)
This diagram illustrates the end-to-end attack lifecycle, from reconnaissance to full system compromise and detection.

---

## Network Setup
- Attacker: Kali Linux (172.16.0.11)
- Targets:
  - 172.16.0.13 (FTP, SSH, SMB)
  - 172.16.0.14 (HTTP, SMB)

---

## Tools Used
- Nmap / Zenmap
- Searchsploit
- Hydra
- Metasploit
- Wireshark
- Snort IDS

---

## 1. Reconnaissance
Network scanning identified active hosts and exposed services.

![Nmap Scan](screenshots/nmap-scan-172.16.0.13.png)

---

## 2. Vulnerability Identification
Searchsploit was used to identify known vulnerabilities in OpenSSH and Samba services.
![Searchsploit Results](screenshots/vulnerability-search-SAMBA.png)


---

## 3. Exploitation (Credential Attack)
A password attack using Hydra successfully compromised user credentials.

![Hydra Password Crack](screenshots/hydra-password-crack-success.png)

---

## 4. Access & Data Exfiltration
Using compromised credentials, FTP access was obtained and sensitive files were discovered and downloaded.

![FTP Login](screenshots/ftp-login-success.png)

![Data Exfiltration](screenshots/ftp-data-exfiltration.png)

---

## 5. Exploitation Attempt (Metasploit)
An attempt was made to exploit a known Samba vulnerability using Metasploit.  
No session was established, likely due to environmental constraints, demonstrating the need for alternative attack paths.

![Metasploit Attempt](screenshots/metasploit-exploit-attempt-samba.png)

---

## 6. Detection (Snort IDS)
Custom Snort rules were created to detect SMB-based attacks. Alerts were successfully triggered during attack simulation.

![Snort Alert](screenshots/snort-alert-smb-detection.png)

Custom rules used in this project can be found in the `/snort-rules/snort-rules.txt` file.

---

## 7. Traffic Analysis (Wireshark)
Network traffic analysis confirmed SMB communication and attack-related activity.

![Wireshark Analysis](screenshots/wireshark-smb-traffic-analysis.png)

---

## Key Takeaways
- Weak credentials can lead to full system compromise
- Multiple attack paths may be required when exploits fail
- Intrusion Detection Systems (Snort) provide visibility into malicious activity
- Network traffic analysis is critical for understanding attack behavior
- Layered security (attack + detection + analysis) is essential

---

## Project Structure 
- `/report` – full project documentation
- `/screenshots` – evidence of scans, attacks, and detections
- `/snort-rules` – custom detection rules
- `/exploitation` – password cracking and attack steps
