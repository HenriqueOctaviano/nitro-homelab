# Remote Access Plan

## Purpose

Plan secure remote access to the homelab after Proxmox is installed and reachable locally.

Do not expose the Proxmox web interface directly to the public internet.

## Initial Recommendation

Use Tailscale Free for the first remote-access setup.

Reason:

- Free for personal use.
- Does not require opening router ports.
- Reduces the risk of exposing Proxmox directly.
- Easy to install on laptops, desktops and phones.
- Good enough for the first homelab remote-access milestone.

Expected access path:

```text
Remote laptop
    ↓
Tailscale
    ↓
Home network / Proxmox node
    ↓
https://192.168.100.50:8006
```

## Later Learning Path

After the base homelab network is stable, evaluate WireGuard through OPNsense.

Reason:

- Free and open source.
- Strong learning value.
- Better fit once OPNsense, routing and firewall rules are part of the lab.

Possible future path:

```text
Remote device
    ↓
WireGuard
    ↓
OPNsense
    ↓
LAB / Management networks
    ↓
Proxmox and internal services
```

## Safety Rules

- Do not port-forward Proxmox directly from the router.
- Do not expose `:8006` publicly.
- Use VPN-style access first.
- Require strong account passwords.
- Add MFA wherever the remote-access provider supports it.
- Document firewall changes before applying them.

## Current Status

```text
Remote access: planned
Tailscale: recommended initial option
WireGuard/OPNsense: future learning path
Public Proxmox exposure: rejected
```
