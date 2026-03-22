# 🌐 Apache Installation & Configuration

## 📌 Overview

Apache was installed on the Ubuntu server to host the company’s web application. It acts as the front-facing web service handling HTTP requests.

---

## ⚙️ Step-by-Step Commands & Purpose

### 🔄 Update System Packages

```bash
sudo apt update
sudo apt upgrade -y
```

**Why:**

* Ensures all packages are up-to-date
* Prevents compatibility issues during installation

---

### 📦 Install Apache

```bash
sudo apt install apache2 -y
```

**Why:**

* Installs Apache web server
* Required to serve web pages over HTTP

---

### ▶️ Start and Enable Apache

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```

**Why:**

* Starts Apache service immediately
* Enables Apache to start automatically on boot

---

### 🔍 Verify Apache Status

```bash
sudo systemctl status apache2
```

**Why:**

* Confirms Apache is running without errors

---

### 🌐 Test Web Server

Open browser:
http://192.168.56.20

**Why:**

* Verifies Apache is accessible from network
* Confirms successful installation

---

## 🎯 Purpose in Project

Apache serves as:

* Web hosting platform
* Entry point for users accessing the website
* Base for deploying WordPress application

---

## ✅ Outcome

Apache is successfully installed, running, and accessible over the network.


## 🌍 Snapshot

<img width="872" height="395" alt="apache-installed-active" src="https://github.com/user-attachments/assets/86097e87-d09e-4460-b378-d04dc7654591" />

Accessed web server using:
http://192.168.56.20

<img width="1108" height="696" alt="apache-installed-active-2" src="https://github.com/user-attachments/assets/9b9e6ae3-494f-4c78-8c14-65dd40160707" />

---

## ✅ Outcome

Apache is successfully installed and serving web content.

