# Pi-hole

**Pi-hole** runs in LXC **108 (`pihole`)** and provides DNS-based filtering for devices on the network.

## What I Use It For

Pi-hole gives me hands-on experience with:

- DNS resolution
- DNS filtering
- Blocklists
- Client DNS configuration
- Service availability
- Network troubleshooting

## Role in the Homelab

Pi-hole is one of the core network services in the lab. Because DNS affects many other services, it is also useful for learning how a failure in one infrastructure component can affect multiple clients and applications.

## Monitoring

Uptime Kuma can be used to help identify when important network services such as DNS are unavailable.

## Privacy

The public repository does not publish private client lists, query history, internal addresses, custom private DNS records, credentials, or sensitive block/allow rules.
