# 🔗 Wazuh Agent Configuration (Windows & Linux)

## 📌 Overview

Wazuh agents were deployed on multiple endpoints (Windows and Linux) to collect logs and send them to the Wazuh SIEM server for centralized monitoring and threat detection.

---

## 🖥️ Windows Agent Configuration

### 📸 Agent Status

The Wazuh agent was successfully installed and configured on a Windows 10 machine.

* **Agent Name:** WIN10-001
* **Status:** Running
* **Manager IP:** 192.168.1.70

---

## ⚙️ Configuration Details

### 🔧 Manager IP

The agent is configured to communicate with the Wazuh Manager:

```bash id="zqj2ci"
192.168.1.70
```

**Why:**

* Defines the SIEM server where logs are sent
* Enables centralized monitoring

---

### 🔑 Authentication Key

```bash id="d4l6pd"
<authentication-key-generated-by-wazuh>
```

**Why:**

* Securely registers the agent with the Wazuh server
* Prevents unauthorized devices from sending logs

---

### ▶️ Agent Service Status

* Status: **Running**

**Why:**

* Confirms the agent is actively sending logs
* Required for real-time monitoring

---

## ⚙️ Windows Agent Installation (Reference Steps)

### Step 1: Download Agent

* From Wazuh dashboard → Add Agent → Windows

---

### Step 2: Install Agent

```bash id="s7w2bn"
msiexec /i wazuh-agent.msi /q WAZUH_MANAGER="192.168.56.122"
```

**Why:**

* Installs Wazuh agent silently
* Links agent to SIEM server

---

### Snapshot:

<img width="986" height="751" alt="image" src="https://github.com/user-attachments/assets/0243be2b-97ff-4af8-a31d-78082724fb7f" />



### Step 3: Start Service

```bash id="4p8rra"
net start wazuhsvc
```

**Why:**

* Starts agent service
* Enables log forwarding

---

## 🐧 Linux Agent (Brief Reference)

```bash id="tw6pfd"
sudo systemctl start wazuh-agent
```

---

## 🎯 Purpose in Project

Wazuh agents enable:

* 📊 Centralized log collection
* 🔍 Real-time monitoring
* 🚨 Threat detection
* 🛡️ Endpoint visibility

---

## ✅ Outcome

* Windows agent successfully connected to Wazuh SIEM
* Logs are being forwarded and monitored
* Endpoint visibility achieved across infrastructure

---

## 💡 Real-World Insight

In enterprise environments:

* Every endpoint runs an agent
* SIEM collects logs centrally
* Security teams monitor alerts in real-time

This setup replicates real SOC architecture.
