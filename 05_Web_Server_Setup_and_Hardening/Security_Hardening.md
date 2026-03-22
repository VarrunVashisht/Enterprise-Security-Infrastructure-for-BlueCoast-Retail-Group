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


### Snapshot:
<img width="1363" height="908" alt="wordpress-live-website" src="https://github.com/user-attachments/assets/070558c3-2aeb-4ac5-80c4-7715674ad338" />
<img width="845" height="731" alt="wordpress-website-configuration" src="https://github.com/user-attachments/assets/c2f3c5b4-aa32-4b1e-a03e-b562d862ae13" />
<img width="830" height="541" alt="wordpress-database-installed-configured" src="https://github.com/user-attachments/assets/c174868b-6d73-46a8-be7a-fc998fc98ecd" />



