# Next Session - Proxmox USB Preparation

## Current State

The homelab is ready to move from preparation into Proxmox installer preparation.

Current status:

```text
Backup: complete
Google Drive upload: complete
New laptop verification: complete
Wipe gate: SAFE TO WIPE
BIOS Intel VT-x: enabled
BIOS Intel VT-d: enabled
Secure Boot: enabled
Current repo branch: main
Next phase: Phase 02 - Proxmox
```

No Proxmox ISO has been downloaded yet in this step.

No USB installer has been created yet.

No disk wipe has been started.

## Next Goal

Prepare a bootable Proxmox VE USB installer, then boot the Acer from USB.

Do not start installation until the target disk is visually confirmed and the destructive-action confirmation is given.

## Step 1 - Download Proxmox VE ISO

Use the official Proxmox downloads page:

```text
https://proxmox.com/en/downloads/proxmox-virtual-environment
```

Target ISO:

```text
Proxmox VE 9.2 ISO Installer
Version: 9.2-1
```

Expected SHA256:

```text
4e88fe416df9b527624a175f24c9aa07c714d3332afb1ee3dbf3879573ef2c6c
```

## Step 2 - Verify ISO Checksum

After download, run PowerShell:

```powershell
Get-FileHash "$env:USERPROFILE\Downloads\proxmox-ve_9.2-1.iso" -Algorithm SHA256
```

If the filename is different, adjust the path.

The result must match:

```text
4e88fe416df9b527624a175f24c9aa07c714d3332afb1ee3dbf3879573ef2c6c
```

If it does not match, do not use the ISO.

## Step 3 - Create USB Installer

Use Rufus or balenaEtcher.

Important:

- The USB drive will be erased.
- Confirm the selected USB drive before writing.
- Do not select any internal Acer SSD.

## Step 4 - Boot Acer From USB

On the Acer Nitro 5:

```text
F2 = BIOS/UEFI setup
F12 = Boot menu, if enabled
```

If F12 boot menu is disabled, enable it in BIOS first.

Boot from the Proxmox USB installer.

## Step 5 - Stop Before Destructive Install

Before the Proxmox installer writes to disk, stop and confirm:

```text
I understand the selected disk will be wiped and I approve continuing.
```

Target disk plan:

```text
WDC PC SN520 ~477 GB: Proxmox VE system, ISOs, templates, small/critical VMs
Kingston NV2 ~932 GB: VM disks, containers, databases, AI models, lab storage
```

The selected installer target disk must be confirmed visually.

## What To Record Next

When continuing, record sanitized facts only:

```text
ISO downloaded: yes/no
SHA256 verified: yes/no
USB installer created: yes/no
Booted from USB: yes/no
Target disk confirmed: yes/no
Install started: yes/no
```

Do not record personal filenames, private paths, account names or raw device serial numbers unless needed.

## Current Stop Point

Stop point for this session:

```text
Ready to download Proxmox ISO.
No ISO downloaded yet.
No USB installer created yet.
No disk wipe started.
```
