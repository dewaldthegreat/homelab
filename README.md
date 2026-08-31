<div align="center">

# 🏠 Dewald's Homelab

### A hands-on environment for learning virtualization, networking, Linux, self-hosting, storage, and automation.

![Proxmox](https://img.shields.io/badge/Proxmox-E57000?style=for-the-badge&logo=proxmox&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Home Assistant](https://img.shields.io/badge/Home_Assistant-18BCF2?style=for-the-badge&logo=homeassistant&logoColor=white)
![Pi-hole](https://img.shields.io/badge/Pi--hole-96060C?style=for-the-badge&logo=pihole&logoColor=white)

</div>

---

## 📖 About

This repository documents my personal homelab and the systems I use to learn more about IT infrastructure.

My homelab gives me a practical environment where I can experiment with:

- Virtualization
- Linux administration
- Networking
- Storage
- Self-hosting
- Home automation
- Troubleshooting
- PC hardware

The goal of this repository is to document what I build, what I learn, problems I encounter, and how I solve them.

---

## 🖥️ Main Server

My primary server runs **Proxmox VE** and provides the virtualization platform for my lab.

### Hardware

| Component | Specification |
|---|---|
| CPU | Intel Core i7-10700 |
| Cores / Threads | 8 Cores / 16 Threads |
| Memory | 32 GB DDR4 |
| Storage | SSD + 4 TB HDD storage |
| Networking | Dual Gigabit Ethernet |
| Hypervisor | Proxmox VE |

---

## 🧱 Infrastructure

```text
                    ┌─────────────────────┐
                    │    Home Network     │
                    └──────────┬──────────┘
                               │
                        ┌──────▼──────┐
                        │   Proxmox   │
                        │    Host     │
                        └──────┬──────┘
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
        ┌────▼────┐       ┌────▼────┐       ┌────▼────┐
        │  VMs    │       │  LXCs   │       │ Storage │
        └─────────┘       └─────────┘       └─────────┘
             │                 │                 │
       HAOS / OPNsense    Self-hosted           ZFS
       Linux VMs          services               SMB
```

---

## 🧩 Current Proxmox Workloads

### Linux Containers (LXC)

| ID | Name | Role |
|---:|---|---|
| 101 | Jellyfin | Self-hosted media server |
| 102 | debianSMB | Debian-based SMB file sharing |
| 103 | Uptime Kuma | Service and uptime monitoring |
| 104 | Homepage | Homelab service dashboard |
| 108 | Pi-hole | Network-wide DNS filtering |
| 109 | Immich | Self-hosted photo management |

### Virtual Machines

| ID | Name | Role |
|---:|---|---|
| 100 | haos18-2 | Home Assistant OS |
| 105 | OPNsense | Firewall and networking lab |
| 106 | test | Linux test VM |
| 107 | Omarchy | Linux VM |

This inventory reflects the current Proxmox environment and will change as the lab evolves.

---

## ⚙️ Services & Technologies

### 🖥️ Virtualization

**Proxmox VE**

Used as the main virtualization platform for running virtual machines and Linux containers.

---

### 💾 Storage

**ZFS**

Used for managing storage on the Proxmox server and providing storage for services and network shares.

**SMB**

Used for sharing files across devices on the local network.

---

### 🌐 Networking

**OPNsense**

Used in my lab for experimenting with routing, firewalling, and network configuration.

**Pi-hole**

Provides network-wide DNS filtering.

---

### 📊 Monitoring & Dashboard

**Uptime Kuma**

Used to monitor the availability of homelab services.

**Homepage**

Provides a central dashboard for accessing and viewing homelab services.

---

### 🎬 Media & Photos

**Jellyfin**

Self-hosted media server used inside the home network.

**Immich**

Self-hosted photo management and backup platform.

---

### 🎮 Remote Desktop & Streaming

**Sunshine + Moonlight**

Used for low-latency desktop and game streaming between systems on my local network.

---

### 🏠 Home Automation

**Home Assistant**

Used as the central platform for home automation.

**ESPHome**

Used with ESP32 devices for custom sensors, controls, and electronics projects.

---

## 🐧 Linux

Linux is used throughout the homelab for servers, containers, virtual machines, and experimentation.

I use the lab to improve my knowledge of:

- Linux administration
- Services
- Permissions
- Networking
- Storage
- Troubleshooting
- Virtual machines
- Containers

---

## 📚 Documentation

As this repository grows, detailed documentation will be separated into dedicated sections:

| Documentation | Description |
|---|---|
| `docs/architecture.md` | Overall homelab architecture and workload inventory |
| `docs/proxmox.md` | Proxmox setup and virtualization |
| `docs/networking.md` | Networking and firewall notes |
| `docs/storage.md` | ZFS and storage configuration |
| `docs/services.md` | Self-hosted services |
| `diagrams/` | Network and infrastructure diagrams |
| `configs/` | Sanitized configuration examples |

---

## 🔐 Security & Privacy

This repository intentionally does **not** contain:

- Passwords
- API keys
- Authentication tokens
- VPN private keys
- Private certificates
- Sensitive configuration files
- Personally identifying network information

Any configuration examples added to this repository will be sanitized before being published.

---

## 🚧 Current Status

This homelab is continuously changing as I experiment with new technologies and improve the infrastructure.

Future documentation will cover more of the individual systems, services, network design, and lessons learned along the way.

---

<div align="center">

### Learning by building, testing, breaking, troubleshooting, and improving.

</div>
