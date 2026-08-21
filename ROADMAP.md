# Roadmap

This roadmap tracks the intended learning path. The order can change as the lab exposes constraints or better sequencing.

## Phase 00 - Preparation

Goal: understand the current machine, protect important data and only wipe the Acer after verification.

Progress:

```text
[x] 00.1 Hardware baseline
[x] 00.2 Storage audit
[x] 00.3 Backup plan
[x] 00.4 Upload to Google Drive
[x] 00.5 Backup verification
[x] 00.6 Review from new laptop
[x] 00.7 Safe to wipe
```

Dependencies:

- Proxmox installation can proceed after final destructive-action confirmation.
- Destructive disk changes require an explicit final confirmation before execution.

## Phase 01 - BIOS / Firmware

Goal: inspect and configure firmware settings required for virtualization.

Progress:

```text
[x] 01.1 BIOS entry plan
[x] 01.2 Enable Intel VT-x
[x] 01.3 Review Secure Boot
[~] 01.4 Confirm virtualization from Windows
[ ] 01.5 Document final firmware state
```

Potential work:

- Enable Intel VT-x if disabled.
- Review Secure Boot implications.
- Document BIOS version and settings.

Dependencies:

- Backup is complete and the Acer is marked `SAFE TO WIPE`.
- Do not install Proxmox until firmware settings are documented.
- Any destructive installation step still requires final confirmation.

## Phase 02 - Proxmox

Goal: evaluate and install Proxmox VE bare metal after preparation is complete.

Progress:

```text
[~] 02.1 Installation plan
[ ] 02.2 ISO download and verification
[ ] 02.3 USB installer creation
[ ] 02.4 Disk layout confirmation
[ ] 02.5 Final destructive-action confirmation
[ ] 02.6 Install Proxmox VE
[ ] 02.7 First boot and web UI access
```

Potential work:

- Choose disk layout.
- Install Proxmox.
- Configure management access.
- Verify remote administration from the new laptop.

Dependencies:

- Backup is complete and the Acer is marked `SAFE TO WIPE`.
- Intel VT-x/VT-d are enabled in BIOS.
- Target disk selection must be confirmed before installation.

## Phase 03 - Networking

Goal: design isolated virtual networks for management, lab services, DMZ and offensive testing.

Potential work:

- Management network.
- LAB-LAN.
- DMZ.
- ATTACK network.
- Routing and firewall boundaries.

## Phase 04 - Firewall / OPNsense

Goal: evaluate OPNsense as the lab firewall.

Potential work:

- Deploy OPNsense VM.
- Configure interfaces.
- Add basic firewall rules.
- Validate isolation.

## Later Phases

Planned learning areas:

| Phase | Area |
| --- | --- |
| 05 | Linux infrastructure |
| 06 | Windows Server / Active Directory |
| 07 | Docker |
| 08 | Cyber range |
| 09 | Observability |
| 10 | Development / APIs |
| 11 | CI/CD |
| 12 | Ansible |
| 13 | Terraform / OpenTofu |
| 14 | Kubernetes / K3s |
| 15 | SIEM / SOC lab |
| 16 | JARVIS / Local AI |

These technologies are learning targets and will become concrete only when introduced, tested and documented.
