# Nitro Homelab

Documented bare-metal homelab for learning infrastructure, networking, cybersecurity, DevOps, development, automation and local AI.

## Overview

This repository tracks the build of a dedicated homelab on an Acer Nitro 5. The goal is to make the lab reproducible from GitHub while keeping a clear record of commands, results, decisions, mistakes and fixes.

The current direction is to prepare the machine, back up important data, verify it is safe to wipe, and then evaluate a Proxmox VE bare-metal installation.

## Goals

The lab will cover:

- Infrastructure and virtualization
- Linux and Windows Server
- Active Directory
- Networking
- Proxmox and OPNsense
- Docker and Kubernetes/K3s
- DevOps and automation
- Ansible and Terraform/OpenTofu
- CI/CD
- Monitoring and observability
- Offensive and defensive security
- APIs, databases and FastAPI
- Local AI and JARVIS-style automation

## Hardware

Current known hardware:

| Component | Value |
| --- | --- |
| Model | Acer Nitro 5 AN515-54 |
| CPU | Intel Core i5-9300H, 4 cores / 8 threads |
| RAM | 16 GB DDR4-2666, dual channel |
| Integrated GPU | Intel UHD Graphics 630 |
| Dedicated GPU | NVIDIA GeForce GTX 1650 4 GB GDDR5 |
| Storage | WDC PC SN520 ~477 GB + Kingston NV2 ~932 GB |
| Ethernet | Realtek Gaming GbE, 1 Gbps |
| Wi-Fi | Intel Wi-Fi 6 AX200 |
| Current OS | Windows 11 Pro |

Virtualization is currently detected as disabled in firmware. BIOS settings have not been changed yet.

## Current Architecture

Current state:

```text
Acer Nitro 5
└── Windows 11 Pro
    ├── C: WDC NVMe, current Windows installation
    └── D: Kingston NVMe, existing data
```

Possible future direction:

```text
Router
  │
  ▼
Proxmox VE
  │
  ├── Management
  ├── LAB-LAN
  ├── DMZ
  └── ATTACK
```

This architecture is still being designed. No destructive changes have been made.

## Planned Stack

Potential technologies include Proxmox VE, OPNsense, Ubuntu Server, Kali Linux, Windows Server, Windows Client, Docker, K3s, Prometheus, Grafana, Loki, SIEM tooling, Ansible, Terraform/OpenTofu, FastAPI, Ollama and local AI automation.

These are planned learning targets, not final design decisions.

## Current Status

Phase 00 - Preparation

```text
[x] Hardware baseline
[~] Storage audit
[ ] Backup plan
[ ] Upload to Google Drive
[ ] Backup verification
[ ] Review from new laptop
[ ] Safe to wipe
```

## Documentation

- `docs/journal/`: command-by-command lab diary, including results, errors, decisions and fixes.
- `docs/00-preparation/`: backup, storage, safety and setup preparation.
- `docs/01-hardware/`: hardware inventory and capability checks.
- `ROADMAP.md`: phases, dependencies and progress.
- `ARCHITECTURE.md`: current and planned architecture notes.

## Roadmap

See `ROADMAP.md`.

## Safety Scope

Security testing is limited to:

- Systems owned in this homelab
- Deliberately vulnerable lab targets
- Environments where explicit authorization exists

Sensitive information must be sanitized before anything is committed.

## Repository Structure

```text
nitro-homelab/
├── README.md
├── ROADMAP.md
├── ARCHITECTURE.md
├── docs/
│   ├── journal/
│   ├── 00-preparation/
│   └── 01-hardware/
└── diagrams/
```
