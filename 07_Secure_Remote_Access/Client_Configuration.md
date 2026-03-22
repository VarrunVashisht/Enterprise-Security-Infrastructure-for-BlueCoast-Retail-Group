# 💻 OpenVPN Client Configuration (Complete Setup)

## 📌 Overview

This section covers the configuration of the OpenVPN client to securely connect a Windows machine to the internal enterprise network (192.168.56.0/24).

The client uses certificate-based authentication and an encrypted tunnel to securely access internal systems.

---

# 🧩 Step 1 — Create Client Configuration File

```bash
nano ~/easy-rsa/client1.ovpn
```

---

## 🎯 Purpose

This file defines:

* VPN server address
* Connection method
* Encryption settings
* Authentication mechanism

---

# 🧩 Step 2 — Add Base Configuration

Paste the following:

```bash
client
dev tun
proto udp
remote 192.168.56.20 1194

resolv-retry infinite
nobind
persist-key
persist-tun

cipher AES-256-CBC

verb 3
```

---

## 🎯 Why This is Required

| Setting   | Purpose                        |
| --------- | ------------------------------ |
| remote    | Defines VPN server IP          |
| proto udp | Faster VPN communication       |
| dev tun   | Secure routed tunnel           |
| cipher    | Encryption standard            |
| persist   | Maintains connection stability |

---

# 🧩 Step 3 — Embed Certificates (CRITICAL STEP)

Add the following at the **end of the same file**:

```bash
<ca>
-----BEGIN CERTIFICATE-----
PASTE YOUR ca.crt CONTENT HERE
-----END CERTIFICATE-----
</ca>

<cert>
-----BEGIN CERTIFICATE-----
PASTE YOUR client1.crt CONTENT HERE
-----END CERTIFICATE-----
</cert>

<key>
-----BEGIN PRIVATE KEY-----
PASTE YOUR client1.key CONTENT HERE
-----END PRIVATE KEY-----
</key>
```

---

## 🎯 Purpose

* Provides client identity
* Enables secure authentication
* Encrypts communication
* Makes file portable (single file setup)

---

# 🧩 Step 4 — Extract Certificate Data

### 🔐 Get CA Certificate

```bash
cat ~/easy-rsa/pki/ca.crt


<img width="1048" height="884" alt="image" src="https://github.com/user-attachments/assets/4fb23864-7e3d-4e25-a8df-c836cf6e58f3" />

```

### 🔐 Get Client Certificate

```bash
cat ~/easy-rsa/pki/issued/client1.crt


<img width="831" height="444" alt="image" src="https://github.com/user-attachments/assets/a619c9b8-0378-4406-ae2a-40b4c49f260b" />

```

---

### 🔐 Get Client Key

```bash
cat ~/easy-rsa/pki/private/client1.key



<img width="858" height="588" alt="image" src="https://github.com/user-attachments/assets/a02b958b-9548-4742-a80c-14e2c20f4b35" />


```

---

# 🧩 Step 5 — Save File

```bash
CTRL + X
Y
ENTER
```

---

# 🧩 Step 6 — Transfer File to Windows

File location:

```bash
/home/sunny/easy-rsa/client1.ovpn
```

Transfer using:

* WinSCP
* Shared folder
* USB

---

# 🧩 Step 7 — Install OpenVPN Client (Windows)

Download:
https://openvpn.net/community-downloads/

Install OpenVPN GUI

---

📸 Screenshot:

<img width="1228" height="886" alt="image" src="https://github.com/user-attachments/assets/833edae3-e6a9-44ce-b846-5c24fdfe86c6" />


---

# 🧩 Step 8 — Import Configuration

Copy file to:

```text
C:\Program Files\OpenVPN\config
```

## Steps:

1. Open OpenVPN GUI as Administrator
2. Right-click icon → Connect

---

📸 Screenshot:

<img width="700" height="490" alt="image" src="https://github.com/user-attachments/assets/d3244253-51f3-4f2f-b234-e450d443d528" />

---

# 🧩 Step 9 — Verify Connection

Check:

* Status → Connected
* Assigned IP → 10.8.0.x

---

# ✅ Final Outcome

* VPN successfully connected
* Secure encrypted tunnel established
* Internal network accessible remotely
* Enterprise remote access implemented

---

# 🔐 Security Features Implemented

* AES-256 encryption
* Certificate-based authentication
* Secure tunneling
* Controlled internal access

---

