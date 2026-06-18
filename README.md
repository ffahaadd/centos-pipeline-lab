# Secure Automated Deployment Pipeline Architecture

A hands-on systems engineering lab demonstrating container isolation, automated version control syncing, enterprise firewall configuration, and packet-level network analysis.

# Infrastructure Architecture Overview

This project establishes a local continuous deployment loop crossing host operating boundaries to simulate a production-ready application pipeline:

1. **Development Layer:** Source code managed and version-tracked using Git within VS Code on a Windows workstation host.
2. **Distribution Layer:** Code changes pushed upstream to a remote GitHub repository repository, serving as the single source of truth.
3. **Host & Virtualization Layer:** A CentOS Linux Enterprise environment hosted via VMware workstation acting as the target production deployment server.
4. **Containerization Layer (Docker):** Isolated application deployment utilizing an Nginx container image, utilizing volume binding maps (`:Z` SELinux flags) to link host deployment paths directly into containerized runtimes.
5. **Security Boundary Layer:** Network enforcement handled via `firewalld`, explicitly restricting traffic access exclusively to monitored HTTP (Port 80) and secure management interfaces.
6. **Network Observation Layer:** Live verification of endpoint connection integrity, structural TCP 3-Way Handshakes (`[SYN]`, `[SYN-ACK]`, `[ACK]`), and active HTTP protocol payload analysis executed via Wireshark.

# Tech Stack & Tools Utilized
* **OS Platforms:** Windows 11 (Host) | CentOS Linux (Server)
* **Virtualization:** VMware Workstation
* **Containers & Orchestration:** Docker | Docker Engine
* **Version Control:** Git | GitHub Cloud
* **Networking & Security:** Firewalld (Linux Linux Netfilter) | Wireshark Packet Analyzer
* **Web Services:** Nginx Server
