# 🛡️ Wazuh SOC Home Lab

A fully functional Security Operations Center (SOC) home lab built from scratch using Wazuh SIEM. This project simulates a real-world SOC environment — from infrastructure setup to active attack detection and monitoring.

---

## 🧰 Tech Stack & Tools

| Tool | Purpose |
|---|---|
| **Wazuh** | SIEM & XDR Platform |
| **VirtualBox** | Virtualization |
| **Ubuntu Server** | Wazuh Server Host |
| **Kali Linux** | Attack Simulation |
| **Wazuh Dashboard** | Log Analysis & Alerting |

---

## 🏗️ Lab Architecture
```
┌─────────────────────────────────────────┐
│              VirtualBox Host            │
│                                         │
│  ┌─────────────────┐  ┌──────────────┐  │
│  │  Ubuntu Server  │  │  Kali Linux  │  │
│  │  (Wazuh SIEM)   │  │  (Attacker)  │  │
│  │                 │  │              │  │
│  │  - Wazuh Mgr    │  │  - Nmap      │  │
│  │  - Wazuh API    │◄─┤  - Hydra     │  │
│  │  - Dashboard    │  │  - Privesc   │  │
│  └─────────────────┘  └──────────────┘  │
└─────────────────────────────────────────┘
```

---

## 📁 Project Structure
```
wazuh-soc-lab/
├── Phase-1-Setup/
│   └── wazuh-server/        # Wazuh server installation & configuration
├── Phase-2-Wazuh-SIEM/      # SIEM setup, dashboard config, log sources
├── Phase-3-Agent-Connected/ # Agent deployment and enrollment
└── Phase-4-Attack-Detection/# Attack simulations and detection results
```

---

## 📌 Project Phases

### ✅ Phase 1 — Infrastructure Setup
- Installed and configured VirtualBox
- Deployed Ubuntu Server as the Wazuh host
- Installed Wazuh Manager, API, and Dashboard
- Configured network settings for VM communication

### ✅ Phase 2 — Wazuh SIEM Configuration
- Accessed and configured the Wazuh Web Dashboard
- Set up log ingestion and analysis rules
- Configured alerting thresholds and severity levels
- Explored Wazuh modules: FIM, SCA, Vulnerability Detection

### ✅ Phase 3 — Agent Deployment
- Deployed Wazuh Agent on target machine
- Successfully enrolled agent to the Wazuh Manager
- Verified real-time log forwarding and heartbeat
- Confirmed agent visibility on the dashboard

### ✅ Phase 4 — Attack Simulation & Detection
Simulated real-world attacks from Kali Linux and verified detection in Wazuh:

| Attack | Tool Used | Detected by Wazuh |
|---|---|---|
| SSH Brute Force | Hydra | ✅ Yes |
| Network Port Scan | Nmap | ✅ Yes |
| Privilege Escalation | Manual/Scripts | ✅ Yes |

---

## 🎯 Skills Demonstrated

- ✅ SIEM Deployment & Configuration
- ✅ Log Monitoring & Analysis
- ✅ Agent Management
- ✅ Attack Simulation (Red Team basics)
- ✅ Threat Detection & Alerting
- ✅ Network Security Fundamentals
- ✅ Linux Server Administration
- ✅ Virtualization & Lab Setup

---

## 🚀 How to Replicate This Lab

1. Install [VirtualBox](https://www.virtualbox.org/)
2. Set up Ubuntu Server VM and install Wazuh using the [official guide](https://documentation.wazuh.com/current/installation-guide/index.html)
3. Set up Kali Linux VM on the same internal network
4. Deploy Wazuh Agent on the target machine
5. Simulate attacks and observe detections on the dashboard

---

## 📸 Screenshots
<img width="1228" height="592" alt="image" src="https://github.com/user-attachments/assets/39c0d58a-1d47-4680-adaf-aa9e102e7040" />


---



---

## 📜 Disclaimer

This lab is built purely for educational purposes. All attacks were simulated in an isolated virtual environment.
