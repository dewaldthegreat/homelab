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

I use LXC containers for services that benefit from lightweight isolation without requiring a complete virtual machine.

### Virtual Machines

| ID | Name | Purpose |
|---:|---|---|
| 100 | Home Assistant OS | Dedicated Home Assistant appliance VM for home automation. |
| 105 | OPNsense | Virtual firewall/router used for networking and firewall experimentation. |
| 106 | test | Linux VM used as a safe environment for Linux testing and experimentation. |
| 107 | Omarchy | Linux desktop VM used for desktop Linux experimentation. |

Virtual machines are used when I want stronger isolation, a complete operating system, appliance-style deployment, or hardware/device configuration that is better suited to a VM.

## Storage

The Proxmox host currently exposes several storage targets:

| Storage | Role |
|---|---|
| `fourTB` | Main large-capacity storage backed by the 4 TB storage pool. |
| `local` | Proxmox local storage. |
| `local-lvm` | Local LVM-thin storage used by Proxmox for virtual disks. |
| `localnetwork` | Additional storage configured on the Proxmox host. |

I also use **ZFS** for storage management in the homelab and provide shared storage to other systems through SMB.

## How I Use Proxmox

My Proxmox environment gives me hands-on experience with:

- Creating and managing virtual machines
- Creating and managing Linux containers
- Resource allocation for CPU, memory, and storage
- Linux server administration
- Virtual networking and bridges
- Firewall and routing labs with OPNsense
- ZFS and storage management
- Network file sharing
- GPU/device passthrough experimentation
- Service isolation
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
