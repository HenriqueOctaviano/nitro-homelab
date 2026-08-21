# Phase 00 - Preparation

This phase prepares the Acer Nitro 5 before any destructive change.

## Goals

- Document the current hardware.
- Audit storage usage.
- Decide what must be backed up.
- Upload important files to Google Drive.
- Verify the backup from the new laptop.
- Mark the machine as safe to wipe only after verification.

## Current Progress

```text
[x] Hardware baseline
[x] Storage audit
[x] Backup classification
[x] Backup plan finalization
[~] Backup execution
[ ] Upload to Google Drive verification
[ ] Backup verification
[ ] Review from new laptop
[ ] Safe to wipe
```

## Rule

Do not install Proxmox or wipe disks until backup, verification and review are complete.

## Current Documents

- `backup-plan.md`: backup rules, target and workflow.
- `backup-classification.md`: current `BACKUP / REVIEW / DISCARD` classification.
- `backup-execution-log.md`: sanitized execution log for the actual Acer backup.
- `backup-verification-checklist.md`: operational checklist for copy and verification.
- `storage-audit.md`: sanitized storage audit summary.
