# SMB File Sharing

SMB file sharing is provided by LXC **102 (`debianSMB`)**, a Debian-based container dedicated to network file access.

## Purpose

The container gives devices on the local network access to shared storage while keeping the file-sharing service separate from unrelated applications.

## What I Learn From It

- Debian/Linux administration
- SMB configuration
- Linux file ownership and permissions
- Mount points and storage access
- Network-share troubleshooting
- Client connectivity
- Separating storage from application workloads

## Storage

The SMB service connects the networking side of the homelab with its storage environment. The public repository documents the logical design but does not expose live share paths, personal file names, credentials, or private access-control details.

See [storage.md](storage.md) for the high-level storage overview.
