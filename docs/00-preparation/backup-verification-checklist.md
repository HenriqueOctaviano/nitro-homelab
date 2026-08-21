# Backup Verification Checklist

## Purpose

Provide the operational checklist for backing up the Acer before any wipe or Proxmox installation.

This file documents what must be done and verified. It must not contain personal filenames, private paths, secrets or raw backup listings.

## Backup Folder

Create a dedicated Google Drive folder for the Acer backup.

Suggested non-sensitive folder name:

```text
nitro-homelab-acer-backup-2026-08
```

## Step 1 - Prepare

- [ ] Confirm the Acer is connected to power.
- [ ] Confirm network connectivity is stable.
- [ ] Confirm Google Drive has enough free space.
- [ ] Confirm no wipe, format or Proxmox install will be started during backup.
- [ ] Keep the raw storage audit local/private.

## Step 2 - Copy BACKUP Items

Copy the high-priority data first:

- [ ] Documents
- [ ] Photos
- [ ] Videos
- [ ] Projects and source code
- [ ] School/work files
- [ ] Selected Desktop files
- [ ] Selected Downloads files
- [ ] Local-only game saves
- [ ] Important app-specific configuration

Notes:

- Do not copy full game libraries by default.
- Do not copy Windows system folders.
- Do not copy Program Files by default.
- Do not copy raw secrets into GitHub.

## Step 3 - Review REVIEW Items

Inspect manually before deciding:

- [ ] User profile folders
- [ ] Personal archives
- [ ] ProgramData items with unknown value
- [ ] Old ISO files
- [ ] Old project folders
- [ ] Game save locations
- [ ] App configuration folders

For each reviewed item, decide:

```text
COPY
DISCARD
SKIP FOR NOW
```

Only document sanitized decisions in GitHub.

## Step 4 - Confirm DISCARD Items

Discard by default unless a specific exception is found:

- [ ] Steam library
- [ ] Standalone game install folders
- [ ] Riot/Blizzard game installs
- [ ] Windows system folders
- [ ] Program Files
- [ ] Program Files (x86)
- [ ] Hibernation file
- [ ] Page file
- [ ] Reinstallable SDKs and IDEs
- [ ] Caches and temporary files
- [ ] Recycle bin contents

## Step 5 - Verify From New Laptop

After upload, verify from the new laptop:

- [ ] Google Drive backup folder is visible.
- [ ] Folder organization makes sense.
- [ ] A sample document opens.
- [ ] A sample image opens.
- [ ] A sample video opens if videos were backed up.
- [ ] A sample archive can be listed or extracted.
- [ ] A sample project folder contains expected files.
- [ ] Selected save/configuration files are present.
- [ ] No obvious required category is missing.

## Step 6 - Document Verification

After verification, document only sanitized facts:

```text
Backup location: Google Drive folder name only
Verified from: new laptop
Verified categories: documents, photos, projects, etc.
Known exclusions: games, reinstallable apps, caches, etc.
Remaining concerns: any unresolved review items
```

Do not document:

- Personal filenames
- Private folder paths
- Account names
- Secrets
- Tokens
- License keys
- Raw file lists

Use `backup-execution-log.md` for the actual execution record.

## SAFE TO WIPE Gate

The Acer can only be marked `SAFE TO WIPE` after:

- [ ] BACKUP items copied.
- [ ] REVIEW items inspected.
- [ ] Selected REVIEW items copied.
- [ ] DISCARD items accepted.
- [ ] Backup verified from the new laptop.
- [ ] Remaining concerns documented.
- [ ] Final confirmation written in the journal.

Until then:

```text
NOT SAFE TO WIPE
```
