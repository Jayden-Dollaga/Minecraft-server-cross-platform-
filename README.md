---

# Badges

```
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Platform](https://img.shields.io/badge/platform-GitHub%20Codespaces-blue)
![Minecraft](https://img.shields.io/badge/Minecraft-Java%20%7C%20Bedrock-orange)
![CraftyControl](https://img.shields.io/badge/Crafty-Control-red)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
```

---

# Features

Add this below your Requirements section:

```
## Features

- Runs a Java/Bedrock Minecraft server on GitHub Codespaces
- Full web-based server management using CraftyControl
- Works on any device (PC, phone, tablet)
- No paid hosting required
- Supports plugins, mods, and multiple server versions
- Cross-platform support (Java ⇄ Bedrock via Geyser/Floodgate)
- Playit.gg tunneling for public IP access without port forwarding
- Automatic service creation for Crafty (optional)
- One-command server startup and updates
- Clean setup that works even on low-spec devices
```

---

# Troubleshooting

Add this near the bottom of your README:

```
## Troubleshooting

### CraftyControl not opening
- Make sure you ran:  
  `/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh`
- If Codespaces shows no popup link, check terminal output for the URL.
- Try restarting the Codespace.

### "pip: command not found"
Run:
  sudo apt install python3-pip

### Installer says "distro missing"
Run:
  pip install distro

### Playit agent not starting
- Make sure you opened a **new terminal** before running `playit`.
- Reinstall Playit by copying a fresh command from playit.gg.

### Server won't start in Crafty
- Check if Java is installed inside Codespaces.
- Verify your server folder is inside:
  `/workspaces/Minecraft-server-cross-platform-/minecraft`

### Codespace shut down
GitHub Codespaces auto-sleeps if idle.  
Just reopen your Codespace and run:
  /workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh
  playit

### "Permission denied" errors
Run the command with:
  sudo ./install_crafty.sh
or
  sudo chmod +x file.sh
```
---

# Minecraft Server (Java & Bedrock)

Cross-platform hosting using **GitHub Codespaces**, **CraftyControl**, and **Playit.gg**

## Requirements

* Sanity
* Time
* GitHub account
* playit.gg account
* CraftyControl

---

## How to Host a Minecraft Server Using GitHub Codespaces

### 1. Create Your GitHub Environment

1. Sign in or create a GitHub account.
2. Create a new repository:

   * Name: anything you want
   * Description: optional
   * Add README: enable
3. Open **Codespaces**:

   * Click “Create new Codespace”
   * Repository: your repo
   * Branch: `main`
   * Region: choose nearest
   * Machine type: **4-core**
4. Click **Create Codespace**.

---

## 2. Install Crafty Controller

Inside your Codespaces terminal:

### Step A — Update system and install Git

```bash
sudo apt update && sudo apt upgrade && sudo apt install git
```

If it asks `[y/N]`, type `y`.

If a configuration window appears (OpenSSH), just select **keep the local version** and continue.

### Step B — Install `distro`

```bash
pip install distro
```

### Step C — Install Crafty (Automated Installer)

Use this one-line command:

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git && cd crafty-installer-4.0 && sudo ./install_crafty.sh
```

If you prefer manual:

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
cd crafty-installer-4.0
sudo ./install_crafty.sh
```

### Step D — Installer Prompts

During installation:

1. “Download Ubuntu requirements?” → **y**
2. “Where should Crafty install?” →

   * Right-click your README
   * Copy path:
     `/workspaces/Minecraft-server-cross-platform-/README.md`
   * Replace `README.md` with `minecraft`
     Example:
     `/workspaces/Minecraft-server-cross-platform-/minecraft`
   * Press **y** to confirm
3. “Master or dev?” → type **master**
4. “Create a service for Crafty?” → **y**

Crafty is now installed.

---

## 3. Running and Updating Crafty

Start Crafty:

```bash
/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh
```

Update Crafty:

```bash
/workspaces/Minecraft-server-cross-platform-/minecraft/update_crafty.sh
```

When it runs, Codespaces will show a small popup link in the corner.
Click it to open Crafty in your browser.

---

## 4. First-Time Login Setup

1. On the Crafty login screen, click **Forgot Password**.
2. Check your Codespaces terminal — it will show a recovery username and password.
3. Log in using those credentials.
4. Go to the dashboard → settings → change the admin password.
   Pick something easy like `12345678` (you can change later).
5. Log out of account recovery and log in with the new admin account.

Your Crafty panel is now ready.

---

## 5. Port Forwarding (Playit.gg)

This lets Java + Bedrock players join from anywhere.

1. Go to **playit.gg** and download the Linux agent.
2. Copy the command they provide.
3. In Codespaces, open a **new terminal** (press the + button).
4. Paste the Playit install command and press enter.
5. When prompts appear, type **y** where needed.
6. Once installed:

   ```bash
   playit
   ```
7. Confirm your token.
8. Choose your agent.
9. Playit will generate public IP + ports for your server.

You're done — CraftyControl + Playit give you a working cross-platform server.

---

## Quick Start Commands

Run Crafty:

```bash
/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh
```

Run Playit:

```bash
playit
```

---
