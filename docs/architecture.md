# Homelab Architecture

This document provides a high-level overview of my homelab architecture.

## Core Platform

The lab is centered around a **Proxmox VE** host that runs virtual machines and Linux containers.

The main areas of the environment are:

- Virtualization with Proxmox VE
- Linux server and desktop workloads
- ZFS-backed storage
- SMB file sharing
- Network and firewall experimentation with OPNsense
- DNS filtering with Pi-hole
- Self-hosted media with Jellyfin
- Home automation with Home Assistant and ESPHome
- Local desktop and game streaming with Sunshine and Moonlight

## High-Level Layout

```text
Home Network
    |
    +-- Proxmox VE Host
    |     |
    |     +-- Virtual Machines
    |     +-- Linux Containers
    |     +-- ZFS Storage
    |
    +-- Network Services
    +-- Home Automation
    +-- Client Devices
```

## Design Goals

- Learn by running real services
- Keep the environment easy to rebuild and document
- Separate experiments from important services where practical
- Improve reliability and security over time
- Avoid publishing sensitive addressing, credentials, or private configuration

This document will be expanded as the homelab changes.
