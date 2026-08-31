# Homelab Architecture

This document provides a high-level overview of my current homelab architecture.

## Core Platform

The lab is centered around a **Proxmox VE** host that runs both virtual machines and Linux containers.

The environment currently includes:

- Virtualization with Proxmox VE
- Linux server and desktop workloads
- ZFS-backed storage
- SMB file sharing
- Network and firewall experimentation with OPNsense
- DNS filtering with Pi-hole
- Monitoring with Uptime Kuma
- A central service dashboard with Homepage
- Self-hosted media with Jellyfin
- Self-hosted photo management with Immich
- Home automation with Home Assistant and ESPHome
- Local desktop and game streaming with Sunshine and Moonlight

## Current Workload Layout

```text
Proxmox VE Host (pve)
|
+-- Virtual Machines
|   +-- 100  haos18-2   -> Home Assistant OS
|   +-- 105  opnsense   -> Firewall / networking lab
|   +-- 106  test       -> Linux test VM
|   +-- 107  Omarchy    -> Linux VM
|
+-- Linux Containers (LXC)
|   +-- 101  jellyfin   -> Media server
|   +-- 102  debianSMB  -> SMB file sharing
|   +-- 103  uptimekuma -> Service monitoring
|   +-- 104  homepage   -> Homelab dashboard
|   +-- 108  pihole     -> DNS filtering
|   +-- 109  immich     -> Photo management
|
+-- Storage
    +-- fourTB
    +-- local
    +-- local-lvm
```

## Design Goals

- Learn by running real services
- Keep the environment easy to rebuild and document
- Separate experiments from important services where practical
- Improve reliability and security over time
- Avoid publishing sensitive addressing, credentials, or private configuration

This document will continue to evolve as the homelab changes.
