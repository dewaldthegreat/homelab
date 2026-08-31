# Monitoring & Dashboard

The homelab uses dedicated services for checking availability and organizing access to other workloads.

## Uptime Kuma — LXC 103

**Uptime Kuma** runs in LXC **103 (`uptimekuma`)**.

I use it to monitor whether important homelab services are reachable and to make service failures easier to notice.

This gives me hands-on experience with:

- Availability monitoring
- Service dependencies
- Connectivity troubleshooting
- Understanding the difference between a running host and a reachable application

## Homepage — LXC 104

**Homepage** runs in LXC **104 (`homepage`)** and acts as a central dashboard for homelab services.

It helps organize access to the environment and makes the collection of self-hosted services easier to navigate.

## Public Documentation

Monitoring endpoints, private URLs, credentials, and internal addressing are intentionally excluded from this public repository.
