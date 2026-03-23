# 🏢 Enterprise Security Infrastructure for BlueCoast Retail Group

## 📌 Project Overview

This project simulates a real-world enterprise environment where a growing retail company, **BlueCoast Retail Group**, required a complete upgrade of its IT infrastructure to address security risks, remote access challenges, and lack of monitoring.

The solution was designed and implemented in a virtual lab using industry-standard tools and practices.

---

## 🎯 Objectives

* Build a secure enterprise network infrastructure
* Enable secure remote access for employees
* Implement centralized identity and access management
* Deploy monitoring and SIEM for threat detection
* Protect systems against common cyber threats

---

## 🏗️ Architecture Design

The infrastructure is built using a segmented network:

* Internal Network: `192.168.56.0/24`
* External Access: NAT (VirtualBox)

### Systems Deployed:

| System         | Role                        |
| -------------- | --------------------------- |
| Windows Server | Active Directory, DNS       |
| Ubuntu Server  | Web Server + Security Tools |
| Windows 10     | Client Machine              |
| TrueNAS        | Central Storage             |
| Wazuh          | SIEM & Monitoring           |

📂 Detailed Architecture:
👉 `02_Architecture_Design/Architecture_Explanation.md`

---

## 🧱 Project Implementation

### 1️⃣ Virtual Lab Setup

* Configured VirtualBox environment
* Created isolated internal network
* Assigned static IP addresses

📂 `03_Virtual_Lab_Setup/`

---

### 2️⃣ Identity & Access Management (Active Directory)

* Installed Active Directory Domain Services
* Configured DNS
* Created Organizational Units (OUs)
* Managed users and groups
* Applied Group Policies
* Joined Windows client to domain

📂 `04_Identity_and_Access_Management/`

---

### 3️⃣ Web Server Deployment (LAMP Stack)

* Installed Apache, MySQL, PHP
* Deployed WordPress
* Configured database and permissions

📂 `05_Web_Server_Setup_and_Hardening/`

---

### 4️⃣ Web Server Security Hardening

* Disabled directory listing
* Configured firewall (UFW)
* Installed Fail2Ban (brute-force protection)
* Installed ClamAV (antivirus)

---

### 5️⃣ Secure Storage (TrueNAS)

* Created storage pool and dataset
* Configured SMB share
* Implemented user-based access control

📂 `06_Secure_Storage_NAS/`

---

### 6️⃣ Secure Remote Access (OpenVPN)

* Configured OpenVPN server
* Implemented certificate-based authentication
* Connected client securely
* Verified encrypted communication

📂 `07_Secure_Remote_Access/`

---

### 7️⃣ Security Implementation

* Firewall configuration
* Fail2Ban (attack prevention)
* Snort IDS (network intrusion detection)
* AIDE (file integrity monitoring)
* ClamAV antivirus

📂 `08_Security_Implementation/`

---

### 8️⃣ Monitoring & SIEM (Wazuh)

* Deployed Wazuh SIEM
* Installed agents on all systems
* Collected logs centrally
* Detected failed logins and suspicious activity
* Created custom detection rules

📂 `09_Monitoring_and_SIEM/`

---

### 9️⃣ Centralized Log Management

* Configured Rsyslog server
* Enabled log forwarding from clients
* Implemented log rotation using Logrotate

📂 `10_Log_Management/`

---

## 🧪 Security Testing & Validation

* Simulated brute-force attacks using Kali Linux
* Monitored traffic using Wireshark
* Detected attacks via Snort and Wazuh
* Verified alerts and logs in SIEM

---

## 🔐 Security Features Implemented

* Active Directory (Central Authentication)
* VPN (Secure Remote Access)
* IDS (Snort)
* SIEM (Wazuh)
* Firewall (UFW)
* Brute-force Protection (Fail2Ban)
* File Integrity Monitoring (AIDE)
* Antivirus (ClamAV + Windows Defender)
* Centralized Logging (Rsyslog)

---

## 📊 Key Outcomes

* Built a fully functional enterprise security lab
* Implemented layered security (defense-in-depth)
* Enabled real-time monitoring and detection
* Simulated real-world cyber attack scenarios
* Demonstrated SOC-level skills

---

## 🚀 Skills Demonstrated

* Network Security
* Active Directory Administration
* Linux System Administration
* SIEM & Log Analysis
* Intrusion Detection (Snort)
* VPN Configuration
* Threat Detection & Monitoring

---

## 📸 Screenshots

All implementation screenshots are available in respective folders.

---

## 📌 Conclusion

This project demonstrates the design and implementation of a secure enterprise infrastructure with real-world cybersecurity controls, making it highly relevant for roles in SOC, system administration, and network security.

## Author

Varun Vashisht

SOC Analyst | Cybersecurity
