# 🚫 Fail2Ban (Brute-Force Protection)

## 📌 Overview

Fail2Ban was implemented to detect and block brute-force login attempts by monitoring authentication logs and banning malicious IP addresses.

---

# 🧩 Step 1 — Install Fail2Ban

```bash
sudo apt install fail2ban -y
```

## 🎯 Purpose

* Installs intrusion prevention tool
* Monitors login attempts

📸 Screenshot:

<img width="702" height="195" alt="image" src="https://github.com/user-attachments/assets/52b02fc9-c045-4a16-b3ae-9570a6178c8b" />


---

# 🧩 Step 2 — Start & Enable Service

```bash
sudo systemctl start fail2ban
sudo systemctl enable fail2ban
```

## 🎯 Purpose

* Starts protection immediately
* Ensures auto-start on reboot

---

# 🧩 Step 3 — Verify Status

```bash
sudo systemctl status fail2ban
sudo fail2ban-client status
```

## 🎯 Purpose

* Confirms service is active
* Shows monitored services (jails)

📸 Screenshot:

<img width="1229" height="189" alt="image" src="https://github.com/user-attachments/assets/4d9498c5-f23c-4555-8c14-1d73c7ee9669" />

<img width="1854" height="390" alt="image" src="https://github.com/user-attachments/assets/97ee510d-80cc-4c09-a78b-de2cf09c71d9" />

---

# 🧩 Step 4 — Check SSH Protection

```bash
sudo fail2ban-client status sshd
```

📸 Screenshot:
<img width="750" height="225" alt="image" src="https://github.com/user-attachments/assets/03627b3d-68c4-452d-a1b2-e1949a216aa1" />

## 🎯 Purpose

* Displays banned IPs
* Confirms SSH protection active

---

# ✅ Outcome

* Brute-force attacks automatically blocked
* Malicious IPs banned dynamically

---
