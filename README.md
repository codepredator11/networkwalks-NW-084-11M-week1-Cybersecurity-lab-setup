# networkwalks-NW-084-11M-week1-Cybersecurity-lab-setup
Cybersecurity lab setup

<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building a Virtual Cybersecurity and Penetration Testing Laboratory using Oracle VirtualBox and Kali Linux 2026.3**

<p>
<img src="https://img.shields.io/badge/Domain-Cybersecurity-C00000?style=flat-square" />
<img src="https://img.shields.io/badge/Hypervisor-VirtualBox%207.2-0070C0?style=flat-square" />
<img src="https://img.shields.io/badge/OS-Kali%20Linux%202026.3-E87500?style=flat-square&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/Network-NAT%20Network-238F89?style=flat-square" />
<img src="https://img.shields.io/badge/Purpose-Ethical%20Hacking-C00000?style=flat-square" />
</p>

</div>

---

## 📌 Project Overview

This project focuses on building a virtual cybersecurity and penetration-testing laboratory using Oracle VirtualBox and Kali Linux 2026.3.

The objective is to establish a controlled virtual environment where cybersecurity tools, network reconnaissance, port scanning, vulnerability assessment, packet analysis, and penetration-testing exercises can be performed.

Kali Linux is configured as the primary security-testing machine and connected through a dedicated VirtualBox NAT Network.

The environment can be expanded by adding additional virtual machines that will serve as targets for authorized security testing.

---

## 🎯 Project Objectives

- Install and configure Oracle VirtualBox.
- Set up Kali Linux 2026.3 as a virtual machine.
- Configure virtual machine hardware resources.
- Create and configure a dedicated NAT Network.
- Establish network connectivity for Kali Linux.
- Verify IP addressing and DNS resolution.
- Create a clean virtual machine snapshot.
- Prepare an isolated environment for penetration-testing practice.
- Document the complete laboratory setup.

---

## 🛡️ Purpose of the Lab

This laboratory provides a controlled environment for learning and practicing cybersecurity concepts.

It will be used for:

- Network reconnaissance
- Port scanning and service enumeration
- Vulnerability assessment
- Packet analysis
- Web application security testing
- Penetration-testing fundamentals
- Linux administration
- Security-tool experimentation

⚠️ **Ethical Notice:** All testing must be performed on systems owned by you or for which you have explicit authorization.

---

## 🏗️ Lab Architecture

The laboratory uses Oracle VirtualBox as the virtualization platform, with Kali Linux configured as the primary penetration-testing machine.

**Current Setup:**

- Host Machine: Windows
- Virtualization Platform: Oracle VirtualBox
- Security Machine: Kali Linux 2026.3
- Virtual Network: NAT Network
- Network Name: NatNetwork

Additional target machines can be connected to the same NAT Network in future projects.

---

## ⚙️ System Configuration

### Host Machine

| Component | Configuration |
|---|---|
| Host Operating System | Windows |
| Virtualization Software | Oracle VirtualBox 7.2 |
| Virtual Network | NAT Network |

### Kali Linux Virtual Machine

| Component | Configuration |
|---|---|
| VM Name | kali-linux-2026.3-virtualbox-amd64 |
| VM Description | My Fresh Kali Linux |
| Operating System | Kali Linux Rolling 2026.3 x64 |
| Base Memory | 2048 MB (2 GB) |
| Processors | 2 |
| Virtual Disk | 80.09 GB |
| Graphics Controller | VMSVGA |
| Video Memory | 128 MB |
| Audio Driver | Windows DirectSound |
| Audio Controller | ICH AC97 |
| Network Adapter | Intel PRO/1000 MT Desktop |
| Network Attachment | NAT Network |
| Network Name | NatNetwork |
| USB Controller | OHCI |
| Shared Folders | None |

---

# 🪜 Lab Setup Procedure

## Step 1: Install 7-Zip

7-Zip was installed to extract the downloaded Kali Linux virtual machine archive.

**Tool:** [7-Zip](https://www.7-zip.org/)

---

## Step 2: Install Oracle VirtualBox

Oracle VirtualBox was installed as the hypervisor to create and manage virtual machines.

**Download:** [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)

---

## Step 3: Download Kali Linux

Kali Linux 2026.3 VirtualBox image was downloaded from the official Kali Linux website.

**Download:** [Kali Linux](https://www.kali.org/get-kali/)

The downloaded virtual machine package was extracted using 7-Zip.

---

## Step 4: Import Kali Linux into VirtualBox

The extracted Kali Linux virtual machine was opened/imported into Oracle VirtualBox.

The VM was named:

```text
kali-linux-2026.3-virtualbox-amd64
```

The virtual machine was configured with 2 GB RAM and 2 processors.

**Virtual Machine Hardware Configuration:**

- RAM: 2048 MB
- CPU: 2 processors
- Virtual Disk: 80.09 GB
- Graphics: VMSVGA
- Video Memory: 128 MB

---

## Step 5: Configure Virtual Network

The Kali Linux network adapter was configured to use a dedicated NAT Network.

**Network Adapter Settings:**

```text
Adapter 1
Attached to: NAT Network
Network Name: NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

A NAT Network allows multiple virtual machines connected to the same virtual network to communicate with one another while providing outbound network connectivity.

This configuration will support the addition of target machines in future laboratory exercises.

---

## Step 6: Start Kali Linux

The virtual machine was started through VirtualBox Manager.

The initial Kali Linux login credentials supplied with the downloaded image were:

```text
Username: kali
Password: kali
```

These are default credentials and should be changed after the initial login.

---

## Step 7: Verify Network Configuration

After successfully starting Kali Linux, the network configuration can be checked using:

```bash
ip a
```

To check the default gateway:

```bash
ip route
```

To verify internet connectivity:

```bash
ping -c 4 8.8.8.8
```

To test DNS resolution:

```bash
nslookup google.com
```

To verify Nmap installation:

```bash
nmap --version
```

---

## Step 8: Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

**Suggested Snapshot Name:**

```text
Clean Kali Linux 2026.3 - Initial Setup
```

The snapshot provides a recovery point before performing penetration-testing exercises or making significant system changes.

---

# 🔎 Lab Verification

| Test | Command | Purpose |
|---|---|---|
| IP Address | `ip a` | Check network interface |
| Routing | `ip route` | Check default gateway |
| Internet | `ping -c 4 8.8.8.8` | Test connectivity |
| DNS | `nslookup google.com` | Verify DNS resolution |
| Nmap | `nmap --version` | Verify security tool |
| Network Interfaces | `ip link` | Inspect network interfaces |

---

# 🐞 Problems Encountered & Solutions

## 1. Virtualization Error

The virtual machine may fail to start if hardware virtualization is disabled.

**Solution:**

1. Restart the computer.
2. Enter BIOS/UEFI settings.
3. Enable Intel VT-x or the corresponding hardware virtualization option.
4. Save the changes.
5. Restart the computer.
6. Launch Kali Linux again.

## 2. Network Connectivity Issues

Network connectivity may fail because of incorrect adapter configuration or network settings.

**Troubleshooting:**

```bash
ip a
ip route
```

Restart NetworkManager if necessary:

```bash
sudo systemctl restart NetworkManager
```

Then verify connectivity again.

---

# 💡 What I Learned

Through this project, I gained practical experience in:

### 1. Virtualization

Understanding how Oracle VirtualBox creates and manages virtual machines.

### 2. Kali Linux Installation

Learning how to import, configure, and launch Kali Linux as a virtual machine.

### 3. Virtual Networking

Understanding NAT Network configuration and communication between virtual machines.

### 4. VM Hardware Allocation

Learning how to allocate RAM, CPU cores, virtual storage, and graphics resources.

### 5. Linux Networking

Practicing commands such as `ip a`, `ip route`, `ping`, and `nslookup`.

### 6. VM Snapshots

Understanding the importance of creating recovery points before conducting security experiments.

### 7. Documentation

Learning to document configurations, commands, screenshots, problems, and solutions clearly.

---

# 🔐 Security & Ethical Use

This laboratory is designed exclusively for educational purposes, cybersecurity research, and authorized penetration-testing activities.

All security testing must be conducted on systems that you own or have permission to assess.

---

# 🔗 Tools & Resources

- **7-Zip:** https://www.7-zip.org/
- **Oracle VirtualBox:** https://www.virtualbox.org/wiki/Downloads
- **Kali Linux:** https://www.kali.org/get-kali/
- **Kali Linux Documentation:** https://www.kali.org/docs/
- **Nmap:** https://nmap.org/

---

# 👤 Author

**Alan Nadh U**

Cybersecurity Enthusiast | Ethical Hacking | Linux | Network Security

---

## 📌 Project Information

| Field | Details |
|---|---|
| Project | Cybersecurity & Penetration Testing Lab Setup |
| Week | 01 |
| Platform | Oracle VirtualBox 7.2 |
| Security OS | Kali Linux 2026.3 |
| Virtual Network | NAT Network |
| Status | Initial VM Setup |

**Next Phase:** Adding target virtual machines and configuring the laboratory for network reconnaissance, vulnerability assessment, and penetration-testing exercises.
