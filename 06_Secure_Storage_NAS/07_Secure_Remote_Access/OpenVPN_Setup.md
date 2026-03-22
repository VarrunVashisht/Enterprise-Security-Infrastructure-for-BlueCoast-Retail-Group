# 🔐 OpenVPN Server Setup

## 📌 Overview

OpenVPN was configured on the Ubuntu server to provide secure remote access to internal infrastructure.

---

## ⚙️ Commands & Purpose

### Install OpenVPN

```bash
sudo apt install openvpn easy-rsa -y
```

Used to install VPN service and certificate tools.

---

### Setup Certificate Authority

```bash
make-cadir ~/easy-rsa
cd ~/easy-rsa
./easyrsa init-pki
./easyrsa build-ca
```

Creates secure authentication infrastructure.

---

### Generate Certificates

```bash
./easyrsa gen-req server nopass
./easyrsa sign-req server server
./easyrsa gen-req client1 nopass
./easyrsa sign-req client client1
```

Used to authenticate server and clients.

---

### Enable IP Forwarding

```bash
sudo sysctl -p
```

Allows VPN traffic routing.

---

### Start OpenVPN

```bash
sudo systemctl start openvpn@server
```

Starts VPN service.

---

## 🎯 Purpose

Provides:

* Encrypted communication
* Secure remote access
* Protection from interception

---

## ✅ Outcome

OpenVPN server successfully deployed and running.
