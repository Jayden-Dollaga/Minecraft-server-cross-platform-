[![Platform](https://img.shields.io/badge/platform-GitHub%20Codespaces-blue)](https://github.com/Jayden-Dollaga/Minecraft-server-cross-platform-/codespaces)

[![Latest Release](https://img.shields.io/github/v/release/Jayden-Dollaga/Minecraft-server-cross-platform-?label=Download&color=blue)](https://github.com/Jayden-Dollaga/Minecraft-server-cross-platform-/releases/latest)

![Status](https://img.shields.io/badge/status-semi--active-yellow)
![Minecraft](https://img.shields.io/badge/Minecraft-Java%20%7C%20Bedrock-orange)
![CraftyControl](https://img.shields.io/badge/Crafty-Control-red)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

> ⚠️ This repository is for personal archive use only.

> ⚠️ **Codespaces Usage Disclaimer:**  
> If you are using GitHub Free Plan, you may hit Codespaces limits:
> - 120 core-hours of Codespaces compute per developer per month
> - 15GB of Codespaces storage per developer
> - You might see messages like:  
>   `"Please adjust your billing settings to continue using Codespaces"`  
> Unlimited public/private repos, collaborators, Actions minutes, and Packages storage still apply.  
> For full details, see the [GitHub Codespaces Billing Documentation](https://docs.github.com/en/billing/concepts/product-billing/github-codespaces).

---

# Table of Contents
- [Overview](#minecraft-server-java--bedrock)
- [Requirements](#requirements)
- [Features](#features)
- [Hosting Guide](#how-to-host-a-minecraft-server-using-github-codespaces)
- [Crafty Installation](#2-install-crafty-controller)
- [Playit Setup](#5-port-forwarding-playitgg-)
- [Quick Commands](#quick-start-commands)
- [Troubleshooting](#troubleshooting)
- [Archive Notes](#archive-notes-personal-use)
- [Minecraft Versions](#minecraft-versions-)
- [Plugins List](#required-plugins-all-jar-files)
- [APK Storage](#apk-storage-personal-archive)


---

# Minecraft Server (Java & Bedrock)

Cross-platform hosting using **GitHub Codespaces**, **CraftyControl**, and **Playit.gg**

## Requirements

* Sanity
* Time
* GitHub account
* Playit.gg account
* CraftyControl

---

# Features

* Runs a Java/Bedrock Minecraft server on GitHub Codespaces
* Full web-based server management using CraftyControl
* Works on any device (PC, phone, tablet)
* No paid hosting required
* Supports plugins, mods, and multiple server versions
* Cross-platform support (Java ⇄ Bedrock via Geyser/Floodgate)
* Playit.gg tunneling for public IP access without port forwarding
* Automatic service creation for Crafty (optional)
* One-command server startup and updates
* Clean setup that works even on low-spec devices

---

## How to Host a Minecraft Server Using GitHub Codespaces

### 1. Create Your GitHub Environment

1. Sign in or create a GitHub account.
2. Create a new repository:

   * Name: anything you want
   * Description: optional
   * Add README: enable
3. Open **Codespaces**: [![Codespaces](https://img.shields.io/badge/platform-GitHub%20Codespaces-blue)](https://github.com/codespaces)

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

Use this manual command:  “(Recomended)“

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
```

```bash
cd crafty-installer-4.0
```

```bash
sudo ./install_crafty.sh
```

If you prefer automatic:

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git && cd crafty-installer-4.0 && sudo ./install_crafty.sh
```

### Step D — Installer Prompts

During installation:

1. “Download Ubuntu requirements?” → **y**
2. “Install Crafty to this directory?” → **n**
3. “Where should Crafty install?” →
   
   * Right-click your README
   * Copy path:
     `/workspaces/Minecraft-server-cross-platform-/README.md`
   * Replace `README.md` with `minecraft`
     Example:
     `/workspaces/Minecraft-server-cross-platform-/minecraft`
   * Press **y** to confirm
4. “Master or dev?” → type **master**
5. “Create a service for Crafty?” → **y**

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

## 5. Port Forwarding (Playit.gg) [![Playit.gg](https://img.shields.io/badge/Playit.gg-Online-blue)](https://playit.gg/)

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

# Troubleshooting

### CraftyControl not opening

* Make sure you ran:
  `/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh`
* If the popup didn’t show, check the terminal for the URL.
* Restart the Codespace if needed.

### "pip: command not found"

```bash
sudo apt install python3-pip
```

### Installer says "distro missing"

```bash
pip install distro
```

### Playit agent not starting

* Open a **new terminal** before running `playit`.
* Reinstall Playit with a fresh command from playit.gg.

### Server won't start in Crafty

* Ensure Java is installed.
* Verify your server files are inside:
  `/workspaces/Minecraft-server-cross-platform-/minecraft`

### Codespace shuts down

Codespaces auto-sleeps. Just reopen and run:

```
/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh
playit
```

### "Permission denied"

Try:

```bash
sudo ./install_crafty.sh
```

Or:

```bash
sudo chmod +x file.sh
```

---

# Archive Notes (Personal Use)

This section is for my own reference.
I am using this repository as an archive for my preferred server setup, versions, and plugins.

## Minecraft Versions [![Latest Release](https://img.shields.io/github/v/release/Jayden-Dollaga/Minecraft-server-cross-platform-?label=Download&color=blue)](https://github.com/Jayden-Dollaga/Minecraft-server-cross-platform-/releases/latest)
**Server Edition**
* spigot/paper version: **1.20.10**
  
**Java Edition:**

* Primary target version: **1.20.10**

**Bedrock Edition:**

* Target version range: **1.21.120**
* Acceptable alternatives: **any version 3–5 builds above or below this**

This setup is tested with Java–Bedrock crossplay through Geyser and Floodgate.

## Required Plugins (all `.jar` files)

These are the plugins I use for compatibility, cosmetics, and cross-version support:

* EmoteOffhand.jar
* floodgate-spigot.jar
* GeyserConnect.jar
* Geyser-Spigot.jar
* hurricane-spigot.jar
* ThirdPartyCosmetics.jar
* Thunder.jar
* ViaBackwards-5.5.1.jar
* ViaRewind-4.0.11.jar
* ViaVersion-5.5.0.jar

All plugins go inside the Crafty-managed server `plugins/` directory.

---

## APK Storage (Personal Archive)

I will store a **custom Minecraft APK** here (or link it through Releases) purely as an archive for my setup.
This is not intended for distribution — only for my own testing and reference.



