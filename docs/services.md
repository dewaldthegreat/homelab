# Services

This page tracks the main workloads currently running in my Proxmox homelab and what each one is used for.

## Linux Containers (LXC)

| ID | Name | Role |
|---:|---|---|
| 101 | `jellyfin` | Self-hosted media server |
| 102 | `debianSMB` | Debian-based SMB file sharing |
| 103 | `uptimekuma` | Service availability and uptime monitoring |
| 104 | `homepage` | Central dashboard for homelab services |
| 108 | `pihole` | Network-wide DNS filtering |
| 109 | `immich` | Self-hosted photo management and backup |
| 112 | `glpi` | IT service management and Help Desk training |
| 113 | `remote-gateway` | Remote-access and networking gateway lab |
| 114 | `hermesagent` | AI agent and automation environment |
| 115 | `firecrawl` | Self-hosted web crawling and retrieval service |
| 116 | `openwebui` | Local AI web interface and model experimentation |

### 101 — Jellyfin

Provides self-hosted media access on the home network and gives me experience managing a persistent network service and its storage requirements.

### 102 — debianSMB

Provides SMB network file sharing from a Debian container. I use it to learn Linux permissions, network shares, storage access, and troubleshooting.

### 103 — Uptime Kuma

Monitors whether important homelab services are reachable and helps me identify outages or service failures.

### 104 — Homepage

Provides a central dashboard for organizing and accessing homelab services.

### 108 — Pi-hole

Provides DNS-based filtering for devices on the network and gives me practical experience with DNS, filtering, and network troubleshooting.

### 109 — Immich

Provides self-hosted photo management and backup inside the homelab.

### 112 — GLPI

Provides a self-hosted Help Desk and IT service management environment. I use it to practise realistic ticket triage, incident and request handling, user communication, internal troubleshooting notes, solution documentation, and escalation decisions.

See [GLPI Help Desk Lab](glpi-helpdesk.md) for the detailed training setup and a documented DNS troubleshooting scenario.

### 113 — Remote Gateway

Provides a dedicated environment for remote-access and network-gateway experimentation while keeping the public documentation free of private addressing and endpoint details.

### 114 — Hermes Agent

Runs an AI-agent environment used for automation, tool orchestration, and practical experimentation with agent workflows.

### 115 — Firecrawl

Provides a self-hosted web crawling and retrieval service for experiments that need structured web content.

### 116 — Open WebUI

Provides a web interface for local AI model and workflow experimentation inside the homelab.

## Virtual Machines

| ID | Name | Role |
|---:|---|---|
| 100 | `haos18-2` | Home Assistant OS |
| 105 | `opnsense` | Firewall and networking lab |
| 106 | `test` | Linux testing and experimentation |
| 107 | `Omarchy` | Linux desktop environment |
| 110 | `AD-DC01` | Active Directory / domain controller lab |
| 111 | `win11` | Windows 11 client and administration lab |

### 100 — Home Assistant OS

Runs Home Assistant OS as the main home-automation platform. ESPHome is used alongside it for ESP32-based devices and experiments.

### 105 — OPNsense

Used as a virtual firewall/router environment for learning routing, firewall rules, interfaces, and network troubleshooting.

### 106 — test

A Linux virtual machine kept specifically for testing, experimentation, and learning without risking more important services.

### 107 — Omarchy

A Linux VM used as a desktop Linux environment in the lab.

### 110 — AD-DC01

Provides a Windows Active Directory/domain-controller lab for practising directory services, identity, domain administration, and related IT support tasks.

### 111 — win11

Provides a Windows 11 client environment for administration, domain/client testing, troubleshooting, and Help Desk practice.

## Other Technologies

### ESPHome

Used with ESP32 devices for custom home-automation and electronics projects.

### Sunshine + Moonlight

Used for low-latency desktop and game streaming across the local network.

## Service Design

Where practical, services are separated into their own VM or LXC. This makes it easier to:

- Learn service isolation
- Troubleshoot one workload at a time
- Rebuild individual services
- Allocate resources independently
- Understand dependencies between networking, storage, identity, and applications

## Documentation

More detailed pages are available for major parts of the lab:

- [Home Assistant and ESPHome](home-assistant.md)
- [Media and Photos](media.md)
- [Monitoring and Dashboard](monitoring.md)
- [OPNsense](opnsense.md)
- [Pi-hole](pihole.md)
- [SMB File Sharing](smb.md)
- [Linux Lab](linux-lab.md)
- [Remote Desktop and Streaming](remote-desktop.md)
- [GLPI Help Desk Lab](glpi-helpdesk.md)
