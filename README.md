# networkwalks-B083-week1-linux-lab-setup
cybersecurity lab-setup
# 🛡️ Kali Linux Cybersecurity Lab

![Kali Linux](https://img.shields.io/badge/Kali%20Linux-Cybersecurity-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-Virtual%20Lab-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Administration-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Learning-red?style=for-the-badge)

> **A hands-on cybersecurity laboratory built with Kali Linux running inside VirtualBox.**

This repository documents my practical cybersecurity learning journey, including
Linux administration, networking, reconnaissance, packet analysis, web security,
digital forensics, and security testing.

The goal of this project is to develop practical cybersecurity skills through
controlled laboratory exercises and document the knowledge gained along the way.

---

## 👨‍💻 About the Project

**Student:** Ssemakula Arthur  
**Field:** Cyber Security  
**Institution:** ISBAT University  
**Platform:** Kali Linux  
**Virtualization:** Oracle VirtualBox 
**linkedIn:** www.linkedin.com/in/ssemakula-arthur-614524405
 
This laboratory is designed as a personal and academic environment for
learning and practicing cybersecurity concepts in a controlled virtual
environment.

---

## 🎯 Objectives

The main objectives of this laboratory are to:

- Learn Linux system administration
- Understand Linux file systems and permissions
- Configure and troubleshoot network connections
- Learn basic networking and network security
- Perform ethical reconnaissance
- Understand network scanning
- Capture and analyze network traffic
- Explore web application security
- Learn basic digital forensics
- Practice cybersecurity tools in a controlled environment
- Document practical cybersecurity knowledge

---

# 🖥️ Laboratory Environment

The laboratory is built using a virtual machine running Kali Linux.

```text
                 CYBERSECURITY LAB
                       │
                       ▼
                ┌──────────────┐
                │  Windows PC  │
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │  VirtualBox  │
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │  Kali Linux  │
                │     VM       │
                └──────┬───────┘
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
     Linux         Networking      Security
   Administration    Tools          Tools

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
## Lab setup
https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linuxlab-setup/blob/main/Screenshot%202026-09-16%20093904.png

# 🪜 Lab building Procedure

##  Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.

**Tool:** 7-Zip


##  Install VirtualBox

VirtualBox was installed as the hypervisor.


##  Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-17%20005018.png
NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.
 Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-17%20005655.png

 Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

```text
Clean Kali - Network Setup
```

The snapshot represents the clean baseline of the laboratory.

https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-16%20092218.png

#  Lab Verification

|  Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
|  Check IP address           | `ip a`                          | Correct Kali IP displayed       |
|  Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
|  Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
|  Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
|  Verify Nmap                | `nmap --version`                | Nmap version displayed          |
|  Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-16%20092747.png

https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-16%20225257.png

https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-17%20004920.png

 Problems Encountered & Solutions


## Problem 1
Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.

One workaround used during this lab was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted/rebooted and connectivity was tested again.

https://github.com/ssemakulaarthur23/networkwalks-B083-week1-linux-lab-setup/blob/main/Screenshot%202026-09-17%20005655.png

 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.


###  Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

## Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

###  VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

###  Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---
