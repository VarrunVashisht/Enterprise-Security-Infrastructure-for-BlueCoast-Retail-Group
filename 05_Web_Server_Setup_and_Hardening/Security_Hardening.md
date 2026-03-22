# 🔐 Web Server Security Hardening

## 📌 Overview

Security hardening was applied to protect the web server from common threats such as brute-force attacks, unauthorized access, and malware.

---

## ⚙️ Commands & Purpose

### 🚫 Disable Directory Listing

```bash
sudo nano /var/www/html/.htaccess
```

Add:

```
Options -Indexes
```

**Why:**

* Prevents attackers from viewing directory contents
* Reduces information disclosure risk

---

### 🛡️ Install Fail2Ban

```bash
sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
```

**Why:**

* Monitors login attempts
* Blocks IPs performing brute-force attacks

---

### 🔥 Configure Firewall (UFW)

```bash
sudo apt install ufw -y
sudo ufw allow OpenSSH
sudo ufw allow 'Apache Full'
sudo ufw enable
```

**Why:**

* Controls incoming traffic
* Allows only required services (SSH & HTTP/HTTPS)

---

### 🦠 Install ClamAV Antivirus

```bash
sudo apt install clamav -y
sudo freshclam
sudo clamscan -r /var/www
```

**Why:**

* Detects malware in web files
* Updates virus definitions
* Performs full system scan

---

## 🎯 Purpose in Project

Security hardening ensures:

* Protection against common web attacks
* Reduced attack surface
* Improved system integrity

---

## ✅ Outcome

The web server is secured using multiple defensive layers including firewall, intrusion prevention, and malware detection.

## Screenshot:
<img width="810" height="572" alt="wordpress-disable-directory-listing-htaccess" src="https://github.com/user-attachments/assets/af997807-f3a0-42dd-9f73-3c18668b63ae" />

<img width="1189" height="429" alt="wordpress-fail2ban-status" src="https://github.com/user-attachments/assets/10983ae8-bd0d-45d9-8944-0cec0aada589" />

<img width="823" height="295" alt="wordpress-ufw-status" src="https://github.com/user-attachments/assets/b7cac29f-8f32-448d-a125-aa9e22192b23" />

<img width="403" height="220" alt="clamav-scan" src="https://github.com/user-attachments/assets/e5b7e7ab-2a17-4aab-89a7-5336f07844b9" />




