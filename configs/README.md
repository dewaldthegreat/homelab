# Sanitized Configuration Examples

This folder is reserved for configuration examples that are safe to publish publicly.

The goal is to document useful patterns from the homelab without exposing the live environment.

## Rules Before Committing a Config

Every configuration must be reviewed and sanitized before it is added here.

Replace real values with obvious placeholders, for example:

```text
SERVER_IP=<server-ip>
GATEWAY=<gateway>
USERNAME=<username>
PASSWORD=<redacted>
API_TOKEN=<redacted>
DOMAIN=<example-domain>
```

## Never Publish

- Passwords
- API keys
- Authentication tokens
- Session cookies
- VPN private keys
- SSH private keys
- Private certificates or certificate keys
- Wi-Fi credentials
- Recovery codes
- Real secrets from `.env` files
- Public endpoints that should remain private
- Sensitive internal addressing
- Personally identifying paths or data

## Before Publishing

Use this checklist:

- [ ] Remove usernames where they are not necessary
- [ ] Replace private IPs/subnets with placeholders when they add no educational value
- [ ] Remove all passwords, tokens, keys, and secrets
- [ ] Remove personal domains or endpoints if they should not be public
- [ ] Remove device identifiers if they could expose private information
- [ ] Check comments as well as active configuration lines
- [ ] Review the Git diff before committing

## Example

Unsafe:

```text
api_token=REAL_SECRET_VALUE
server=192.0.2.10
password=my-real-password
```

Safe:

```text
api_token=<redacted>
server=<server-ip>
password=<redacted>
```

The public repository should explain **how** something is configured, not provide credentials or a map to the live environment.
