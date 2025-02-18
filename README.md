# Nexus Testent II

<div align="center">
  <img src="ss.png" alt="Flexx Richie Banner"/>
</div>


# Nexus CLI Installation Guide

A comprehensive and up-to-date guide for installing and running the Nexus CLI on Android, Windows, macOS, and EC2 Ubuntu instances.

## Table of Contents
- [AWS EC2 Ubuntu Setup](#aws-ec2-ubuntu-setup)
- [Android Installation (Termux)](#android-installation-termux)
- [Windows Installation](#windows-installation)
- [macOS Installation](#macos-installation)
- [Running and Maintaining Nexus CLI](#running-and-maintaining-nexus-cli)
- [Troubleshooting](#troubleshooting)
- [Support and Updates](#support-and-updates)

---

## AWS EC2 Ubuntu Setup

### Prerequisites
- AWS Account ([Setup Guide](https://github.com/Fl3xxRichie/AWS-EC2-SSH-GUIDE))
- EC2 Ubuntu Instance (18.04 or later)
- SSH Access (Terminal, Termux, or PuTTY)

### Step 1: Launch an EC2 Instance
Follow this repository guide to set up an EC2 instance: [AWS EC2 SSH GUIDE](https://github.com/Fl3xxRichie/AWS-EC2-SSH-GUIDE)

### Step 2: SSH into Your Instance
```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

### Step 3: Update and Install Dependencies
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential clang make gcc pkg-config libssl-dev libcrypto++-dev libc6-dev zlib1g-dev curl wget
```

### Step 4: Install Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

---

## Android Installation (Termux)

### Prerequisites
- Android 7.0 or higher
- 2GB of free storage
- Stable internet connection

### Step 1: Install Termux
1. Uninstall Termux if from Play Store.
2. Download and install F-Droid: https://f-droid.org
3. Install Termux from F-Droid.

### Step 2: Set Up Termux
```bash
pkg update && pkg upgrade -y
pkg install proot-distro curl wget
```

### Step 3: Install Ubuntu on Termux
```bash
proot-distro install ubuntu
proot-distro login ubuntu
```

### Step 4: Install Dependencies
```bash
apt update && apt upgrade -y
apt install -y build-essential clang make gcc pkg-config libssl-dev libcrypto++-dev libc6-dev zlib1g-dev
```

### Step 5: Install Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

---

## Windows Installation

### Prerequisites
- Windows 10 version 2004+ (Build 19041+)
- Administrator privileges

### Step 1: Install WSL
```powershell
wsl --install
wsl --set-default-version 2
```
Restart your computer.

### Step 2: Install Ubuntu from Microsoft Store

### Step 3: Install Dependencies
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential pkg-config libssl-dev libcrypto++-dev gcc libc6-dev zlib1g-dev
```

### Step 4: Install Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

---

## macOS Installation

### Prerequisites
- macOS 10.15 or later
- Command Line Tools for Xcode

### Step 1: Install Homebrew
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Step 2: Install Dependencies
```bash
brew install openssl pkg-config
brew link openssl --force
```

### Step 3: Install Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

---

## Running and Maintaining Nexus CLI

### Starting Nexus CLI
```bash
nexus
```

### Keeping Nexus CLI Running
#### Using `nohup` (Runs in Background)
```bash
nohup nexus &
```
#### Using `tmux` (Best for EC2)
```bash
tmux
nexus
```
Detach with `Ctrl + b`, then `d`. Reattach with `tmux attach`.
#### Using `screen`
```bash
screen
nexus
```
Detach with `Ctrl + a`, then `d`. Reattach with `screen -r`.

---

## Troubleshooting

### Common Issues
#### Android/Termux
- "linker cc not found":
  ```bash
  apt install -y build-essential
  ```
- SSL/Crypto errors:
  ```bash
  apt install -y libssl-dev libcrypto++-dev
  ```

#### Windows
- WSL installation fails:
  ```powershell
  dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  ```
- Library errors:
  ```bash
  sudo apt install --reinstall build-essential libssl-dev
  ```

#### macOS
- OpenSSL errors:
  ```bash
  brew reinstall openssl
  export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/opt/openssl/lib/
  ```

### General Checks
```bash
ps aux | grep nexus
pkill nexus
rm -rf ~/.nexus/temp/*
```

---

## Support and Updates

### Getting Help
[![Twitter](https://img.shields.io/badge/Twitter-%231DA1F2.svg?style=for-the-badge&logo=Twitter&logoColor=white)](https://twitter.com/FlexxRichie)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/FlexxRichie)
[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Fl3xxRichie)
[![Premium Channel](https://img.shields.io/badge/Telegram%20Channel-Premium%20Scripts-blue?style=for-the-badge&logo=telegram)](https://t.me/+GIfY4Pb0Spw5OGZk)
[![Direct Contact](https://img.shields.io/badge/Telegram-Direct%20Contact-green?style=for-the-badge&logo=telegram)](https://t.me/flexxrichie)

### Checking for Updates
```bash
nexus update
```

