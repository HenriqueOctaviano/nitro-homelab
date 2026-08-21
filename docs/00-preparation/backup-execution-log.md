# Backup Execution Log

## Purpose

Track the actual Acer backup execution and verification before any wipe or Proxmox installation.

This file should only contain sanitized facts. Do not include personal filenames, private folder paths, account names, raw file listings, secrets, tokens or license keys.

## Current State

```text
Backup execution: NOT STARTED
Google Drive upload: NOT VERIFIED
New laptop verification: NOT VERIFIED
Wipe status: NOT SAFE TO WIPE
```

## Backup Target

```text
Google Drive folder: nitro-homelab-acer-backup-2026-08
```

## Execution Checklist

### Prepare

- [ ] Acer connected to power.
- [ ] Network connection stable.
- [ ] Google Drive available.
- [ ] Backup folder created.
- [ ] No wipe, format or Proxmox install started.

### Copy BACKUP Items

- [ ] Documents copied.
- [ ] Photos copied.
- [ ] Videos copied, if applicable.
- [ ] Projects/source code copied.
- [ ] School/work files copied.
- [ ] Selected Desktop files copied.
- [ ] Selected Downloads files copied.
- [ ] Local-only game saves copied, if needed.
- [ ] Important app-specific configuration copied, if needed.

### Review REVIEW Items

- [ ] User profile reviewed.
- [ ] Personal archives reviewed.
- [ ] ProgramData reviewed where needed.
- [ ] Old ISO files reviewed.
- [ ] Old project folders reviewed.
- [ ] Game save locations reviewed.
- [ ] App configuration folders reviewed.

### Confirm DISCARD Items

- [ ] Full game libraries excluded unless specific saves/configs are needed.
- [ ] Windows system folders excluded.
- [ ] Program Files excluded.
- [ ] Program Files (x86) excluded.
- [ ] Hibernation/page files excluded.
- [ ] Reinstallable SDKs, IDEs and caches excluded.
- [ ] Recycle bin excluded unless a specific item is needed.

### Verify From New Laptop

- [ ] Google Drive backup folder visible from new laptop.
- [ ] Folder organization verified.
- [ ] Sample document opens.
- [ ] Sample image opens.
- [ ] Sample video opens, if applicable.
- [ ] Sample archive lists or extracts correctly, if applicable.
- [ ] Sample project folder contains expected files.
- [ ] Selected saves/configs are present, if applicable.
- [ ] No obvious required category is missing.

## Sanitized Results

Fill this after execution:

```text
Backup started:
Backup completed:
Verified from new laptop:
Verified categories:
Known exclusions:
Remaining concerns:
Final status: NOT SAFE TO WIPE
```

## SAFE TO WIPE Decision

Current decision:

```text
NOT SAFE TO WIPE
```

Only change this after:

- Backup is complete.
- Upload is visible in Google Drive.
- Verification was performed from the new laptop.
- Remaining concerns are resolved or accepted.
- Final confirmation is recorded in the journal.
