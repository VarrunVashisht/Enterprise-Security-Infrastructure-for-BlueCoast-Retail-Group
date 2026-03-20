# 🏗️ Architecture Design – BlueCoast Retail Group

## 📌 Overview

This project simulates a secure enterprise network for BlueCoast Retail Group using a virtual lab environment. The architecture is designed to replicate real-world infrastructure by integrating identity management, web services, secure storage, monitoring, and attack simulation systems.

The design follows a layered security approach and ensures separation between internal and external network communication.

---

## 🌐 Network Design

The environment is built using two network types:

### 🔒 Internal Network (Host-Only)

* Network Range: **192.168.56.0/24**
* Purpose: Secure communication between internal machines
* No direct exposure to the internet

### 🌍 External Network (NAT)

* Provides internet access for updates and package installation
* Controlled connectivity outside the lab

---

## 🖥️ System Architecture & IP Plan

| System              | Role                                                   | IP Address    |
| ------------------- | ------------------------------------------------------ | ------------- |
| Windows Server 2025 | Active Directory, DNS, Domain Controller               | 192.168.56.10 |
| Ubuntu Server       | Web Server (Apache, MySQL, WordPress) + Security Tools | 192.168.56.20 |
| Windows 10          | Domain Client Machine                                  | 192.168.56.11 |
| Kali Linux          | Attack Simulation (Pen Testing)                        | 192.168.56.30 |
| TrueNAS             | Network Storage (SMB Shares)                           | 192.168.56.50 |
| Wazuh SIEM          | Log Monitoring & Threat Detection                      | 192.168.56.40 |

---

## 🔐 Security Architecture

The infrastructure is designed using a **defense-in-depth strategy**:

* **Identity Layer:** Active Directory (Windows Server)
* **Network Layer:** Firewall rules + Snort IDS
* **Endpoint Protection:** Windows Defender + ClamAV
* **Monitoring Layer:** Wazuh SIEM
* **Access Layer:** OpenVPN for secure remote access
* **Integrity Monitoring:** AIDE (Linux)

---

## 🔄 Data Flow

1. Users authenticate via Active Directory (Windows Server)
2. Clients (Windows 10) access internal services and web server (Ubuntu)
3. Logs from all systems are forwarded to Wazuh SIEM
4. Security tools continuously monitor activity
5. Attack simulations from Kali Linux are detected and logged

---

## 🎯 Design Justification

This architecture was designed to:

* Simulate a real enterprise IT environment
* Enable safe attack testing in an isolated network
* Implement layered security controls
* Provide centralized monitoring and visibility
* Demonstrate real-world cybersecurity practices

---

## ✅ Conclusion

The architecture provides a secure, scalable, and practical environment to implement and test enterprise-level security controls, making it suitable for demonstrating real-world cybersecurity skills.
