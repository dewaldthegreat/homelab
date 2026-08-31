# Security Policy

This is a public documentation repository for a personal homelab. It is intentionally designed to describe the environment without exposing information that would make the live infrastructure less secure.

## Information That Must Not Be Published

Do not commit:

- Passwords
- API keys
- Authentication or session tokens
- Home Assistant access tokens
- ESPHome encryption keys
- VPN private keys or credentials
- SSH private keys
- Private certificate keys
- Wi-Fi passwords
- Recovery codes
- Secret `.env` files
- Sensitive firewall rules
- Private external endpoints
- Personal files or backups
- Unnecessary internal addressing

## Configuration Examples

All configuration examples must use placeholders for sensitive values.

Example:

```text
HOST=<server-ip>
USERNAME=<username>
PASSWORD=<redacted>
TOKEN=<redacted>
```

See [`configs/README.md`](configs/README.md) for the full sanitization checklist.

## If a Secret Is Accidentally Committed

Treat the secret as exposed even if the commit is quickly removed.

Recommended response:

1. Revoke or rotate the affected credential/key/token.
2. Remove the sensitive value from the current repository state.
3. Check commit history for the exposed value.
4. Replace the secret anywhere it was reused.
5. Review related logs or services if appropriate.

Deleting a secret from the latest file alone does not make the old value safe again.

## Public Network Information

Documentation should prefer logical diagrams and placeholders over exact live addressing. Details should only be included when they add real educational value and do not unnecessarily expose the environment.

## Scope

This file describes how this repository is kept safe for public sharing. It is not a complete security policy for the physical home network or every service running in the homelab.
