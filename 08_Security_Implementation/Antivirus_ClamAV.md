# 🦠 ClamAV Antivirus

## 📌 Overview

ClamAV was deployed to detect malware and malicious files within the system, particularly in the web server directory.

---

# 🧩 Step 1 — Install ClamAV

```bash
sudo apt install clamav -y
```

## 🎯 Purpose

* Installs antivirus engine

📸 Screenshot:
<img width="807" height="112" alt="image" src="https://github.com/user-attachments/assets/794e4393-dcdd-4af9-bf2b-5ee8782df452" />


---

# 🧩 Step 2 — Update Virus Database

```bash
sudo freshclam
```

## 🎯 Purpose

* Downloads latest virus definitions
* Ensures accurate detection

---

📸 Screenshot:
<img width="1318" height="213" alt="image" src="https://github.com/user-attachments/assets/90214fd6-f5e0-44ae-8199-c3cb8d438287" />


# 🧩 Step 3 — Scan System

```bash
sudo clamscan -r /var/www
```

## 🎯 Purpose

* Scans web directory
* Detects malicious files

---

# 🧩 Step 4 — Verify Version

```bash
clamscan --version
```

---

# ✅ Outcome

* System scanned for malware
* No threats detected (or identified threats removed)

---
