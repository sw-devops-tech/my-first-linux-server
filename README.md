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

## 🌐 Level 1 Achieved: Manual Web Infrastructure Deployment

I have successfully advanced this environment from a basic text container into a functional, live-hosting web server architecture. This phase establishes the critical manual foundation required before implementing cloud automation.

### 🛠️ Execution & Configuration Tasks
- **Network Layer Routing:** Configured a secondary network port forwarding rule through the VirtualBox NAT hypervisor. Mapped local host traffic from `127.0.0.1:8080` to point directly to guest destination network port `80` (the global standard for unencrypted HTTP web traffic).
- **Web Engine Deployment:** Logged into the headless server via remote shell and utilized the advanced packaging tool to securely install the enterprise-grade **Nginx Web Server** platform (`sudo apt install nginx -y`).
- **File System Operations:** Navigated the core Linux system directories (`/var/www/html`) to access root-level application deployment directories. 
- **Production Code Implementation:** Used the Linux command-line text engine (`nano`) under elevated root administrator privileges (`sudo`) to wipe default server text templates and implement clean, customized HTML web architecture files (`index.html`).

### 🔍 Verification & System Metrics
- **Host-to-Guest Validation:** Confirmed full connectivity by executing cross-platform network requests via a local host browser (**Google Chrome**). 
- **Deployment Status:** Verified that the custom-coded server interface rendering successfully, verifying an active end-to-end network tunnel between the independent Linux node and the main Windows 11 host operating system.

**Next Phase Target:** Level 2 — Shifting from manual setups to *Infrastructure as Code (IaC)* by creating executable automation scripts to handle this entire sequence in under 3 seconds.

# Local Infrastructure as Code (IaC) Automation with Terraform & Docker

An automated DevOps project that uses HashiCorp Terraform to provision, deploy, and manage a Linux-based Nginx web server inside a local Docker environment on Windows 11.

## 🚀 Overview

This project demonstrates the core principles of **Infrastructure as Code (IaC)** by replacing manual environment configuration with a repeatable, automated deployment pipeline. Instead of clicking through a graphical user interface (GUI) or manually running terminal setup steps, the entire infrastructure lifecycle is managed through declarative configuration files.

## 🛠️ Tech Stack & Tools

*   **IaC Tool:** HashiCorp Terraform (v1.5+)
*   **Container Platform:** Docker Desktop for Windows 11
*   **Virtualization:** Windows Hyper-V / Virtual Machine Platform
*   **Web Server Engine:** Nginx (Linux-based Docker image)

## 📁 Project Architecture & Files

*   `main.tf`: The core declarative script that defines the infrastructure provider (Docker), downloads the base Linux web server image, and spins up the live container.
*   `terraform.tfstate`: The state management file used by Terraform to track the real-world resources against our configuration code.

## ⚙️ How It Works (Step-by-Step)

### 1. Declaring the Infrastructure
The system configuration is defined inside `main.tf`. It explicitly asks for the `kreuzwerker/docker` provider, pulls down the latest lightweight Nginx server image, and maps internal container traffic (Port 80) directly to the local machine host network (Port 8080).

### 2. Initializing & Upgrading Providers
```cmd
terraform init -upgrade
```
This command analyzes the script, initializes the workspace backend, and safely downloads the specific provider plugins required to talk to the local Docker engine.

### 3. Executing the Deployment Blueprint
```cmd
terraform apply
```
Terraform compares the current live state of the computer against the code instructions, builds an execution path graph, and deploys the infrastructure. Once approved, the Linux server spins up seamlessly under 5 seconds.

## 📊 Core Business & DevOps Outcomes

*   **Zero Manual Configuration:** Eradicated human configuration errors by defining the server architecture purely through version-controlled text files.
*   **Immediate Environmental Recovery:** If the container freezes or crashes, running `terraform destroy` followed by `terraform apply` builds a pristine, functional server automatically in seconds.
*   **Resource Efficiency:** Leveraging localized virtualization tools allows for complete infrastructure prototyping without incurring cloud subscription billing or platform costs.

---
*This project was built as part of my practical portfolio alongside my Open University Q62 (Computing & IT) degree.*
