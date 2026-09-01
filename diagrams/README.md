# Homelab Diagrams

This folder contains text-based and Mermaid-style diagrams of the homelab. The diagrams are intentionally sanitized and do not include private IP addresses, subnets, credentials, or externally reachable endpoints.

## Proxmox Workload Layout

```text
pve (Proxmox VE)
|
+-- VMs
|   +-- 100  haos18-2   [Home Assistant OS]
|   +-- 105  opnsense   [Firewall / networking lab]
|   +-- 106  test       [Linux test VM]
|   +-- 107  Omarchy    [Linux desktop VM]
|
+-- LXCs
|   +-- 101  jellyfin   [Media]
|   +-- 102  debianSMB  [File sharing]
|   +-- 103  uptimekuma [Monitoring]
|   +-- 104  homepage   [Dashboard]
|   +-- 108  pihole     [DNS filtering]
|   +-- 109  immich     [Photos]
|   +-- 112  glpi       [ITSM / Help Desk training]
|
+-- Storage
    +-- fourTB
    +-- local
    +-- local-lvm
```

## Functional Architecture

```mermaid
flowchart TD
    NET[Home Network] --> PVE[Proxmox VE Host]

    PVE --> VM[Virtual Machines]
    PVE --> LXC[Linux Containers]
    PVE --> ST[Storage]

    VM --> HA[Home Assistant OS]
    VM --> OP[OPNsense]
    VM --> TEST[Linux Test VM]
    VM --> OM[Omarchy]

    LXC --> JF[Jellyfin]
    LXC --> SMB[debianSMB]
    LXC --> UK[Uptime Kuma]
    LXC --> HP[Homepage]
    LXC --> PH[Pi-hole]
    LXC --> IM[Immich]
    LXC --> GLPI[GLPI Help Desk]

    ST --> FOUR[fourTB]
    ST --> LOCAL[local]
    ST --> LVM[local-lvm]

    HA --> ESP[ESPHome]
```

## Network-Service View

```mermaid
flowchart LR
    CLIENTS[Client Devices] --> NET[Home Network]
    NET --> OP[OPNsense Lab VM]
    NET --> PH[Pi-hole DNS]
    NET --> SMB[SMB File Sharing]
    NET --> JF[Jellyfin]
    NET --> IM[Immich]
    NET --> HA[Home Assistant]
    NET --> GLPI[GLPI Help Desk]
    UK[Uptime Kuma] -. monitors .-> PH
    UK -. monitors .-> JF
    UK -. monitors .-> IM
    UK -. monitors .-> HA
    HP[Homepage] -. links to .-> PH
    HP -. links to .-> JF
    HP -. links to .-> IM
    HP -. links to .-> HA
```

These diagrams represent the logical structure of the lab rather than the exact live network topology.
