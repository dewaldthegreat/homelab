<div align="center">

# 🏠 Dewald's Homelab

### Hands-on infrastructure for learning virtualization, networking, Linux, self-hosting, storage, and automation.

![Proxmox](https://img.shields.io/badge/Proxmox-E57000?style=for-the-badge&logo=proxmox&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Home Assistant](https://img.shields.io/badge/Home_Assistant-18BCF2?style=for-the-badge&logo=homeassistant&logoColor=white)
![Pi-hole](https://img.shields.io/badge/Pi--hole-96060C?style=for-the-badge&logo=pihole&logoColor=white)

**[Architecture](docs/architecture.md) · [Proxmox](docs/proxmox.md) · [Networking](docs/networking.md) · [Storage](docs/storage.md) · [Services](docs/services.md) · [GLPI Help Desk](docs/glpi-helpdesk.md) · [Troubleshooting](docs/troubleshooting.md) · [Diagrams](diagrams/README.md) · [Roadmap](ROADMAP.md)**

</div>

---

## 📖 About

This repository documents my personal homelab and the systems I use to build practical experience with IT infrastructure.

I use the lab to learn by running real services, testing changes, troubleshooting failures, and documenting what I discover. Areas I actively work with include:

- Virtualization and containers
- Linux administration
- Networking and DNS
- Storage and file sharing
- Self-hosted services
- Home automation
- Monitoring
- PC hardware and troubleshooting
- Help Desk and service-desk workflows

This is a living lab rather than a finished project. The layout and services change as I learn and experiment.

---

## 🖥️ Main Server

My primary server runs **Proxmox VE** and provides the virtualization platform for the lab.

| Component | Specification |
|---|---|
| CPU | Intel Core i7-10700 |
| Cores / Threads | 8 Cores / 16 Threads |
| Memory | 32 GB DDR4 |
| Storage | SSD + 4 TB HDD storage |
| Networking | Dual Gigabit Ethernet |
| Hypervisor | Proxmox VE |

---

## 🧩 Current Proxmox Workloads

### Linux Containers (LXC)

| ID | Name | Role |
|---:|---|---|
| 101 | `jellyfin` | Self-hosted media server |
| 102 | `debianSMB` | Debian-based SMB file sharing |
| 103 | `uptimekuma` | Service availability monitoring |
| 104 | `homepage` | Homelab service dashboard |
| 108 | `pihole` | Network-wide DNS filtering |
| 109 | `immich` | Self-hosted photo management |
| 112 | `glpi` | IT service management and Help Desk training |

### Virtual Machines

| ID | Name | Role |
|---:|---|---|
| 100 | `haos18-2` | Home Assistant OS |
| 105 | `opnsense` | Firewall and networking lab |
| 106 | `test` | Linux testing and experimentation |
| 107 | `Omarchy` | Linux desktop environment |

---

## 💾 Storage Overview

| Storage | Role |
|---|---|
| `fourTB` | Higher-capacity homelab data storage |
| `local` | Proxmox local storage |
| `local-lvm` | VM and LXC disk storage |

Detailed notes are in [docs/storage.md](docs/storage.md).

---

## 🧱 Architecture

```text
Proxmox VE Host (pve)
|
+-- VMs
|   +-- Home Assistant OS
|   +-- OPNsense
|   +-- Linux test VM
|   +-- Omarchy
|
+-- LXCs
|   +-- Jellyfin
|   +-- debianSMB
|   +-- Uptime Kuma
|   +-- Homepage
|   +-- Pi-hole
|   +-- Immich
|   +-- GLPI Help Desk
|
+-- Storage
    +-- fourTB
    +-- local
    +-- local-lvm
```

See the [architecture documentation](docs/architecture.md) and [diagrams](diagrams/README.md) for more detail.

---

## ⚙️ Services & Technologies

### Virtualization

**Proxmox VE** is the main platform for running virtual machines and Linux containers.

### Networking

- **OPNsense** — routing, firewalling, interfaces, and network experimentation
- **Pi-hole** — DNS-based network filtering
- **Uptime Kuma** — monitoring service reachability

### Storage & File Sharing

- **ZFS** — storage-management learning and data organization
- **SMB** — network file sharing through the `debianSMB` LXC

### Media & Photos

- **Jellyfin** — self-hosted media
- **Immich** — self-hosted photo management and backup

### Home Automation

- **Home Assistant OS** — central home-automation platform
- **ESPHome** — ESP32-based automation and electronics projects

### Help Desk & ITSM

- **GLPI** — self-hosted ticketing environment for practising incident handling, service requests, user communication, documentation, troubleshooting, and escalation

### Desktop & Streaming

- **Omarchy** — Linux desktop VM
- **Sunshine + Moonlight** — low-latency desktop and game streaming on the local network

---

## 🛠️ Troubleshooting Case Studies

I document real troubleshooting situations to show the investigation process, the steps I tested, the result, and what I learned.

Current case study:

- **Windows PC boot loop and motherboard beep codes** — used the beep-code pattern to narrow down a likely hardware/RAM issue, powered the system down safely, reseated the RAM, cleared CMOS during troubleshooting, and re-tested the machine until it booted normally.

See [Troubleshooting Case Studies](docs/troubleshooting.md) for the full write-up.

---

## 📚 Documentation

| Page | What it covers |
|---|---|
| [Architecture](docs/architecture.md) | Overall design and workload layout |
| [Proxmox](docs/proxmox.md) | Host, VMs, LXCs, storage and virtualization |
| [Networking](docs/networking.md) | Network services and concepts |
| [Storage](docs/storage.md) | Proxmox storage, ZFS and SMB |
| [Services](docs/services.md) | Current hosted workloads |
| [GLPI Help Desk](docs/glpi-helpdesk.md) | Help Desk lab, ticket workflows, troubleshooting and escalation practice |
| [Troubleshooting](docs/troubleshooting.md) | Real troubleshooting case studies and lessons learned |
| [Home Assistant](docs/home-assistant.md) | Home Assistant OS and ESPHome |
| [Media](docs/media.md) | Jellyfin and Immich |
| [Monitoring](docs/monitoring.md) | Uptime Kuma and Homepage |
| [OPNsense](docs/opnsense.md) | Firewall and routing lab |
| [Pi-hole](docs/pihole.md) | DNS filtering |
| [SMB](docs/smb.md) | Debian SMB file sharing |
| [Linux Lab](docs/linux-lab.md) | Linux test VM and experimentation |
| [Remote Desktop](docs/remote-desktop.md) | Sunshine, Moonlight and Omarchy |
| [Diagrams](diagrams/README.md) | Sanitized topology diagrams |
| [Sanitized Configs](configs/README.md) | Rules for safe public config examples |

---

## 🚧 Homelab Status

**Status: Active and evolving**

The homelab changes regularly as I test software, reorganize services, learn new concepts, and improve reliability. The repository is intended to track that progression rather than present the environment as permanently finished.

Planned improvements and learning goals are tracked in [ROADMAP.md](ROADMAP.md), while notable repository and lab-documentation changes are tracked in [CHANGELOG.md](CHANGELOG.md).

---

## 🔐 Security & Privacy

This repository is public, so documentation is deliberately sanitized.

It does **not** intentionally publish:

- Passwords
- API keys or authentication tokens
- VPN/SSH private keys
- Private certificates
- Wi-Fi credentials
- Internal addressing that is unnecessary to the documentation
- Sensitive firewall rules
- Private external endpoints
- Personally identifying configuration data

See [SECURITY.md](SECURITY.md) and [configs/README.md](configs/README.md) for the repository's disclosure and sanitization rules.

---

<div align="center">

### Learning by building, testing, breaking, troubleshooting, and improving.

</div>
