# Blockcast BEACON Node – One-Click Installation Guide

This guide helps you install and register a **Blockcast BEACON node** in just a few steps using a single shell script. No manual Docker setup required.

---

## 📦 Prerequisites

- A Linux/macOS/WSL machine with internet access
- Basic terminal/command-line knowledge
- Docker installed (or this script will install it for you)
- Git installed

---

## 💪 Step-by-Step Setup

### 1. Clone the Repository and Run the Script

```bash
git clone https://github.com/your-repo/blockcast-beacon-installer.git
cd blockcast-beacon-installer
chmod +x install-beacon.sh
./install-beacon.sh
```

> 📝 This script will install Docker & Docker Compose (if not already installed), clone the BEACON Docker repo, and start the BEACON services.

---

### 2. Wait for Initialization

The script will wait briefly for the container to initialize, then automatically run:

```bash
docker-compose exec blockcastd blockcastd init
```

This command outputs:
- 🔑 **Hardware ID**
- 🔐 **Challenge Key**
- 🔗 **Registration URL**

---

### 3. Register Your Node

You can now register your node using one of these two methods:

#### ✅ Automatic (Recommended):
Open the **registration URL** shown in the terminal after running the script.

#### 📝 Manual:
1. Go to: [https://app.blockcast.network/manage-nodes](https://app.blockcast.network/manage-nodes)
2. Click **"Register Node"**
3. Paste in the **Hardware ID** and **Challenge Key**
4. Allow browser location access when prompted

---

### 4. Verify Node Health

After successful registration:
- Your node will appear on the `/manage-nodes` dashboard.
- It may take a few minutes for status to show as **Healthy**
- Click on the node to view uptime, rewards, and performance data

---

### 5. Keep Your Node Online

- ⏱️ **Minimum uptime**: 6 hours for first connectivity test
- 💰 **Reward eligibility**: Starts after 24 hours of uptime

---

## 🔒 Backup Instructions

Make sure to **back up your private key**:

```bash
~/.blockcast/certs/gw_challenge.key
```

> 📂 If you lose this key, you won’t be able to prove ownership of the node.

---

## 💬 FAQs

- **Can I run multiple BEACON nodes?**  
  ➤ Yes, but each must be on a **unique public IP** and **registered under a separate Blockcast account**.

- **Does this work on macOS or Windows?**  
  ➤ Yes. This script runs on any OS that supports Docker (including macOS, Linux, and WSL on Windows).

- **Where can I read more?**  
  ➤ Visit the official docs: [docs.blockcast.network](https://docs.blockcast.network/main/getting-started/how-do-i-participate-in-the-network/beacon/start-running-your-beacon-today)

---

## 📜 License

MIT License – use freely, contribute improvements, and help decentralize!
