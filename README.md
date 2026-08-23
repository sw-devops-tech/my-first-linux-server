# My First Linux DevOps Server

This repository documents the setup of my local Linux home lab server environment. I built this project to practice system virtualization, networking, and command-line administration ahead of my computing degree.

## 🛠️ Infrastructure Setup
- **Hypervisor:** Oracle VirtualBox
- **Operating System:** Ubuntu Server 24.04 LTS
- **Hardware Profile:** 2x CPU Cores, 2GB RAM, 25GB Dynamic Storage (M.2 SSD)

## 🌐 Networking & Port Forwarding
To allow my Windows 11 host machine to securely talk to the guest Linux operating system, I configured a port forwarding rule through the VirtualBox NAT adapter:
- **Protocol:** TCP
- **Host Connection:** 127.0.0.1:2222
- **Guest Destination:** Port 22 (SSH Receiver)

## 💻 Skills Practiced
- Navigating the BIOS to unlock AMD-V hardware virtualization features.
- Navigating a Linux system installer entirely using keyboard text inputs.
- Using the Linux Command Line interface to run network diagnostic tools (`ping`).
- Updating and patching enterprise software dependencies using the advanced packaging tool (`apt update && apt upgrade`).

Next, I will be using this server environment to practice Python scripting and network automation.
