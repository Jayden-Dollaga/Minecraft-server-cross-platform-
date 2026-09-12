[![Platform](https://img.shields.io/badge/platform-GitHub%20Codespaces-blue)](https://github.com/Jayden-Dollaga/Minecraft-server-cross-platform-/codespaces)

[![Latest Release](https://img.shields.io/github/v/release/Jayden-Dollaga/Minecraft-server-cross-platform-?label=Download&color=blue)](https://github.com/Jayden-Dollaga/Minecraft-server-cross-platform-/releases/latest)

![Status](https://img.shields.io/badge/status-semi--active-yellow)
![Minecraft](https://img.shields.io/badge/Minecraft-Java%20%7C%20Bedrock-orange)
![CraftyControl](https://img.shields.io/badge/Crafty-Control-red)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

> ⚠️ This repository is for personal archive use only.
>
> ⚠️ **Codespaces Usage Disclaimer:**  
> GitHub Codespaces has limits on free and billed use for **personal accounts**.  
> **Note:** GitHub plans for organizations and enterprises do **not** include a free Codespaces quota.
>
> **Free Quota for Personal Accounts:**  
> All GitHub personal accounts include a quota of free compute time and storage for Codespaces. Any usage beyond the included amounts is billed to your account.
>
> | Account Plan | Storage per Month | Compute Time per Month |
> |-------------|-----------------|----------------------|
> | GitHub Free | 15 GB-month      | 120 hrs              |
> | GitHub Pro  | 20 GB-month      | 180 hrs              |
>
> **Important Notes:**  
> - GitHub Codespaces is not available for repositories owned by **managed user accounts**. See [About Enterprise Managed Users](https://docs.github.com/en/enterprise-cloud@latest/admin/overview/about-enterprise-managed-users) for details.  
> - For tips on making the most of your free usage, see [Getting the most out of your included usage](https://docs.github.com/en/billing/concepts/product-billing/github-codespaces).  
> - You may see messages like: `"Please adjust your billing settings to continue using Codespaces"` if you exceed your quota.

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

   * Click "Create new Codespace"
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

![Update system prompt](Asset/185425.png)

If a configuration window appears (OpenSSH), just select **keep the local version** and continue.

![OpenSSH config prompt](Asset/185936.png)

### Step B — Install `distro`

```bash
pip install distro
```

### Step C — Install Crafty (Automated Installer)

Use this manual command: "(Recommended)"

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
cd crafty-installer-4.0
sudo ./install_crafty.sh
```

Or, if you'd rather run it as a one-liner:

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git && cd crafty-installer-4.0 && sudo ./install_crafty.sh
```

### Step D — Installer Prompts

Walk through the prompts in order:

1. "Download Ubuntu requirements?" → **y**

   ![Download requirements prompt](Asset/190209.png)

2. "Install Crafty to this directory?" → **n**

   ![Install directory prompt](Asset/190409.png)

3. "Where should Crafty install?" — point it at a `minecraft` folder inside your repo:

   * Right-click your `README.md` in the file explorer and **Copy Path**:
     `/workspaces/Minecraft-server-cross-platform-/README.md`

     ![Copy README path](Asset/190459.png)

   * Paste it in, then replace `README.md` with `minecraft`, e.g.:
     `/workspaces/Minecraft-server-cross-platform-/minecraft`

     ![Replace with minecraft path](Asset/190628.png)

   * Press **y** to confirm.

4. "Master or dev?" → type **master**

   ![Master or dev prompt](Asset/190759.png)

5. "Create a service for Crafty?" → **y**

   ![Create service prompt](Asset/190842.png)

Crafty is now installed.

![Crafty installed](Asset/190951.png)

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

When it runs, Codespaces will show a small popup link in the corner. Click it to open Crafty in your browser.

![Crafty popup link](Asset/191058.png)

---

## 4. First-Time Login Setup

1. On the Crafty login screen, click **Forgot Password**.
2. Check your Codespaces terminal — it will print a recovery username and password.
3. Log in using those credentials.
4. Go to the dashboard → settings → change the admin password to something you'll remember (you can change it again later).
5. Log out of the recovery account and log back in with your new admin account.

![Crafty recovery login](Asset/191214.png)
![Crafty dashboard](Asset/191226.png)
![Crafty settings](Asset/191317.png)
![Change admin password](Asset/191344.png)
![Confirm new password](Asset/191408.png)
![Logged in as admin](Asset/191448.png)

Your Crafty panel is now ready.

---

## 5. Port Forwarding (Playit.gg) [![Playit.gg](https://img.shields.io/badge/Playit.gg-Online-blue)](https://playit.gg/)

This lets Java + Bedrock players join from anywhere, without touching your router.

> ⚠️ **Codespaces has no systemd.** Playit's installer (both the APT method and the
> official `curl | bash` script) tries to register itself as a systemd service. Codespaces
> containers don't run an init system at all, so that registration silently fails. You'll
> see something like:
> ```
> System has not been booted with systemd as init system (PID 1). Can't operate.
> ```
> and then, whenever you try to use the `playit` command normally:
> ```
> The playit service is running, but its IPC socket does not exist yet.
> Restart the service, then try again: sudo systemctl restart playit
> ```
> **`sudo systemctl restart playit` will never work here — don't run it.** Instead, run
> the daemon by hand, as shown below. This is a one-time quirk of the environment, not
> something you broke.

### A. Install playit

1. Go to [playit.gg](https://playit.gg/) and copy their Linux install command.

   ![Playit install download](Asset/191833.png)

2. In Codespaces, open a **new terminal** (press the **+** button) and paste it in.

   ![Paste playit install command](Asset/191935.png)

3. Answer **y** to every prompt as it installs.

   ![Playit install log](Asset/192208.png)

4. Near the end it will ask "Would you like to start playit now to finish setup?" — say **y**. This will fail with the systemd error described above. That's expected — continue to the next step.

   ![Playit install log, systemd failure](Asset/192219.png)

### B. Start the daemon manually

Since systemd isn't available, you run playit's daemon (`playitd`) directly instead of letting it manage itself as a service.

In this same terminal tab:

```bash
sudo mkdir -p /run/playit
sudo /opt/playit/playitd
```

Leave this tab running for as long as your server is online — this is your live playit daemon. It'll sit here waiting:

![Playit daemon waiting for secret](Asset/193321.png)

### C. Claim the agent

1. Open a **second terminal tab** (don't touch the one running the daemon) and run:

   ```bash
   playit setup
   ```

   You may hit this even if you're already in the `playit` group:

   ```
   The playit service is running, but this shell cannot access its IPC socket:
     /run/playit/playitd.sock

   Your user is already in the `playit` group, but this shell has not picked up that membership yet.

   Refresh group membership for this shell:
     newgrp playit
   ```

   If so, just do what it says:

   ```bash
   newgrp playit
   playit setup
   ```

   If `newgrp` behaves oddly in the embedded VS Code terminal, close the tab and open a fresh one instead — a new terminal picks up group membership automatically.

   Once it works, you'll get a claim link:

   ![Playit setup + newgrp fix](Asset/193551.png)

2. Open the claim link. VS Code will ask to open the external site — click **Open**.

   ![Confirm open external site](Asset/193556.png)

3. Log in to your playit.gg account if prompted.

   ![Claim agent - login required](Asset/193601.png)

   The page will show "Waiting for agent..." while it checks the connection.

   ![Waiting for agent](Asset/193613.png)

4. Verify the connecting agent's details (IP, program version, location) and click **Continue**.

   ![Verify agent details](Asset/193617.png)

5. Give the agent a name and click **Add Agent**.

   ![Name the agent](Asset/193622.png)

   It'll briefly show "Looking for your agent..." while it finalizes.

   ![Looking for agent](Asset/193628.png)

6. Once connected, click **Create a tunnel**.

   ![Agent connected](Asset/193639.png)

### D. Create your tunnel

1. Name your tunnel and click **Next**.

   ![Name your tunnel](Asset/193649.png)

2. Choose **Minecraft Java** (or **Minecraft Bedrock**, depending on your server) as the tunnel type.

   ![Choose tunnel type](Asset/193729.png)

3. Pick **Free Network** as your public endpoint (or Premium if you have it).

   ![Choose public endpoint](Asset/193735.png)

4. Set the Origin Config — Local IP `127.0.0.1`, Local Port matching your server (default Java is `25565`) — then click **Next**.

   ![Origin config](Asset/193744.png)

5. Review everything and click **Create Tunnel**.

   ![Review and create tunnel](Asset/193751.png)

6. Playit will allocate a public address — this can take a few seconds.

   ![Allocating address](Asset/193800.png)

### E. Confirm you're live

Back in your controller terminal tab:

```bash
playit status
```

You should see your agent connected and the tunnel listed with its public address.

![Playit status check](Asset/200236.png)

Keep both terminal tabs open the whole time your server is running — closing the daemon tab kills your public connection.

You're done — CraftyControl + Playit give you a working cross-platform server.

### Quick restart (after first-time setup)

Every time you reopen the Codespace, in one tab run:

```bash
sudo /opt/playit/playitd
```

then in another tab:

```bash
playit status
```

No need to re-claim the agent or recreate your tunnel — playit remembers your linked account and existing tunnels.

---

## Quick Start Commands

Run Crafty:

```bash
/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh
```

Run Playit — daemon (first tab):

```bash
sudo /opt/playit/playitd
```

Run Playit — status check (second tab):

```bash
playit status
```

---

# Troubleshooting

### CraftyControl not opening

* Make sure you ran:
  `/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh`
* If the popup didn't show, check the terminal for the URL.
* Restart the Codespace if needed.

### "pip: command not found"

```bash
sudo apt install python3-pip
```

### Installer says "distro missing"

```bash
pip install distro
```

### Playit: "service is running, but IPC socket does not exist"

* Codespaces has no systemd, so playit's service registration silently fails. Any
  `sudo systemctl ...` command related to playit will never work here.
* This happens regardless of install method (APT or the official `curl | bash` script).
* Fix: run the daemon directly instead of through a service manager. See [Section 5](#5-port-forwarding-playitgg-) for the full walkthrough:

  ```bash
  sudo mkdir -p /run/playit
  sudo /opt/playit/playitd
  ```

  in one tab, then `playit setup` / `playit status` in a second tab.

### Playit: `playit --stdout`, `playit start`, `playit agent`, etc. still show the socket error

* `playit` is only a controller — it always checks for a live daemon and socket first, no matter what flag or subcommand you give it. There's no flag that skips this check.
* You need to start the daemon binary itself (`sudo /opt/playit/playitd`), not the wrapper.

### Playit: "unexpected argument '--xyz' found" / "unrecognized subcommand"

* `playit` (the controller) and `playitd` (the daemon) take different arguments — flags for one won't work on the other (e.g. `--stdout` belongs to `playit`, not `playitd`).
* Run `playit --help` or `sudo /opt/playit/playitd --help` to check the right options for whichever binary you're calling.

### Playit: "socket is restricted to the `playit` group"

* Run: `sudo usermod -aG playit $USER`
* Close and reopen the terminal tab, then retry.

### Playit: "already in the `playit` group, but this shell has not picked up that membership yet"

* Run `newgrp playit`, then retry your command (e.g. `playit setup`).
* If `newgrp` misbehaves in the embedded VS Code terminal, close the tab and open a fresh one instead.

### Playit: daemon says "Waiting for frontend secret provisioning over IPC" and just sits there

* That's normal — it's waiting on you to run `playit setup` in a second terminal tab.
* Don't close the daemon tab; open a new one for setup/status commands.

### Server won't start in Crafty

* Ensure Java is installed.
* Verify your server files are inside:
  `/workspaces/Minecraft-server-cross-platform-/minecraft`

### Codespace shuts down

Codespaces auto-sleeps. Just reopen and run:

```bash
/workspaces/Minecraft-server-cross-platform-/minecraft/run_crafty.sh
sudo /opt/playit/playitd
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

This section is for my own reference. I'm using this repository as an archive for my preferred server setup, versions, and plugins.

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

I will store a **custom Minecraft APK** here (or link it through Releases) purely as an archive for my setup. This is not intended for distribution — only for my own testing and reference.
