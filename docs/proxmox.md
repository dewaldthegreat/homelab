# Proxmox VE

Proxmox VE is the core virtualization platform in my homelab. I use it to run a mix of Linux containers and virtual machines, separate services into individual workloads, manage storage, and experiment with networking and virtualization in a practical environment.

## Host Hardware

| Component | Specification |
|---|---|
| CPU | Intel Core i7-10700 |
| Cores / Threads | 8 Cores / 16 Threads |
| Memory | 32 GB DDR4 |
| Storage | SSD + 4 TB HDD storage |
| Networking | Dual Gigabit Ethernet |
| Hypervisor | Proxmox VE |

## Current Workloads

### Linux Containers (LXC)

| ID | Name | Purpose |
|---:|---|---|
| 101 | Jellyfin | Self-hosted media server for streaming media across the home network. |
| 102 | debianSMB | Debian-based file server providing SMB network shares. |
| 103 | Uptime Kuma | Service monitoring and uptime tracking for homelab services. |
| 104 | Homepage | Self-hosted dashboard for organizing and accessing homelab services. |
| 108 | Pi-hole | Network-wide DNS filtering and blocking for clients on the network. |
| 109 | Immich | Self-hosted photo and video management platform. |
| 112 | GLPI | IT service management and Help Desk training environment. |
| 113 | remote-gateway | Remote-access and networking gateway lab. |
| 114 | hermesagent | AI agent and automation environment. |
| 115 | firecrawl | Self-hosted web crawling and retrieval service. |
| 116 | openwebui | Local AI web interface and model experimentation. |

I use LXC containers for services that benefit from lightweight isolation without requiring a complete virtual machine.

### Virtual Machines

| ID | Name | Purpose |
|---:|---|---|
| 100 | Home Assistant OS | Dedicated Home Assistant appliance VM for home automation. |
| 105 | OPNsense | Virtual firewall/router used for networking and firewall experimentation. |
| 106 | test | Linux VM used as a safe environment for Linux testing and experimentation. |
| 107 | Omarchy | Linux desktop VM used for desktop Linux experimentation. |
| 110 | AD-DC01 | Active Directory/domain-controller lab for Windows administration practice. |
| 111 | win11 | Windows 11 client VM for administration, client/domain testing, and Help Desk practice. |

Virtual machines are used when I want stronger isolation, a complete operating system, appliance-style deployment, or hardware/device configuration that is better suited to a VM.

## Help Desk & Windows Lab

The GLPI LXC provides a dedicated environment for practising IT support workflows without affecting production systems. The lab includes technician and Self-Service profiles, ITIL categories, ticket templates, simulated users, realistic support incidents, troubleshooting notes, solution documentation, and escalation practice.

The `AD-DC01` and `win11` VMs extend the lab into Windows administration and directory-services practice, providing a separate domain-controller environment and Windows client for identity, domain, policy, administration, and troubleshooting exercises.

See [GLPI Help Desk Lab](glpi-helpdesk.md) for the detailed setup and practice workflow.

## Storage

The Proxmox host currently exposes several storage targets:

| Storage | Role |
|---|---|
| `fourTB` | Main large-capacity storage backed by the 4 TB storage pool. |
| `local` | Proxmox local storage. |
| `local-lvm` | Local LVM-thin storage used by Proxmox for virtual disks. |
| `localnetwork` | Additional network-backed storage configured on the Proxmox host. |

I also use **ZFS** for storage management in the homelab and provide shared storage to other systems through SMB.

## How I Use Proxmox

My Proxmox environment gives me hands-on experience with:

- Creating and managing virtual machines
- Creating and managing Linux containers
- Resource allocation for CPU, memory, and storage
- Linux and Windows administration
- Active Directory and domain/client testing
- Virtual networking and bridges
- Firewall and routing labs with OPNsense
- Remote-access gateway experimentation
- ZFS and storage management
- Network file sharing
- GPU/device passthrough experimentation
- Service isolation
- Help Desk and IT service management labs
- Local AI and automation tooling
- Troubleshooting virtualized workloads
- Backups, recovery, and rebuilding services

## Why I Separate Services

Instead of running every service directly on one operating system, I separate workloads into individual VMs and containers where practical. This makes it easier to:

- Troubleshoot individual services
- Restart or rebuild one workload without affecting everything else
- Allocate resources independently
- Test changes in isolated environments
- Learn how real virtualized infrastructure is organized

## Security & Privacy

Public documentation intentionally excludes sensitive infrastructure information such as:

- Private and public IP addressing details
- Passwords and credentials
- API keys and authentication tokens
- VPN private keys
- Certificates and secrets
- Configuration containing personally identifying information

Any configuration examples added to this repository will be sanitized before publication.

---

This document is updated as the Proxmox environment changes and new workloads are added or retired.
