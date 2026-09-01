# Homelab Architecture

This document provides a high-level view of my current homelab architecture without exposing private addressing or sensitive configuration.

## Core Platform

The lab is centered around a single **Proxmox VE** host named `pve`.

The host provides:

- Virtual machines
- Linux containers (LXC)
- Local and large-capacity storage
- Virtual networking
- A platform for testing, self-hosting, and troubleshooting

## Current Workload Layout

```text
Proxmox VE Host (pve)
|
+-- Virtual Machines
|   +-- 100  haos18-2   -> Home Assistant OS
|   +-- 105  opnsense   -> Firewall / networking lab
|   +-- 106  test       -> Linux test VM
|   +-- 107  Omarchy    -> Linux desktop VM
|
+-- Linux Containers (LXC)
|   +-- 101  jellyfin   -> Media server
|   +-- 102  debianSMB  -> SMB file sharing
|   +-- 103  uptimekuma -> Service monitoring
|   +-- 104  homepage   -> Homelab dashboard
|   +-- 108  pihole     -> DNS filtering
|   +-- 109  immich     -> Photo management
|   +-- 112  glpi       -> IT service management and Help Desk training
|
+-- Storage
    +-- fourTB      -> Higher-capacity homelab data storage
    +-- local       -> Proxmox local storage
    +-- local-lvm   -> VM/LXC disk storage
```

## Functional View

```text
                         Home Network
                              |
                         Proxmox VE
                              |
          +-------------------+-------------------+
          |                   |                   |
      Networking          Core Services        Storage
          |                   |                   |
      OPNsense VM          Pi-hole LXC          fourTB
                          Uptime Kuma           local
                          Homepage              local-lvm
          |                   |
          |              +----+-------------------------+
          |              |              |               |
       Routing        Jellyfin        Immich        debianSMB
       Firewall          Media          Photos          Files

                     Home Automation
                           |
                    Home Assistant OS
                           |
                        ESPHome
```

The diagram is intentionally conceptual. It shows service relationships without publishing IP addresses, subnets, external endpoints, or credentials.

## Design Approach

I use a mixture of VMs and LXCs depending on the workload.

### Virtual Machines

VMs are useful when I want stronger separation, a complete operating system, or a workload that makes sense as its own appliance or desktop environment.

Current examples include:

- Home Assistant OS
- OPNsense
- Linux testing
- Omarchy

### Linux Containers

LXCs are used for lightweight server workloads and self-hosted services.

Current examples include:

- Jellyfin
- SMB file sharing
- Uptime Kuma
- Homepage
- Pi-hole
- Immich
- GLPI Help Desk

## Design Goals

- Learn by operating real services
- Separate important services from experiments where practical
- Keep workloads understandable and independently manageable
- Improve reliability and security over time
- Document changes and lessons learned
- Keep all public documentation sanitized

## Related Documentation

- [Proxmox VE](proxmox.md)
- [Networking](networking.md)
- [Storage](storage.md)
- [Services](services.md)
- [GLPI Help Desk Lab](glpi-helpdesk.md)
- [Diagrams](../diagrams/README.md)
