# 🛡️ Snort IDS (Intrusion Detection System)

## 📌 Overview

Snort was deployed as a Network Intrusion Detection System (IDS) to monitor traffic and detect malicious activity in real time.

---

# 🧩 Step 1 — Install Snort

```bash
sudo apt install snort -y
```

## 🎯 Purpose

* Installs network IDS
* Enables traffic monitoring

---

# 🧩 Step 2 — Verify Installation

```bash
snort -V
```

📸 Screenshot:

<img width="953" height="217" alt="image" src="https://github.com/user-attachments/assets/5623e14c-27e9-416f-b70a-ad8585baad0e" />


## 🎯 Purpose

* Confirms installation
* Displays version

---

# 🧩 Step 3 — Configure Network

```bash
sudo nano /etc/snort/snort.conf
```

Find:

```bash
ipvar HOME_NET any
```

Change to:

```bash
ipvar HOME_NET 192.168.56.0/24
```

## 🎯 Purpose

* Defines internal network
* Ensures Snort monitors your lab environment

📸 Screenshot:
<img width="618" height="280" alt="image" src="https://github.com/user-attachments/assets/23c4dc2b-606b-4418-9b5b-924e5dd596ad" />


---

# 🧩 Step 4 — Add Detection Rule

```bash
sudo nano /etc/snort/rules/local.rules
```

Add:

```bash
alert tcp any any -> any 22 (msg:"SSH Brute Force Attempt"; sid:1000001;)
```

## 🎯 Purpose

* Detects SSH brute-force attempts
* Generates alerts

📸 Screenshot:

<img width="1031" height="328" alt="image" src="https://github.com/user-attachments/assets/8c2841a1-859f-4289-88eb-6b2b03fc55c0" />


---

# 🧩 Step 5 — Run Snort

```bash
sudo snort -A console -q -c /etc/snort/snort.conf -i enp0s3
```

## 🎯 Purpose

* Runs Snort in live monitoring mode
* Displays alerts in real time

---

# 🧪 Test Attack (Kali Linux)

```bash
hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://192.168.56.20
```

## 🎯 Purpose

* Simulates brute-force attack
* Validates IDS detection

---

# ✅ Outcome

* Snort detects malicious activity
* Real-time alerts generated

---
