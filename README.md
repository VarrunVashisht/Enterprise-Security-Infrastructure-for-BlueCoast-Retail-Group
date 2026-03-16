# 🏢 Enterprise Security Infrastructure for BlueCoast Retail Group

---

## 📌 Project Overview

BlueCoast Retail Group is a rapidly expanding retail and e-commerce organization experiencing significant growth in online transactions, customer base, and remote workforce adoption.

With this growth, the company’s legacy IT infrastructure became increasingly inadequate, exposing the organization to multiple cybersecurity risks and operational inefficiencies.

### ⚠️ Key Business Challenges

The organization faced the following critical issues:

* ❌ **Unsecured Remote Access**

  * Employees accessed internal systems using unsafe methods without encryption or authentication controls.

* ❌ **Outdated Infrastructure**

  * Legacy systems lacked modern security hardening, patching, and monitoring.

* ❌ **Lack of Centralized Identity Management**

  * No structured user management, leading to weak access control and privilege misuse.

* ❌ **Increased Attack Surface**

  * Public-facing web applications were vulnerable to brute-force, malware, and DoS attacks.

* ❌ **No Centralized Monitoring or Logging**

  * Security incidents were not detected or responded to in real-time.

* ❌ **Risk of Data Breaches & Service Downtime**

  * Absence of backup strategies and intrusion detection increased business risk.

---

## 🎯 Project Objective

The goal of this project is to design, implement, and secure a **realistic enterprise IT infrastructure** within a controlled virtual lab environment.

This project simulates a real-world corporate environment and demonstrates practical cybersecurity skills aligned with industry expectations.

### 🎯 Key Objectives

* 🔐 Establish **secure remote access** for employees using VPN
* 🧑‍💼 Implement **centralized identity and access management** using Active Directory
* 🌐 Deploy and harden a **production-ready web server**
* 🛡️ Integrate **multi-layered security controls**
* 📊 Enable **real-time monitoring, alerting, and incident detection**
* 💾 Implement **data protection, backup, and recovery mechanisms**
* 🧪 Simulate real-world cyberattacks and validate defenses

---

## 🏗️ Solution Architecture

The infrastructure was designed using a **multi-tier architecture model**:

### 🔹 Core Layers

1. **Identity Layer**

   * Windows Server acting as Domain Controller (Active Directory + DNS)

2. **Application Layer**

   * Ubuntu Server hosting Apache, MySQL, and WordPress

3. **Security Layer**

   * IDS/IPS (Snort), SIEM (Wazuh), Fail2Ban, ClamAV

4. **Storage Layer**

   * TrueNAS for secure file storage and sharing

5. **Client & Attack Simulation Layer**

   * Windows 10 (legitimate user)
   * Kali Linux (attacker simulation)

---

## 🧱 Infrastructure Components

| System                  | Role              | Description                                      |
| ----------------------- | ----------------- | ------------------------------------------------ |
| **Windows Server 2025** | Domain Controller | Manages Active Directory, DNS, Group Policies    |
| **Ubuntu Server**       | Web Server        | Hosts WordPress-based e-commerce platform        |
| **Windows 10**          | Client Machine    | Simulates employee workstation                   |
| **Kali Linux**          | Attack Machine    | Used for penetration testing & attack simulation |
| **TrueNAS**             | Storage Server    | Provides secure shared storage with SMB          |
| **Wazuh SIEM**          | Monitoring Server | Centralized logging, threat detection & alerting |

---

## 🌐 Network Design

The lab environment was implemented using **Oracle VirtualBox** with the following network segmentation:

* **NAT Adapter**

  * Provides internet access for updates and package installation

* **Host-Only Adapter**

  * Enables secure internal communication between virtual machines

* **Isolated Lab Environment**

  * Ensures safe testing of attacks without impacting external networks

---

## 🔐 Security Implementations

A **defense-in-depth strategy** was applied by implementing multiple security layers:

### 🛡️ Network Security

* Firewall configuration (UFW & Windows Firewall)
* Network segmentation
* DoS protection mechanisms

### 🔍 Threat Detection & Monitoring

* **Snort (IDS/IPS)** for real-time intrusion detection
* **Wazuh SIEM** for centralized logging and alert correlation

### 🔑 Access Control & Authentication

* Active Directory (User & Group Management)
* Group Policy Objects (GPO)
* Multi-Factor Authentication (2FA)

### 🚫 Attack Prevention

* **Fail2Ban** to block brute-force attacks
* Secure SSH and RDP configurations

### 🧬 Integrity & Malware Protection

* **AIDE** for file integrity monitoring
* **ClamAV** for malware scanning
* Windows Defender for endpoint protection

### 🌐 Secure Communication

* OpenVPN for encrypted remote access
* HTTPS readiness (optional extension)

### 📦 Data Protection

* TrueNAS secure shared storage
* Windows Server Backup configuration

---

## 🧪 Testing & Validation

To validate the effectiveness of the implemented controls, multiple real-world attack scenarios were simulated:

### 🔴 Attack Simulations

* **Brute-force Attack**

  * Tool: Hydra (Kali Linux)
  * Target: SSH service on Ubuntu Server
  * Result: Blocked via Fail2Ban and detected by Snort

* **Network Traffic Analysis**

  * Tool: Wireshark
  * Captured and analyzed suspicious packets

* **Log Monitoring**

  * Verified alerts in Wazuh SIEM dashboard

* **File Integrity Testing**

  * Modified system files to trigger AIDE alerts

* **Central Logging**

  * RSyslog used to collect logs from multiple machines

---

## 📊 Tools & Technologies Used

| Category               | Tools                                          |
| ---------------------- | ---------------------------------------------- |
| Virtualization         | Oracle VirtualBox                              |
| Operating Systems      | Windows Server, Ubuntu, Windows 10, Kali Linux |
| Monitoring             | Wazuh SIEM                                     |
| IDS/IPS                | Snort                                          |
| Network Analysis       | Wireshark                                      |
| Vulnerability Scanning | OpenVAS                                        |
| File Integrity         | AIDE                                           |
| Malware Protection     | ClamAV                                         |
| Remote Access          | OpenVPN                                        |
| Logging                | RSyslog, Logrotate                             |

---

## 📦 Final Outcome

This project successfully delivers a **fully functional enterprise cybersecurity lab**, demonstrating:

* ✅ Secure infrastructure design and deployment
* ✅ Implementation of layered security controls
* ✅ Real-world attack detection and mitigation
* ✅ Centralized monitoring and incident response
* ✅ Practical experience with industry-standard tools

---

## 🚀 Key Learning Outcomes

* Hands-on experience with enterprise infrastructure setup
* Deep understanding of defense-in-depth strategy
* Real-world SOC (Security Operations Center) exposure
* Practical knowledge of attack simulation and detection
* Strong foundation for cybersecurity roles (SOC Analyst, Security Engineer)

---

## 📁 Project Documentation

Detailed implementation steps, configurations, and screenshots are available in the respective folders within this repository.

---

## ⚠️ Disclaimer

This project was conducted in a **controlled virtual lab environment** for educational purposes only.
All attack simulations were performed ethically and legally within isolated systems.

---

## Author

Varrun Vashisht

Experienced in: Cybersecurity | Data Analytics 
