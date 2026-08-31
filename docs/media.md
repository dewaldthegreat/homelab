# Media & Photos

The homelab currently runs two self-hosted services for media and photo management.

## Jellyfin — LXC 101

**Jellyfin** runs in LXC **101 (`jellyfin`)** and provides self-hosted media access on the home network.

Operating Jellyfin gives me experience with:

- Running a persistent Linux service
- Storage access
- Client/server connectivity
- Media-library organization
- Troubleshooting service availability

## Immich — LXC 109

**Immich** runs in LXC **109 (`immich`)** and provides self-hosted photo management and backup.

It gives me experience with:

- Self-hosted application management
- Storage planning
- Service dependencies
- Backup considerations
- Client connectivity

## Storage

Media and photo workloads are closely connected to the storage side of the homelab. Public documentation intentionally avoids exposing personal media paths, photo-library details, credentials, and other private data.

See [storage.md](storage.md) for the high-level storage layout.
