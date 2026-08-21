# Phase 01 - BIOS / Firmware

## Purpose

Prepare the Acer Nitro 5 firmware settings for virtualization and a future Proxmox installation.

This phase is not the wipe itself. It only covers entering BIOS/UEFI, checking required settings and documenting the final firmware state.

## Known Starting State

| Item | State |
| --- | --- |
| Machine | Acer Nitro 5 AN515-54 |
| BIOS | Insyde V1.33, 2020-11-17 |
| Secure Boot | Enabled |
| Windows virtualization detection | `VirtualizationFirmwareEnabled: False` |
| Backup status | Complete |
| Wipe gate | `SAFE TO WIPE` |

## Goals

- Enable Intel VT-x if it is disabled.
- Review Secure Boot before Proxmox installation.
- Confirm boot order behavior.
- Document BIOS/UEFI settings after changes.
- Return to Windows once to confirm virtualization is enabled before wiping.

## Checklist

- [ ] Enter BIOS/UEFI.
- [ ] Find Intel Virtualization Technology / VT-x setting.
- [ ] Enable virtualization if disabled.
- [ ] Review Secure Boot state.
- [ ] Review boot order / USB boot option.
- [ ] Save BIOS changes.
- [ ] Boot back into Windows.
- [ ] Confirm virtualization is enabled from Windows.
- [ ] Document final firmware state.

## Safety Notes

- Do not install Proxmox during this phase.
- Do not wipe disks during this phase.
- Do not change disk mode, RAID/AHCI settings or security keys unless explicitly planned.
- If a setting is unclear, document it before changing it.

## Expected Next Phase

After virtualization is enabled and documented, move to Phase 02 - Proxmox planning.
