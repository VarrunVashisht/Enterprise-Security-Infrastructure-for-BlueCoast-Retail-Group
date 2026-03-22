# 📰 WordPress Deployment

## 📌 Overview

WordPress was deployed as the web application for BlueCoast Retail Group to simulate a real-world e-commerce environment.

---

## ⚙️ Commands & Purpose

### 🗄️ Create Database & User

```bash
sudo mysql -u root -p
```

```sql
CREATE DATABASE wordpress;
CREATE USER 'wpuser'@'localhost' IDENTIFIED BY 'P@ssw0rd2025!';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wpuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

**Why:**

* Creates a dedicated database for WordPress
* Ensures secure database access using a specific user

---

### 📥 Download WordPress

```bash
cd /tmp
wget https://wordpress.org/latest.tar.gz
tar -xvzf latest.tar.gz
```

**Why:**

* Downloads latest WordPress package
* Extracts installation files

---

### 📂 Move Files to Web Directory

```bash
sudo cp -r wordpress/* /var/www/html/
```

**Why:**

* Places WordPress files in Apache root directory
* Makes website accessible via browser

---

### 🔐 Set Permissions

```bash
sudo chown -R www-data:www-data /var/www/html/
sudo chmod -R 755 /var/www/html/
```

**Why:**

* Assigns correct ownership to Apache user
* Ensures secure file access and execution

---

### 🔄 Restart Apache

```bash
sudo systemctl restart apache2
```

**Why:**

* Applies configuration changes
* Ensures WordPress loads correctly

---

### 🌐 Access WordPress

http://192.168.56.20

**Why:**

* Completes installation via browser interface

---

## 🎯 Purpose in Project

WordPress simulates:

* Real-world web application
* Business website environment
* Target system for security testing

---

## ✅ Outcome

WordPress is successfully deployed and accessible.





### Snapshot:
<img width="1363" height="908" alt="wordpress-live-website" src="https://github.com/user-attachments/assets/070558c3-2aeb-4ac5-80c4-7715674ad338" />
<img width="845" height="731" alt="wordpress-website-configuration" src="https://github.com/user-attachments/assets/c2f3c5b4-aa32-4b1e-a03e-b562d862ae13" />
<img width="830" height="541" alt="wordpress-database-installed-configured" src="https://github.com/user-attachments/assets/c174868b-6d73-46a8-be7a-fc998fc98ecd" />
