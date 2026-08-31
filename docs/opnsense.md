# OPNsense

**OPNsense** runs as Proxmox VM **105 (`opnsense`)** and is used as a networking and firewall lab environment.

## What I Use It For

The VM gives me a practical environment for learning concepts such as:

- Interfaces
- Routing
- Firewall rules
- Gateways
- NAT concepts
- Network segmentation concepts
- Connectivity troubleshooting
- Virtual networking inside Proxmox

## Why a VM

Running OPNsense as a VM lets me experiment with a complete firewall/router operating system while keeping it manageable through Proxmox.

It also helps me understand how virtual NICs, bridges, and routed networks interact with workloads running on the same virtualization host.

## Security

This repository does not publish the live firewall rule set, private IP addressing, external addresses, VPN credentials, private keys, or other security-sensitive configuration.

See [networking.md](networking.md) for the wider networking overview.
