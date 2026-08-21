# Backup Execution Log

## Purpose

Track the actual Acer backup execution and verification before any wipe or Proxmox installation.

This file should only contain sanitized facts. Do not include personal filenames, private folder paths, account names, raw file listings, secrets, tokens or license keys.

## Current State

```text
Backup execution: LOCAL COPY COMPLETE
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

- [x] Acer connected to power.
- [x] Network connection stable.
- [x] Google Drive available.
- [x] Backup folder created.
- [x] No wipe, format or Proxmox install started.

### Copy BACKUP Items

- [x] Documents copied.
- [x] Photos copied.
- [x] Videos copied, if applicable.
- [x] Projects/source code copied.
- [x] School/work files copied.
- [x] Selected Desktop files copied.
- [x] Selected Downloads files copied.
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

Current sanitized result:

```text
Initial backup copy: 14,583 items, 16.39 GB
Filtered Downloads copy: 4,485 items, 100.71 GB
Approximate local backup total: 117.10 GB
Google Drive upload: pending
Verified from new laptop: no
Verified categories: pending
Known exclusions: full game libraries, reinstallable applications, Windows system folders, Program Files, caches, temporary files, audio/video/app installers from Downloads filter
Remaining concerns: upload to Google Drive and verification from the new laptop still required
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
