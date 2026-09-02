# Homelab Architecture

This document provides a high-level view of my current homelab architecture without exposing private addressing or sensitive configuration.

## Core Platform

The lab is centered around a single **Proxmox VE** host named `pve`.

The host provides:

- Virtual machines
- Linux containers (LXC)
- Local and network-backed storage
- Virtual networking
- A platform for testing, self-hosting, automation, and troubleshooting

## Current Workload Layout

```text
Proxmox VE Host (pve)
|
+-- Virtual Machines
|   +-- 100  haos18-2   -> Home Assistant OS
|   +-- 105  opnsense   -> Firewall / networking lab
|   +-- 106  test       -> Linux test VM
|   +-- 107  Omarchy    -> Linux desktop VM
|   +-- 110  AD-DC01    -> Active Directory / domain controller lab
|   +-- 111  win11      -> Windows 11 client and administration lab
|
+-- Linux Containers (LXC)
|   +-- 101  jellyfin       -> Media server
|   +-- 102  debianSMB      -> SMB file sharing
|   +-- 103  uptimekuma     -> Service monitoring
|   +-- 104  homepage       -> Homelab dashboard
|   +-- 108  pihole         -> DNS filtering
|   +-- 109  immich         -> Photo management
|   +-- 112  glpi           -> IT service management and Help Desk training
|   +-- 113  remote-gateway -> Remote-access / network gateway lab
|   +-- 114  hermesagent    -> AI agent and automation environment
|   +-- 115  firecrawl      -> Web crawling and retrieval service
|   +-- 116  openwebui      -> Local AI web interface
|
+-- Storage
    +-- fourTB       -> Higher-capacity homelab data storage
    +-- local        -> Proxmox local storage
    +-- local-lvm    -> VM/LXC disk storage
    +-- localnetwork -> Additional network-backed storage
```

## Functional View

```text
                              Home Network
                                   |
                              Proxmox VE
                                   |
        +--------------------------+--------------------------+
        |                          |                          |
    Networking                Core Services               Storage
        |                          |                          |
    OPNsense VM                 Pi-hole LXC                fourTB
    Remote Gateway             Uptime Kuma                 local
                               Homepage                    local-lvm
        |                          |                        localnetwork
        |                    +-----+------------------+
        |                    |            |           |
     Routing              Jellyfin      Immich    debianSMB
     Firewall               Media        Photos      Files
     Remote access

              +--------------------+--------------------+
              |                                         |
        Windows / IT Lab                              AI Lab
              |                                         |
          AD-DC01                                   Hermes Agent
          Windows 11                                 Firecrawl
          GLPI                                      Open WebUI

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
- Active Directory/domain-controller lab
- Windows 11 client lab

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
- Remote Gateway
- Hermes Agent
- Firecrawl
- Open WebUI

## Design Goals

- Learn by operating real services
- Separate important services from experiments where practical
- Keep workloads understandable and independently manageable
- Build hands-on Windows, Linux, networking, and IT support experience
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
