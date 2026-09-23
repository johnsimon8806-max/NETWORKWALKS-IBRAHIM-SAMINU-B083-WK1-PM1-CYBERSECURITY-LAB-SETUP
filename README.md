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
ParameterAssigned ValueNetwork TypeNAT Network (NatNetwork)Subnet CIDR10.0.0.0/24Gateway IP10.0.0.1Kali VM Address10.0.0.2/24Upstream DNS8.8.8.8Deployment & Setup GuidePhase 1: Archive Extraction & Software SetupInstalled 7-Zip to handle multi-part virtual machine archives (.7z format).Deployed Oracle VM VirtualBox as the central virtualization manager.Phase 2: Virtual Network ProvisioningOpened VirtualBox Global Tools and configured a new NAT Network.Applied the IPv4 range 10.0.0.0/24 and disabled IPv6 to prevent unexpected address assignment conflicts.Phase 3: Kali Linux Virtual Machine ImportImported the pre-built Kali Linux virtual appliance into VirtualBox.Allocated 2048 MB RAM and 2 Virtual Processors for smooth command-line and graphical tool performance.Attached Network Adapter 1 directly to the custom NatNetwork.Phase 4: Network Interface Configuration & VerificationBooted Kali Linux and assigned a persistent IPv4 address to maintain static routing.Verified routing functionality using standard network diagnostic tools:Interface Check: ip aLocal Routing: ping 10.0.0.1External Connectivity: ping 8.8.8.8Maintenance & Recovery ProtocolsTo prevent loss of progress during aggressive security testing or manual configuration changes, a baseline state was saved using VirtualBox Snapshots:Snapshot Label: Baseline Setup - Clean InstallationPurpose: Restores the VM to a fully working network state instantly if system files or network configs become corrupt during exercises.Troubleshooting LogIssue 1: Host Virtualization ConflictSymptom: VirtualBox returned hardware acceleration errors when booting the VM.Resolution: Accessed system BIOS settings during boot and enabled Intel VT-x / AMD-V hardware virtualization modes.Issue 2: Network Interface Drop OutSymptom: Static IP assignment caused intermittent packet drop during DNS lookup.Resolution: Adjusted interface behavior via NetworkManager CLI to disable duplicate address detection delays:Bashsudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
Operational Scope & EthicsThis virtual environment is built exclusively for authorized testing and educational learning. All operations are confined to private virtual adapters to prevent unauthorized traffic from escaping to external production networks.Author InformationIbrahim SaminuCybersecurity Trainee | Cohort B083Project Reference: NETWORKWALKS-IBRAHIM-SAMINU-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
