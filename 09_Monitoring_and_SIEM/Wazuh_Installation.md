# 📊 Wazuh SIEM Deployment & Overview (Dedicated VM)

## 📌 Overview

Wazuh was deployed on a dedicated Ubuntu virtual machine to function as a centralized **Security Information and Event Management (SIEM)** system within the BlueCoast Retail Group infrastructure.

The SIEM plays a critical role in:

* Collecting logs from all systems
* Detecting security threats in real-time
* Providing centralized visibility across the network
* Supporting incident detection and response

This setup simulates a real-world **Security Operations Center (SOC)** environment.

---

# 🧩 Step 1 — Prepare SIEM Virtual Machine

## ⚙️ VM Configuration

A dedicated VM was created specifically for Wazuh to ensure:

* Isolation from other systems
* Better performance and monitoring
* Realistic enterprise architecture

### Network Configuration

* Adapter 1 → NAT (Internet access)
* Adapter 2 → Host-Only (Internal communication)

---

## 🌐 Static IP Assignment

```bash
192.168.56.122
```

### 🎯 Why Static IP?

* Required for agents to connect reliably
* Ensures consistent communication across infrastructure
* Critical for SIEM and monitoring tools

---


📸 Screenshot:
<img width="965" height="618" alt="image" src="https://github.com/user-attachments/assets/d24488ee-8a7a-440b-a62f-81eae036c7f4" />

📸 Screenshot (Active Status):
<img width="688" height="599" alt="image" src="https://github.com/user-attachments/assets/0c45dec9-3674-474c-8fd9-1353f7d5cf6b" />


---

# 🧩 Step 2 — System Update

## ⚙️ Command

```bash
sudo apt update && sudo apt upgrade -y
```

### 🎯 Purpose

* Updates package lists
* Installs latest security patches
* Prevents compatibility issues during installation

---

# 🧩 Step 3  — Access Wazuh Dashboard

## 🌐 URL

* From Windows 10 (Client Machine)
```bash
https://192.168.56.122
```

📸 Screenshot (Wazuh Dashboard):
<img width="1212" height="846" alt="image" src="https://github.com/user-attachments/assets/9820b586-fa21-4575-9e8e-e92112abd6f7" />

---








