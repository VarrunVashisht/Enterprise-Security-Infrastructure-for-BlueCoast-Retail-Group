# 📊 Wazuh SIEM Installation (Separate VM)

## 📌 Overview

Wazuh was deployed on a dedicated Ubuntu VM to act as a Security Information and Event Management (SIEM) system.

This server collects logs, detects threats, and provides real-time monitoring across the enterprise infrastructure.

---

# 🧩 Step 1 — Prepare New VM

## Configuration:

* Network:

  * Adapter 1 → NAT
  * Adapter 2 → Host-Only

Assign IP:

```bash
192.168.56.122
```

---

📸 Screenshot:
<img width="965" height="618" alt="image" src="https://github.com/user-attachments/assets/d24488ee-8a7a-440b-a62f-81eae036c7f4" />

📸 Screenshot (Active Status):
<img width="688" height="599" alt="image" src="https://github.com/user-attachments/assets/0c45dec9-3674-474c-8fd9-1353f7d5cf6b" />

---

# 🧩 Step 2 — Update System

```bash
sudo apt update && sudo apt upgrade -y
```

---

# 🧩 Step 3 — Install Wazuh (All-in-One)

```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a
```

---

## 🎯 Purpose

* Installs:

  * Wazuh Manager
  * Elasticsearch
  * Dashboard (Kibana)

---

---

# 🧩 Step 4 — Get Login Credentials

After install:

```bash
sudo tar -xvf wazuh-install-files.tar
```

---

## Default:

```bash
Username: admin
Password: (shown in output)
```

---

📸 Screenshot:
`Screenshots/wazuh-credentials.png`

---

# 🧩 Step 5 — Access Dashboard

Open browser:

```bash
https://192.168.56.60
```

---

## Accept certificate warning

Login with:

* admin
* password

---

📸 Screenshot:
`Screenshots/wazuh-dashboard.png`

---

# ✅ Outcome

* Wazuh SIEM installed
* Dashboard accessible
* Ready to receive logs

---
