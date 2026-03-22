# 🔐 OpenVPN Setup (Secure Remote Access)

## 📌 Overview

OpenVPN was configured on the Ubuntu server to provide secure remote access to the internal enterprise network (192.168.56.0/24).

This allows remote users to securely connect to internal systems such as:

* Windows Server (Active Directory)
* Ubuntu Web Server
* TrueNAS Storage
* Wazuh SIEM

---

# 🧩 Step 1 — Install OpenVPN & Easy-RSA

```bash
sudo apt update
sudo apt install openvpn easy-rsa -y
```

## 🎯 Purpose

* `openvpn` → VPN service for secure tunneling
* `easy-rsa` → Used to generate certificates for secure authentication

---

# 🧩 Step 2 — Setup Certificate Authority (CA)

```bash
make-cadir ~/easy-rsa
cd ~/easy-rsa
./easyrsa init-pki
./easyrsa build-ca
```

## 🎯 Purpose

* Creates Public Key Infrastructure (PKI)
* Generates root certificate authority (CA)
* Used to sign server and client certificates

📸 **Screenshot Certificate Generate **


<img width="973" height="722" alt="openvpn-CA-Certificate-generate" src="https://github.com/user-attachments/assets/fe7f7a45-f9a1-4eb4-ad1f-fe81c2c43805" />


---

# 🧩 Step 3 — Generate Server Certificate

```bash
./easyrsa gen-req server nopass
./easyrsa sign-req server server
```

## 🎯 Purpose

* Creates server identity
* Allows clients to trust VPN server

📸 **Screenshot Server Certificate**


<img width="1078" height="842" alt="openvpn-Service-Certificate-generate" src="https://github.com/user-attachments/assets/a54ffbec-4fb8-408b-bf81-97e6bd66c721" />


---

# 🧩 Step 4 — Generate Client Certificate

```bash
./easyrsa gen-req client1 nopass
./easyrsa sign-req client client1
```

## 🎯 Purpose

* Creates secure client authentication
* Ensures only authorized users can connect

📸 **Screenshot Client Certificate**


<img width="1078" height="815" alt="openvpn-Client-Certificate-generate" src="https://github.com/user-attachments/assets/d645ec10-38cc-48fd-96a7-1f6c9e6e21ec" />


---

# 🧩 Step 5 — Generate Diffie-Hellman Parameters

```bash
./easyrsa gen-dh
```

## 🎯 Purpose

* Enables secure key exchange
* Prevents interception during handshake

---

# 🧩 Step 6 — Copy Certificates to OpenVPN Directory

```bash
sudo cp ~/easy-rsa/pki/ca.crt /etc/openvpn/
sudo cp ~/easy-rsa/pki/issued/server.crt /etc/openvpn/
sudo cp ~/easy-rsa/pki/private/server.key /etc/openvpn/
sudo cp ~/easy-rsa/pki/dh.pem /etc/openvpn/
```

## 🎯 Purpose

* Makes certificates accessible to OpenVPN service

---

# 🧩 Step 7 — Configure OpenVPN Server

```bash
sudo nano /etc/openvpn/server.conf
```

### 🔧 Replace with:

```
port 1194
proto udp
dev tun

ca ca.crt
cert server.crt
key server.key
dh dh.pem

topology subnet
server 10.8.0.0 255.255.255.0

ifconfig-pool-persist /var/log/openvpn/ipp.txt

push "route 192.168.56.0 255.255.255.0"
push "redirect-gateway def1 bypass-dhcp"

push "dhcp-option DNS 8.8.8.8"
push "dhcp-option DNS 8.8.4.4"

keepalive 10 120

cipher AES-256-CBC
user nobody
group nogroup

persist-key
persist-tun

status /var/log/openvpn/openvpn-status.log

verb 3
explicit-exit-notify 1
```

## 🎯 Purpose

* Defines VPN network
* Routes traffic securely
* Applies encryption and security settings

---

# 🧩 Step 8 — Enable IP Forwarding

```bash
sudo nano /etc/sysctl.conf
```

Uncomment:

```
net.ipv4.ip_forward=1
```

Apply:

```bash
sudo sysctl -p
```

## 🎯 Purpose

* Allows traffic routing between VPN and internal network

---

# 🧩 Step 9 — Start OpenVPN Server

```bash
sudo systemctl start openvpn@server
sudo systemctl enable openvpn@server
sudo systemctl status openvpn@server
```

## 🎯 Purpose

* Starts VPN service
* Ensures auto-start on boot
* Verifies service health

📸 **Screenshot Required**

<img width="1483" height="546" alt="image" src="https://github.com/user-attachments/assets/a845350d-fab3-4693-911e-d33ffdcdf779" />


* Capture: Active (running) status

---

# 🧩 Step 10 — Verify VPN Service

```bash
journalctl -xeu openvpn@server
```

## 🎯 Purpose

* Used for troubleshooting errors
* Confirms successful initialization

📸 **Screenshot Required (Optional)**


<img width="966" height="843" alt="image" src="https://github.com/user-attachments/assets/03fca15b-6487-4555-932a-5de943f3d11c" />


---

# ✅ Final Outcome

* OpenVPN server successfully deployed
* Secure encrypted tunnel established
* Internal network (192.168.56.0/24) accessible remotely

---

# 🔥 Key Security Features Implemented

* AES-256 encryption
* Certificate-based authentication
* Secure routing of internal traffic
* DNS protection
* Least privilege execution

---
