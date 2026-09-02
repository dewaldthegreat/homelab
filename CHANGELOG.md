# Changelog

This file tracks notable documentation and homelab-structure changes that are useful to record publicly.

## 2026-09-02

### Added

- LXC `113` (`remote-gateway`) for remote-access and networking gateway experimentation
- LXC `114` (`hermesagent`) for AI-agent automation and tool-orchestration experiments
- LXC `115` (`firecrawl`) for self-hosted web crawling and retrieval
- LXC `116` (`openwebui`) for local AI model and workflow experimentation
- VM `110` (`AD-DC01`) for Active Directory/domain-controller administration practice
- VM `111` (`win11`) as a Windows 11 client for domain, administration, troubleshooting, and Help Desk practice

### Updated

- Main homelab README with the current VM/LXC inventory and expanded technology areas
- Proxmox documentation with the new workloads and Windows lab
- Services documentation with roles for the new AI, remote-access, and Windows workloads
- Architecture documentation with the expanded topology
- Storage documentation to include the `localnetwork` storage target
- Profile README to reflect Windows, Active Directory, remote-access, and AI/automation lab work

## 2026-09-01

### Added

- GLPI Help Desk and IT service management lab in Proxmox LXC `112`
- Simulated Self-Service users and realistic incident/request tickets for Help Desk practice
- Ticket workflow practice covering triage, assignment, troubleshooting, user communication, solutions, closure, and escalation
- GLPI documentation with a DNS troubleshooting and escalation example

### Updated

- Main README with the GLPI workload and Help Desk learning area
- Proxmox inventory with LXC `112`
- Services documentation with the GLPI role and training purpose

## 2026-08-31

### Added

- Initial professional homelab documentation
- Current Proxmox VM and LXC inventory
- Storage overview for `fourTB`, `local`, and `local-lvm`
- Architecture and networking documentation
- Dedicated pages for Home Assistant, media, monitoring, OPNsense, Pi-hole, SMB, Linux testing, and remote desktop/streaming
- Sanitized text and Mermaid diagrams
- Security and configuration-sanitization guidance
- Project roadmap

### Updated

- Main README with navigation, current workloads, storage, status, and security sections
- Service documentation with workload IDs and roles
- Storage documentation with the current logical layout

## Notes

This changelog focuses on meaningful public documentation changes. Small edits and private infrastructure details are not necessarily recorded here.
