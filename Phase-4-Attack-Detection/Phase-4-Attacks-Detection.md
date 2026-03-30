## Attack Scenarios & Detection

1.SSH Brute Force Attack (Hydra)

Description:

A brute-force attack was simulated using Hydra from Kali Linux targeting the SSH service on the Ubuntu agent system.

Command Used:

"hydra -l socuser -P pass.txt ssh://192.168.1.43"

![Hydra Attack](Screenshots/Hydra%20attack.png)

Observations:

Multiple failed login attempts were generated.
Logs showed repeated "Failed password" entries.
Source IP (192.168.1.39) identified as attacker.
Wazuh Detection:
Logs collected from /var/log/auth.log
Alerts showed authentication failures via SSH
Events categorized under sshd
MITRE ATT&CK Mapping:
Technique: T1110 – Brute Force
Tactic: Credential Access

![Wazuh Hydra Detection](Screenshots/Wazuh-hydra%20detection.png)

2. Network Scanning Attack (Nmap)

Description:

An Nmap scan was performed to identify open ports and services on the target system.

Command Used:

nmap -A 192.168.1.45

![Nmap Scan](Screenshots/Kali%20nmap%20attack.png)

Observations:

Port 22 (SSH) was found open.
Service version (OpenSSH 8.9p1) detected.
OS identified as Linux (Ubuntu).
Security Impact:
Reveals system vulnerabilities and attack surface.
Helps attackers plan targeted attacks such as brute-force or exploitation.

Wazuh Detection:

Limited detection due to absence of firewall logging.
Demonstrates importance of enabling network-level logging.
MITRE ATT&CK Mapping:
Technique: T1046 – Network Service Discovery
Technique: T1595 – Active Scanning

3 Privilege Escalation Attack (Sudo Abuse)

Description:

Privilege escalation was simulated by executing sudo commands to gain root access from a normal user account.

Commands Used:

"sudo -l"
"sudo su"

![Privilege Escalation](Screenshots/Privilege%20Escalation.png)

Observations:

User socuser had full administrative privileges.
Successful switch to root user was achieved.
Wazuh Detection:
Logs recorded sudo command execution.
Privileged access activity captured in system logs.
Events associated with PAM and sudo usage.

![Wazuh Sudo Activity](Screenshots/wazuh-sudo%20activity.png)

4. Results
Wazuh successfully detected SSH brute-force attacks in real-time.
Privilege escalation activities were logged and monitored effectively.
Network scanning highlighted reconnaissance risks and logging limitations.
The system demonstrated strong log collection, correlation, and visualization capabilities.

## Conclusion

The project successfully implemented a SOC environment using Wazuh SIEM and demonstrated its ability to detect multiple types of cyberattacks. The system effectively monitored authentication failures, privilege escalation attempts, and system activities. This project highlights the importance of centralized logging and real-time monitoring in cybersecurity operations.