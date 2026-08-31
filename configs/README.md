# Sanitized Configuration Examples

This folder is reserved for configuration examples that are safe to publish.

Before any configuration is committed here, sensitive values must be removed or replaced with placeholders.

Never publish:

- Passwords
- API keys
- Authentication tokens
- VPN private keys
- Private certificates
- Public IP details that should remain private
- Personally identifying information

Example placeholders should look like:

```text
SERVER_IP=<server-ip>
USERNAME=<username>
API_TOKEN=<redacted>
```

The goal is to document useful configuration patterns without exposing the live homelab.
