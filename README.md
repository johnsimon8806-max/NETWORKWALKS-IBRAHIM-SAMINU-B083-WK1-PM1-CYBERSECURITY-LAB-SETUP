# Local Cybersecurity & Penetration Testing Environment

A fully isolated, safe virtual network laboratory built for conducting hands-on security research, network analysis, and ethical hacking experiments.

---

## Technical Overview

The objective of this environment is to provide a sandbox network decoupled from local production systems. This setup enables controlled security testing, packet inspection, and tool validation without impacting real-world infrastructure or host resources.

This lab was created to simulate a realistic cybersecurity practice environment in a controlled virtualized space, making it suitable for hands-on learning, experimentation, and secure development testing.

---

## Hardware & Software Specifications

* **Hypervisor Engine:** Oracle VM VirtualBox 7.0
* **Attack Platform:** Kali Linux 2026
* **Host Operating System:** Windows 10/11
* **Target Architecture:** Isolated virtual NAT lab
* **Primary IP Subnet:** 10.0.0.0/24
* **Network Type:** NAT Network
* **Primary DNS:** 8.8.8.8
* **Security Scope:** Educational and ethically authorized use only

---

## Lab Architecture & IP Allocation

```text
[ Host Machine ] 
       │
       └── [ VirtualBox Internal Engine ]
                 │
                 └── [ Isolated NAT Network (10.0.0.0/24) ]
                           │
                           ├── Router Gateway: 10.0.0.1
                           └── Kali Linux VM:  10.0.0.2
```

```text
Parameter                 Assigned Value
--------------------------------------------
Network Type             NAT Network (NatNetwork)
Subnet CIDR              10.0.0.0/24
Gateway IP               10.0.0.1
Kali VM Address          10.0.0.2/24
Upstream DNS             8.8.8.8
```

---

## Deployment & Setup Guide

### Phase 1: Installation of VirtualBox
1. Download and install Oracle VM VirtualBox 7.0 on the Windows host machine.
2. Install the VirtualBox Extension Pack for better functionality and networking support.
3. Launch VirtualBox and verify that the installation is successful.

### Phase 2: Creating the NAT Network
1. Open VirtualBox in Expert Mode.
2. Navigate to:
   - File > Tools > Network Manager
3. Create a NAT Network named `NatNetwork`.
4. Set the network details as:
   - Subnet: `10.0.0.0/24`
   - Gateway: `10.0.0.1`
   - DNS: `8.8.8.8`

### Phase 3: Creating the Kali Linux Virtual Machine
1. Click **New** in VirtualBox.
2. Configure the following:
   - Name: `Kali Linux`
   - Type: `Linux`
   - Version: `Debian (64-bit)`
   - RAM: 2-4 GB
   - Storage: 20-30 GB dynamically allocated
3. Attach the Kali Linux ISO image.
4. Configure the network adapter to use the NAT Network.

### Phase 4: Kali Linux Installation
1. Boot the newly created VM from the Kali Linux ISO.
2. Complete the installation process using the standard setup wizard.
3. Set a secure username and password.
4. Reboot the VM after installation completes.

---

## System Configuration

After installation, verify that the VM has been assigned the appropriate IP address and connectivity.

```bash
ip addr show
ip route
ping 10.0.0.1
ping 8.8.8.8
ping google.com
```

Expected behavior:
- The Kali VM should receive an IP in the `10.0.0.0/24` subnet
- Gateway reachability should succeed
- DNS resolution should work
- Internet access should be available through NAT

---

## Troubleshooting & Common Issues

### Issue 1: Network Settings Not Visible
During the setup, the network bar and NAT settings were not visible because VirtualBox was started in Basic Mode instead of Expert Mode.

#### Resolution
1. Close VirtualBox.
2. Reopen it in Expert Mode.
3. Navigate to the network configuration settings.
4. Create the NAT network and attach the VM to it.

This issue was resolved by switching from Basic Mode to Expert Mode, which exposes the full networking configuration options required for lab setup.

---

### Issue 2: Kali Linux VM Failed to Start
The Kali Linux virtual machine had trouble starting and booting correctly during setup.

#### Resolution
1. Verified the installation ISO was correctly attached.
2. Reviewed the VM configuration and boot order.
3. Checked that the virtual machine had enough assigned resources.
4. Reconfigured settings according to the guidance provided by the administrator.
5. Restarted the VM and completed the installation process successfully.

This issue was resolved by following the troubleshooting guidance and correcting the VM configuration.

---

## Connectivity Testing Results

The following tests were performed to confirm the environment was functioning properly:

```bash
ping -c 4 10.0.0.1
ping -c 4 8.8.8.8
ping -c 4 google.com
```

### Results
- Gateway reachability: Successful
- DNS resolution: Successful
- Internet access through NAT: Successful
- Kali Linux VM connectivity: Confirmed

---

## Lab Notes

This cybersecurity environment is intended for:

- Secure educational learning
- Packet analysis exercises
- Network troubleshooting practice
- Ethical hacking and security research in a safe sandbox
- Controlled testing without affecting production systems

This lab remains isolated from the host environment and is designed for authorized, safe experimentation only.

---

## Operational Scope & Ethics

This virtual environment is built exclusively for authorized testing and educational learning. All operations are confined to private virtual adapters to prevent unauthorized access to external networks or real production systems.

The environment must be used responsibly and only for:
- Learning
- Security testing with proper authorization
- Research within the isolated lab environment

It must not be used for malicious, illegal, or unauthorized activity.

---

## Security Reminder

- Use only in an isolated environment
- Never connect this lab to a live production network
- Do not test against systems without permission
- Keep all activity within the configured NAT-only environment

---

## Project Summary

This project successfully created a controlled cybersecurity lab using:
- Oracle VM VirtualBox
- Kali Linux 2026
- NAT Network configuration
- Safe, isolated virtual infrastructure

The environment provides a practical foundation for future cybersecurity tasks such as:
- Packet sniffing
- Network analysis
- Exploit testing
- System hardening experiments
- Ethical hacking skill development

---

## Conclusion

The lab setup was completed successfully and the environment is operational for ethical cybersecurity learning and testing. The NAT network model provides a secure and isolated framework for practical experimentation while minimizing risk to the host machine and external networks.

---

## Student Information

**Student Name:** Ibrahim Saminu  
**Course:** Network Walks  
**Week:** Week 1  
**Project:** Cybersecurity Lab Setup
