gr# Cybersecurity Lab Setup - NETWORKWALKS
## Ibrahim Saminu | B083 | WK1 PM1

**My first experience in cybersecurity engineering**

---

## Overview

This repository documents my initial setup and configuration of a cybersecurity lab environment using Oracle VirtualBox and Kali Linux. The lab is designed for network security testing and learning fundamental cybersecurity concepts.

---

## Lab Components

### 1. **VirtualBox Network Manager**
The foundation of our virtual lab environment where we configure isolated networks for safe testing.

![VirtualBox Network Configuration](screenshots/01-virtualbox-network-config.png)

**Configuration Details:**
- **Network Name:** NatNetwork
- **IPv4 Prefix:** 10.0.0.0/24
- **IPv6 Prefix:** fd17:625c:f037::/64
- **DHCP Server:** Enabled
- **Purpose:** Provides NAT networking for virtual machines

---

### 2. **Kali Linux Homepage**
Kali Linux is a specialized Linux distribution for penetration testing and cybersecurity auditing.

![Kali Linux Homepage](screenshots/02-kali-linux-homepage.png)

**Key Features:**
- Pre-installed penetration testing tools
- Network analysis utilities
- Vulnerability assessment frameworks
- Ethical hacking toolset
- Comprehensive documentation available at kali.org

---

### 3. **Kali Network Configuration**
Fine-tuning network settings on the Kali Linux VM for optimal lab performance.

![Kali Network Settings](screenshots/03-kali-network-settings.png)

**Network Setup:**
- **Connection Name:** Wired connection 1
- **IPv4 Method:** Manual
- **IP Address:** 10.0.0.2
- **Netmask:** 24 (10.0.0.0/24)
- **Gateway:** 10.0.0.1
- **DNS Server:** 8.8.8.8
- **Purpose:** Static IP assignment for consistent network access

---

### 4. **VirtualBox Welcome Screen**
The main VirtualBox interface showing available virtual machines and lab resources.

![VirtualBox Welcome](screenshots/04-virtualbox-welcome.png)

**Next Steps:**
- Create new virtual machines
- Import existing VM images
- Configure machine settings
- Manage snapshots and backups

---

## Lab Objectives

- [x] Install and configure VirtualBox
- [x] Set up isolated network environment (NatNetwork)
- [x] Deploy Kali Linux virtual machine
- [x] Configure static networking for lab VMs
- [ ] Set up additional security tools
- [ ] Document penetration testing scenarios
- [ ] Create network topology diagrams

---

## Technology Stack

| Component | Details |
|-----------|---------|
| **Hypervisor** | Oracle VirtualBox 7.x |
| **OS** | Kali Linux (Latest) |
| **Network** | NAT Network - 10.0.0.0/24 |
| **Kernel** | Linux (Kali) |
| **Tools** | Metasploit, Wireshark, Nmap, etc. |

---

## Network Architecture

```
┌─────────────────────────────────────┐
│    Host Machine (Windows/Linux)     │
└──────────────────┬──────────────────┘
                   │
        ┌──────────▼──────────┐
        │   VirtualBox NAT    │
        │   Network 10.0.0.0  │
        └──────────┬──────────┘
                   │
        ┌──────────▼──────────┐
        │  Kali Linux VM      │
        │  IP: 10.0.0.2       │
        │  Gateway: 10.0.0.1  │
        └─────────────────────┘
```

---

## Getting Started

### Prerequisites
- Oracle VirtualBox installed
- Minimum 4GB RAM available
- 20GB disk space for Kali Linux
- Host machine with administrative access

### Quick Start
1. Launch VirtualBox
2. Create new virtual machine
3. Allocate resources (2+ CPU cores, 2-4GB RAM)
4. Install Kali Linux
5. Configure network using NatNetwork
6. Install additional tools as needed

---

## Lab Usage Guidelines

### Security Practices
- ✅ Always use isolated networks for testing
- ✅ Create snapshots before major changes
- ✅ Document all configurations
- ✅ Use strong credentials for VMs
- ✅ Enable logging for audit trails

### Do's and Don'ts
- ✅ DO practice ethical hacking only
- ✅ DO get proper authorization before testing
- ✅ DO keep VMs updated with security patches
- ❌ DON'T use these skills without consent
- ❌ DON'T connect lab VMs to production networks

---

## Resources & References

- [Kali Linux Official Documentation](https://docs.kali.org/)
- [VirtualBox Documentation](https://www.virtualbox.org/wiki/Documentation)
- [OWASP Penetration Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [Metasploit Framework](https://www.metasploit.com/)

---

## Learning Outcomes

Through this lab setup, I am learning:
- Virtual machine management and networking
- Linux system administration
- Network configuration and protocols
- Cybersecurity fundamentals
- Ethical hacking methodologies
- Professional documentation practices

---

## Future Enhancements

- [ ] Add Windows Server VM for domain testing
- [ ] Configure VPN for secure access
- [ ] Set up vulnerable apps (DVWA, WebGoat)
- [ ] Create network intrusion detection system
- [ ] Document common attack scenarios
- [ ] Establish incident response procedures

---

## Contact & Support

**Author:** Ibrahim Saminu  
**Course:** B083 - WK1 PM1 Cybersecurity Lab  
**Repository:** [NETWORKWALKS-IBRAHIM-SAMINU-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP](https://github.com/johnsimon8806-max/NETWORKWALKS-IBRAHIM-SAMINU-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP)

---

## License

This project is for educational purposes only. All tools and techniques documented here should be used responsibly and ethically, with proper authorization.

---

**Last Updated:** September 26, 2026  
**Status:** Lab Setup Complete ✓
