---
tags:
  - network
  - hint
---
# lvh.me resolves to localhost

`lvh.me` is a domain whose public DNS record points to `127.0.0.1`. Every subdomain (`*.lvh.me`) resolves to `127.0.0.1` too. This works out of the box on any machine with internet access — no `/etc/hosts` edit required.

## Why it's useful

Some code special-cases and rejects `localhost` or the `127.0.0.1` literal, but happily accepts a real domain name. `lvh.me` lets you point such code at your local machine while still passing a "looks like a real domain" check. Common cases:
- OAuth/OIDC redirect URIs that must be a registered hostname.
- CORS origin allowlists.
- TLS/SNI and certificates that require a hostname.
- Subdomain-based multi-tenant local dev, e.g. `tenant-a.lvh.me`, `tenant-b.lvh.me`.

## Usage

```
http://app.lvh.me:3000
http://tenant-a.lvh.me:8080
```

>[!info]
It depends on a third-party public DNS record, so it breaks offline and if that record ever changes. Offline-resilient alternatives:
- `nip.io` / `sslip.io` — wildcard resolvers that encode the IP in the hostname, e.g. `127.0.0.1.nip.io`, `app.127.0.0.1.nip.io`.
- A local `/etc/hosts` entry when you need full control.
