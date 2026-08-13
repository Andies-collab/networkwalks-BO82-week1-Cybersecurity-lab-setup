# 🔐 Cybersecurity Lab Environment Setup
Building an isolated virtual lab using VirtualBox and Kali Linux for cybersecurity learning and authorized security testing.

---

## 📌 Project Overview
This project documents the setup and configuration of a virtual
cybersecurity laboratory using Oracle VirtualBox and Kali Linux.

The laboratory provides a safe and isolated environment for
learning cybersecurity, networking, system administration, and
security testing without directly affecting the host computer
or external networks.

The lab was configured with a custom VirtualBox NAT Network
called `Kali-Network`, allowing the Kali Linux virtual machine
to communicate through a controlled virtual network while
maintaining Internet connectivity.



---

## 🎯 Objectives

The main objectives of this lab are to:

- Set up a virtual cybersecurity laboratory using VirtualBox.
- Configure and use Kali Linux as a virtual machine.
- Create and configure an isolated virtual network.
- Understand virtual network adapters and network interfaces.
- Configure IP addressing, gateway, and DNS.
- Verify network connectivity using Linux networking commands.
- Troubleshoot network configuration problems.
- Test Internet connectivity from Kali Linux.
- Document the complete laboratory setup and troubleshooting process.



  ---

## 🛡️ Purpose of the Lab

The purpose of this laboratory is to provide a safe and controlled
environment for learning and practicing cybersecurity and networking
concepts.

Using VirtualBox, the laboratory separates the virtual machines from
the normal host environment, allowing different network configurations
and security experiments to be performed without unnecessarily
affecting the host computer or external systems.

The isolated network also makes it possible to understand how virtual
machines communicate, how IP addresses are assigned, how gateways and
DNS work, and how network connectivity can be tested and troubleshot.

This laboratory will be used as a foundation for future cybersecurity
practical exercises and authorized security testing.

---

## 🏗️ Lab Environment

The cybersecurity laboratory was built using Oracle VirtualBox as the
virtualization platform and Kali Linux as the main security-focused
operating system.

### 💻 Host Machine

| Component | Specification |
|---|---|
| Operating System | Windows |
| Virtualization Software | Oracle VirtualBox |
| RAM | 8 GB |
| Processor | Intel Core i5 |
| Storage | 256 GB SSD |

### 🐉 Kali Linux Virtual Machine

| Component | Specification |
|---|---|
| Operating System | Kali Linux 2026.2 |
| VM Name | `kali-linux-2026.2-virtualbox-amd64` |
| RAM | 2048 MB |
| CPU | 2 cores |
| Network Adapter | Adapter 1 |
| Network Type | NAT Network |
| Network Name | `Kali-Network` |

### 🌐 Network Configuration

| Component | Configuration |
|---|---|
| Network Name | `Kali-Network` |
| Network Range | `10.0.0.0/24` |
| Gateway | `10.0.0.1` |
| Kali Interface | `eth0` |
| Kali IP Address | `10.0.0.3/24` |
| DNS | `8.8.8.8` |
| DHCP Server | Enabled |


---
## 🌐 Lab Network Architecture

The laboratory uses a custom VirtualBox NAT Network called
`Kali-Network`. The network operates within the `10.0.0.0/24`
address range.

The Kali Linux virtual machine uses `eth0` as its Ethernet interface
and is configured with the IP address `10.0.0.3/24`.

The default gateway is `10.0.0.1`, which provides network access,
while DNS `8.8.8.8` is used for domain name resolution.

---
## ⚙️ Lab Setup

### Step 1 — Install Archive Utility

The first step was to prepare an archive utility for extracting
the downloaded Kali Linux VirtualBox files.

The instructor recommended using 7-Zip for this step. However,
WinRAR was used instead because it was already available on the
host computer.

WinRAR was used to extract the downloaded Kali Linux VirtualBox
archive before importing the virtual machine into Oracle VirtualBox.

<img width="463" height="422" alt="WinRar_extracting" src="https://github.com/user-attachments/assets/c9cfe2e9-4573-4ebf-8b2a-feb447a39e05" />



### Step 2 — Install Oracle VirtualBox

Oracle VirtualBox was installed on the Windows host computer to
provide the virtualization platform for the cybersecurity laboratory.

VirtualBox allows a complete operating system such as Kali Linux
to run inside a virtual machine while using the resources of the
host computer.

After installation, VirtualBox was opened and prepared for the
Kali Linux virtual machine and the required network configuration.

**Virtualization software:** Oracle VirtualBox

<img width="1356" height="725" alt="virtualbox" src="https://github.com/user-attachments/assets/d5ec65bb-fa1b-4c77-bb05-dc2d17a14281" />


### Step 3 — Configure the VirtualBox NAT Network

A custom NAT Network named `Kali-Network` was created in Oracle
VirtualBox to provide a controlled network environment for the
Kali Linux virtual machine.

The network was configured with the `10.0.0.0/24` address range
and the gateway was set to `10.0.0.1`. DHCP was enabled to allow
the network to provide IP configuration to connected virtual
machines.

The final network configuration was verified using the
`VBoxManage` command in Windows Command Prompt.

**Network Name:** `Kali-Network`

**Network Range:** `10.0.0.0/24`

**Gateway:** `10.0.0.1`

**DHCP:** Enabled

<img width="651" height="588" alt="net_config" src="https://github.com/user-attachments/assets/9cda7788-9f2f-4410-9d60-11e6ff9e22ad" />


### Step 4 — Download and Import Kali Linux

Kali Linux was downloaded as a pre-built VirtualBox virtual machine
image. The downloaded archive was extracted using WinRAR and the
Kali Linux virtual machine was then imported into Oracle VirtualBox.

The imported virtual machine was checked to ensure that the virtual
disk was attached correctly and that the machine could start
successfully.

The Kali Linux virtual machine used in this laboratory was
`kali-linux-2026.2-virtualbox-amd64`.

**Operating System:** Kali Linux 2026.2

**Virtual Machine:** `kali-linux-2026.2-virtualbox-amd64`

**Virtualization Platform:** Oracle VirtualBox


<img width="1339" height="752" alt="kali_linux" src="https://github.com/user-attachments/assets/097bc382-1ede-4647-8394-5aafcdc7cd93" />

### Step 5 — Configure Kali Linux IP Settings

The Kali Linux network interface was configured to allow the
virtual machine to communicate through the VirtualBox NAT Network.

The Ethernet interface `eth0` was identified as the active network
interface. The final IPv4 configuration was set as follows:

- **Interface:** `eth0`
- **IPv4 Address:** `10.0.0.3/24`
- **Gateway:** `10.0.0.1`
- **DNS Server:** `8.8.8.8`

After applying the configuration, the network connection was
successfully activated.


<img width="676" height="312" alt="kali_config1" src="https://github.com/user-attachments/assets/da150678-bf84-4bae-a2b8-f62ff9993526" />


Internet connectivity was also tested successfully by accessing
Google from the Kali Linux virtual machine.

<img width="1363" height="693" alt="Internet_conn" src="https://github.com/user-attachments/assets/06766be6-ff29-4342-b3d5-7a2182c6cff0" />


### Step 6 — Create a VM Snapshot

After completing the Kali Linux and network configuration, a
snapshot of the virtual machine was created in Oracle VirtualBox.

The snapshot provides a restore point for the laboratory. If a
future configuration change or cybersecurity experiment causes
a problem, the virtual machine can be restored to this working
state without having to repeat the entire setup process.

The snapshot was created after confirming that the Kali Linux
network configuration and Internet connectivity were working
correctly.

**Snapshot purpose:** Backup and recovery

**Snapshot point:** Fully configured and working Kali Linux lab

<img width="827" height="710" alt="snapshot" src="https://github.com/user-attachments/assets/442c36d9-5bcb-4160-9ca3-a6b3153e271e" />
