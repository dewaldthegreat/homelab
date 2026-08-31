# Networking

Networking is one of the main areas I use my homelab to learn and experiment with. The environment is built around a **Proxmox VE** host with virtual machines and Linux containers connected through virtual networking to my home network.

## Network Components

| Component | Type | Role |
|---|---|---|
| **OPNsense** | VM 105 | Routing, firewalling, and network configuration lab |
| **Pi-hole** | LXC 108 | Network-wide DNS filtering |
| **debianSMB** | LXC 102 | SMB file sharing across the local network |
| **Uptime Kuma** | LXC 103 | Service and availability monitoring |
| **Proxmox VE** | Host | Virtual networking for VMs and containers |

## High-Level Traffic Flow

```text
Internet
   |
Home Router / Network
   |
   +---------------------------+
   |                           |
Client Devices             Proxmox VE
                               |
                    +----------+----------+
                    |          |          |
                 OPNsense   Pi-hole    Other VMs/LXCs
                  VM 105    LXC 108
                    |          |
               Firewall /    DNS
                Routing    Filtering
                  Lab
```

This is a simplified public view of the network. Exact addressing and sensitive configuration are intentionally omitted.

## OPNsense

**OPNsense runs as VM 105** on the Proxmox host.

I use it as a hands-on environment for learning and experimenting with:

- Firewall rules
- Routing
- Network interfaces
- Gateways
- NAT concepts
- Subnets
- Traffic isolation
- Troubleshooting connectivity between networks

Running OPNsense virtually lets me practice network changes without needing dedicated firewall hardware for every experiment.

## Pi-hole

**Pi-hole runs as LXC 108**.

It provides DNS-based filtering and gives me practical experience with:

- DNS resolution
- Network-wide domain blocking
- Client DNS configuration
- Query troubleshooting
- Understanding how devices discover and use DNS services

## Proxmox Virtual Networking

The Proxmox host provides the virtual networking layer used by the VMs and containers in the lab.

This gives me hands-on experience with:

- Linux bridges
- Virtual network interfaces
- VM and LXC connectivity
- Connecting virtual workloads to the physical LAN
- Diagnosing connectivity between guests, the host, and other network devices

## File Sharing

**debianSMB runs as LXC 102** and provides SMB-based file sharing on the local network.

This has given me experience with:

- Network shares
- Linux file permissions
- SMB client/server connectivity
- Windows-to-Linux file sharing
- Troubleshooting authentication and connectivity issues

## Monitoring

**Uptime Kuma runs as LXC 103** and is used to monitor services in the homelab.

Monitoring helps me identify when a service becomes unreachable and gives me a better understanding of service availability and basic infrastructure monitoring.

## Remote Desktop & Streaming

I also use **Sunshine and Moonlight** for low-latency desktop and game streaming over the local network.

This is useful for learning how network latency, bandwidth, display configuration, and hardware acceleration affect real-time traffic.

## Skills I Practice

Through the networking side of the homelab, I get hands-on experience with:

- IPv4 addressing
- Subnetting
- DNS
- Routing
- NAT
- Firewall rules
- Network troubleshooting
- Virtual networking
- Service connectivity
- SMB networking
- Monitoring
- Client/server communication

## Security & Privacy

This public repository does **not** document:

- Internal IP addresses
- Public IP addresses
- Firewall rule specifics that could expose the network
- VPN keys or credentials
- Passwords or authentication tokens
- Port-forwarding details for externally reachable services
- Private certificates

Public documentation focuses on the technologies, architecture, and lessons learned rather than information that could unnecessarily expose the home network.
