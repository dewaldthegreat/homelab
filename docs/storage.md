# Storage

Storage in my homelab is managed through Proxmox VE and is split between host storage, virtual-machine/container storage, and higher-capacity data storage.

## Current Proxmox Storage

| Storage | Purpose |
|---|---|
| `fourTB` | Large-capacity storage used for homelab data and shared storage workloads |
| `local` | Proxmox local storage used for host-managed files such as ISOs, templates, and other local content |
| `local-lvm` | Proxmox LVM-thin storage used for virtual machine and container disks |

The physical system includes an SSD and a 4 TB HDD. Storage roles can change as the lab evolves, so this page focuses on the logical layout rather than publishing private mount paths or detailed live configuration.

## ZFS

I use ZFS in the homelab to learn and work with concepts such as:

- Pools and datasets
- Storage allocation
- Data organization
- Permissions
- Capacity planning
- Recovery and backup concepts

## Network File Storage

LXC **102 (`debianSMB`)** provides SMB file sharing for systems on the local network.

This lets me practice:

- Linux file permissions
- SMB shares
- Client access and troubleshooting
- Shared-storage organization
- Service-to-storage connectivity

## VM and Container Storage

Proxmox separates storage used by the host from storage assigned to virtual machines and containers. This gives me hands-on experience with deciding where workloads should live and how storage choices affect management and recovery.

## Backup & Recovery

Backup and recovery are areas I continue to improve. My documentation focuses on the concepts and structure of the environment without publishing live backup destinations, credentials, or private paths.

## What I Am Learning

- ZFS storage management
- VM and LXC disk allocation
- SMB and network shares
- Linux permissions
- Storage capacity planning
- Backup and recovery concepts
- Separating application data from operating-system storage

## Public Documentation Policy

This repository intentionally omits sensitive storage details including:

- Private mount paths where they could reveal personal information
- Credentials
- Share passwords
- Private backup destinations
- Authentication information
- Sensitive file or folder names
