# Local Cybersecurity & Penetration Testing Environment

A fully isolated, safe virtual network laboratory built for conducting hands-on security research, network analysis, and ethical hacking experiments.

---

## Technical Overview

The objective of this environment is to provide a sandbox network decoupled from local production systems. This setup enables controlled security testing, packet inspection, and tool validation without risk to external hardware or live networks.

### Hardware & Software Specifications

* **Hypervisor Engine:** Oracle VM VirtualBox
* **Attack Platform:** Kali Linux
* **Target Architecture:** Scalable subnets configured for modular VM addition
* **Primary IP Subnet:** 10.0.0.0/24

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
