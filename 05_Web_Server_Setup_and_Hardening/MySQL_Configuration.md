# 🗄️ MySQL Installation & Configuration

## 📌 Overview

MySQL was installed to manage the backend database required for dynamic web applications like WordPress.

---

## ⚙️ Commands & Purpose

### 📦 Install MySQL Server

```bash
sudo apt install mysql-server -y
```

**Why:**

* Installs MySQL database engine
* Required for storing website data

---

### 🔐 Secure MySQL Installation

```bash
sudo mysql_secure_installation
```

**Why:**

* Removes insecure default settings
* Sets root password
* Disables remote root login
* Removes test databases

---

### 🔍 Verify MySQL Status

```bash
sudo systemctl status mysql
```

**Why:**

* Ensures MySQL service is running properly

---

## 🎯 Purpose in Project

MySQL is used for:

* Storing WordPress data (users, posts, settings)
* Supporting dynamic content generation

---

## ✅ Outcome

MySQL is securely installed and ready for database operations.



# Snapshot

<img width="877" height="459" alt="mysql-installed-active" src="https://github.com/user-attachments/assets/66b5be96-d037-4e02-b5e6-6b6fb674b8f0" />
