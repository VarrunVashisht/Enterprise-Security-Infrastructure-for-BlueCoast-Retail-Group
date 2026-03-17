# 🖥️ VirtualBox Configuration

## 📌 Overview

A virtual lab environment was created using Oracle VirtualBox to simulate an enterprise network infrastructure.

---

## 🧱 Virtual Machines Created

The following machines were deployed:

* Windows Server 2025 (Domain Controller) - 192.168.56.10
* Ubuntu Server (Web Server)
* Windows 10 (Client Machine) - 192.168.56.11
* Kali Linux (Attack Machine)
* TrueNAS (Storage Server)
* Wazuh (SIEM Monitoring Server)

---

## 🌐 Network Adapter Configuration

Each virtual machine was configured with two network adapters:

### Adapter 1: NAT

* Provides internet access
* Used for downloading packages and updates

### Adapter 2: Host-Only Adapter (vboxnet0)

* Enables communication between internal machines
* Isolated from external network

---

## 🎯 Purpose of Configuration

This dual-network setup ensures:

* Safe attack simulation within an isolated network
* Controlled internet access
* Realistic enterprise network behavior

---

## ✅ Outcome

All virtual machines were successfully configured and connected within the same internal network while maintaining external internet access via NAT.

