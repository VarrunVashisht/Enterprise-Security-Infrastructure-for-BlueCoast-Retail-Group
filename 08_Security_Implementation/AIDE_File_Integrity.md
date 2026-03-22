# 🧬 AIDE (File Integrity Monitoring)

## 📌 Overview

AIDE (Advanced Intrusion Detection Environment) was implemented to detect unauthorized file changes.

---

# 🧩 Step 1 — Install AIDE

```bash
sudo apt install aide -y
```

## 🎯 Purpose

* Installs file integrity monitoring tool

---

# 🧩 Step 2 — Initialize Database

```bash
sudo aideinit
```

📸 Screenshot:

<img width="838" height="93" alt="image" src="https://github.com/user-attachments/assets/9cda1119-4bab-4c42-b857-b13774ce7b48" />

## 🎯 Purpose

* Creates baseline snapshot of system files
* Used for comparison

---

# 🧩 Step 3 — Verify Database

```bash
sudo ls -lh /var/lib/aide/
```

📸 Screenshot:

<img width="653" height="55" alt="image" src="https://github.com/user-attachments/assets/7ff3eeca-ffb6-4b28-a670-f1f8f22d3643" />

---

# 🧩 Step 4 — Run Integrity Check

```bash
sudo aide --check
```

## 🎯 Purpose

* Detects file changes
* Identifies tampering

--

# 🧪 Test Change

```bash
sudo nano /etc/cron.daily/aide
```

Then re-run:

```bash
sudo aide --check
```

---

# ✅ Outcome

* Unauthorized file changes detected
* System integrity monitored

---
