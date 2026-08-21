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
| Intel VT-x | Enabled in BIOS |
| Intel VT-d | Enabled in BIOS |
| Windows Task Manager virtualization | Enabled |
| Windows CIM virtualization detection | Inconsistent / returned `False` |
| Backup status | Complete |
| Wipe gate | `SAFE TO WIPE` |

## Goals

- Enable Intel VT-x if it is disabled.
- Review Secure Boot before Proxmox installation.
- Confirm boot order behavior.
- Document BIOS/UEFI settings after changes.
- Return to Windows once to confirm virtualization is enabled before wiping.

## Checklist

- [x] Enter BIOS/UEFI.
- [x] Find Intel Virtualization Technology / VT-x setting.
- [x] Enable virtualization if disabled.
- [x] Confirm Intel VT-d is enabled.
- [x] Review Secure Boot state.
- [ ] Review boot order / USB boot option.
- [ ] Save BIOS changes.
- [ ] Boot back into Windows.
- [x] Confirm virtualization is enabled from Windows Task Manager.
- [~] Investigate CIM/WMI virtualization reporting inconsistency.
- [ ] Document final firmware state.

## Verification Notes

BIOS showed:

```text
Intel VT-x: Enabled
Intel VT-d: Enabled
Secure Boot: Enabled
```

Windows Task Manager showed:

```text
Virtualization: Enabled
```

However, this PowerShell check returned inconsistent values:

```powershell
Get-CimInstance Win32_Processor | Format-List Name,VirtualizationFirmwareEnabled,VMMonitorModeExtensions,SecondLevelAddressTranslationExtensions
```

Observed result:

```text
VirtualizationFirmwareEnabled: False
VMMonitorModeExtensions: False
```

Decision:

Treat Task Manager plus BIOS state as the current practical confirmation, but keep the CIM/WMI inconsistency documented for follow-up if Proxmox or Hyper-V behavior exposes a real issue.

## Safety Notes

- Do not install Proxmox during this phase.
- Do not wipe disks during this phase.
- Do not change disk mode, RAID/AHCI settings or security keys unless explicitly planned.
- If a setting is unclear, document it before changing it.

## Expected Next Phase

After virtualization is enabled and documented, move to Phase 02 - Proxmox planning.
