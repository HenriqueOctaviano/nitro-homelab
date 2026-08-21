# Phase 02 - Proxmox

## Purpose

Plan and execute the Proxmox VE bare-metal installation on the Acer Nitro 5.

This phase is destructive once the installer writes to disk. Do not start installation until the target disk and wipe decision are confirmed.

## Current Readiness

| Item | State |
| --- | --- |
| Backup | Complete |
| Google Drive verification | Complete |
| Wipe gate | `SAFE TO WIPE` |
| Intel VT-x | Enabled in BIOS |
| Intel VT-d | Enabled in BIOS |
| Secure Boot | Enabled |
| Target hypervisor | Proxmox VE bare metal |

## Official Requirements Notes

Proxmox VE requires a 64-bit CPU and an Intel VT/AMD-V capable CPU/mainboard for KVM full virtualization support. For evaluation, the minimum is 1 GB RAM plus RAM for guests, a hard drive and one network card. Recommended hardware includes at least 2 GB RAM for Proxmox services plus guest memory, SSD storage and Intel VT/AMD-V.

For PCIe passthrough, Intel VT-d/AMD-d is required.

Source:

- [Proxmox VE requirements](https://www.proxmox.com/en/products/proxmox-virtual-environment/requirements)

## Installer Warning

The Proxmox VE installer is destructive for selected disks.

The official Proxmox installation documentation states that existing data on selected drives will be removed during installation, and the Proxmox get-started page notes that the bare-metal installer uses the complete server and removes existing data on selected disks.

Sources:

- [Proxmox VE installation documentation](https://github.com/proxmox/pve-docs/blob/master/pve-installation.adoc)
- [Proxmox VE get started](https://www.proxmox.com/en/products/proxmox-virtual-environment/get-started)

## ISO Plan

Use the current x86 Proxmox VE ISO installer from the official Proxmox downloads page.

Current download page shows:

```text
Proxmox VE 9.2 ISO Installer
Version: 9.2-1
File size: 1.71 GB
SHA256: 4e88fe416df9b527624a175f24c9aa07c714d3332afb1ee3dbf3879573ef2c6c
```

Source:

- [Proxmox VE downloads](https://proxmox.com/en/downloads/proxmox-virtual-environment)

## Secure Boot Note

Proxmox VE 8.1 and newer support Secure Boot out of the box when using the supported signed boot chain. Secure Boot still needs attention during installer boot and hardware setup.

Source:

- [Proxmox VE Secure Boot documentation](https://github.com/proxmox/pve-docs/blob/master/system-booting.adoc)

## Proposed Disk Layout

Initial intended layout:

```text
WDC PC SN520 ~477 GB
├── Proxmox VE system
├── ISO images
├── templates
└── small/critical VMs

Kingston NV2 ~932 GB
├── VM disks
├── containers
├── databases
├── AI models
└── lab storage
```

Important:

The final disk selected in the installer must be confirmed visually before continuing.

## Pre-Install Checklist

- [ ] Download Proxmox VE ISO from official site.
- [ ] Verify ISO checksum.
- [ ] Create bootable USB installer.
- [ ] Boot Acer from USB.
- [ ] Confirm installer sees both NVMe SSDs.
- [ ] Confirm target disk before any install action.
- [ ] Confirm final destructive action with user.
- [ ] Install Proxmox VE.
- [ ] Boot into Proxmox.
- [ ] Access Proxmox web UI from new laptop.

## Destructive Boundary

Before the installer writes to disk, stop and confirm:

```text
I understand the selected disk will be wiped and I approve continuing.
```

No destructive installation step should happen before that explicit confirmation.
