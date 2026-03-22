# 🔥 Firewall Configuration (UFW)

## 📌 Overview

UFW (Uncomplicated Firewall) was configured on the Ubuntu server to control inbound and outbound network traffic. This ensures that only authorized services are accessible, reducing the attack surface.

---

# 🧩 Step 1 — Install UFW

```bash
sudo apt update
sudo apt install ufw -y
```

## 🎯 Purpose

* Installs firewall utility
* Prepares system for network access control

📸 Screenshot:

<img width="792" height="457" alt="image" src="https://github.com/user-attachments/assets/bc7ddcc4-322b-411a-8a60-2c7d93fdef74" />


---

# 🧩 Step 2 — Allow Required Services

```bash
sudo ufw allow OpenSSH
sudo ufw allow 'Apache Full'
```

## 🎯 Purpose

| Command     | Why                          |
| ----------- | ---------------------------- |
| OpenSSH     | Allows remote administration |
| Apache Full | Allows HTTP/HTTPS traffic    |

---

# 🧩 Step 3 — Enable Firewall

```bash
sudo ufw enable
```

## 🎯 Purpose

* Activates firewall rules
* Blocks all other unauthorized traffic

---

# 🧩 Step 4 — Verify Status

```bash
sudo ufw status verbose
```

## 🎯 Purpose

* Confirms firewall is active
* Displays allowed ports and rules

📸 Screenshot:

<img width="758" height="247" alt="image" src="https://github.com/user-attachments/assets/52ecb8f2-33e5-4137-ae7a-da9ad1b9b3d2" />


---

# ✅ Outcome

* Firewall enabled
* Only required ports allowed
* Unauthorized access blocked

---
