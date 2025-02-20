# Nexus Testent II

<div align="center">
  <img src="ss.png" alt="Flexx Richie Banner"/>
</div>


# Nexus CLI Installation Guide (UPDATED)

A comprehensive and up-to-date guide for installing and running the Nexus CLI on Ubuntu (Recommended), Windows, Android, macOS, and EC2 Ubuntu instances. This update includes real-time error solutions for a smooth experience.

## Table of Contents
- [Ubuntu Installation (Recommended)](#ubuntu-installation-recommended)
- [Windows Installation](#windows-installation)
- [AWS EC2 Ubuntu Setup](#aws-ec2-ubuntu-setup)
- [Android Installation (Termux)](#android-installation-termux)
- [macOS Installation](#macos-installation)
- [Running and Maintaining Nexus CLI](#running-and-maintaining-nexus-cli)
- [Troubleshooting (Errors & Solutions)](#troubleshooting-errors--solutions)
- [Support and Updates](#support-and-updates)

---

## Ubuntu Installation (Recommended)

### Prerequisites
- Ubuntu 20.04 or later
- Minimum 8GB RAM (Recommended: 16GB)

### Step 1: Update & Install Dependencies
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential clang make gcc pkg-config libssl-dev libcrypto++-dev libc6-dev zlib1g-dev curl wget
```

### Step 2: Install Rust and Cargo
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### Step 3: Install Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

### Step 4: Verify Installation
```bash
nexus --version
```

---

## Windows Installation

### Prerequisites
- Windows 10 version 2004+ (Build 19041+)
- Administrator privileges
- Minimum 8GB RAM (Recommended: 16GB)

### Step 1: Install WSL
```powershell
wsl --install
wsl --set-default-version 2
```
Restart your computer.

### Step 2: Install Ubuntu from Microsoft Store

### Step 3: Launch Ubuntu and Install Dependencies
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential pkg-config libssl-dev libcrypto++-dev gcc libc6-dev zlib1g-dev curl wget
```

### Step 4: Install Rust and Cargo
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### Step 5: Install Nexus CLI
```bash
curl https://cli.nexus.xyz/ | sh
```

### Step 6: Verify Installation
```bash
nexus --version
```

---

## AWS EC2 Ubuntu Setup

### Step 1: Launch an EC2 Instance
Follow this [AWS EC2 SSH GUIDE](https://github.com/Fl3xxRichie/AWS-EC2-SSH-GUIDE)

### Step 2: SSH into Your Instance
```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

### Step 3: Install Dependencies, Rust, Cargo & Nexus CLI (Same as Ubuntu Steps)

---

## Android Installation (Termux)

### Prerequisites
- Android 7.0 or higher

### Step 1: Install Termux from F-Droid

### Step 2: Set Up Termux
```bash
pkg update && pkg upgrade -y
pkg install proot-distro curl wget
proot-distro install ubuntu
proot-distro login ubuntu
```

### Step 3: Install Dependencies, Rust, Cargo & Nexus CLI (Same as Ubuntu Steps)

---

## macOS Installation

### Prerequisites
- macOS 10.15 or later

### Step 1: Install Homebrew
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Step 2: Install Dependencies
```bash
brew install openssl pkg-config
brew link openssl --force
```

### Step 3: Install Rust and Cargo
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### Step 4: Install Nexus CLI
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
#### nohup
```bash
nohup nexus &
```
#### tmux
```bash
tmux
nexus
```
Detach: `Ctrl + b` + `d`, Reattach: `tmux attach`

#### screen
```bash
screen
nexus
```
Detach: `Ctrl + a` + `d`, Reattach: `screen -r`

---

## Troubleshooting (Errors & Solutions)

### 1. `linker cc not found` (Termux/Ubuntu)
```bash
apt install -y build-essential
```

### 2. `error while loading shared libraries: libssl.so` (Ubuntu/Windows WSL)
```bash
sudo apt install -y libssl-dev libcrypto++-dev
```

### 3. WSL Installation Fails (Windows)
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

### 4. `Memory Allocation Errors` (Ubuntu/Windows WSL)
- Ensure at least 8GB RAM, Recommended 16GB
- Check available memory:
```bash
free -h
```
- If Swap is low, increase swap space:
```bash
sudo fallocate -l 4G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
sudo bash -c 'echo "/swapfile none swap sw 0 0" >> /etc/fstab'
```

### 5. General Maintenance
```bash
ps aux | grep nexus
pkill nexus
rm -rf ~/.nexus/temp/*
```

---

## Support and Updates

```bash
nexus update
```



### Getting Help
[![Twitter](https://img.shields.io/badge/Twitter-%231DA1F2.svg?style=for-the-badge&logo=Twitter&logoColor=white)](https://twitter.com/FlexxRichie)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/FlexxRichie)
[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Fl3xxRichie)
[![Premium Channel](https://img.shields.io/badge/Telegram%20Channel-Premium%20Scripts-blue?style=for-the-badge&logo=telegram)](https://t.me/+GIfY4Pb0Spw5OGZk)
[![Direct Contact](https://img.shields.io/badge/Telegram-Direct%20Contact-green?style=for-the-badge&logo=telegram)](https://t.me/flexxrichie)



