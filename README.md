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

## 🚀 Remote Management & Verification (SSH Validation)
To simulate real-world cloud operations, I verified that the server could be managed completely "headless" (without a graphical user interface) from my host machine's native terminal. 

- **Execution:** Initiated a secure remote session via Windows Command Prompt using the Secure Shell protocol: `ssh developer@127.0.0.1 -p 2222`.
- **Security Handshake:** Successfully completed the ECDSA/ED25519 cryptographic key fingerprint verification to establish a trusted link between host and guest.
- **Network Validation:** Executed live network diagnostics (`ping -c 3 google.com`) directly through the remote terminal shell, confirming 100% packet transmission success and 0% packet loss.
- **System Monitoring:** Utilized Linux process management tools (`top`) to monitor live CPU and memory telemetry metrics remotely.
- **Graceful Shutdown:** Implemented standard infrastructure operations by executing elevated administrative commands (`sudo poweroff`) to terminate the virtual environment cleanly without data corruption.
