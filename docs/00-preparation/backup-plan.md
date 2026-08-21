# Backup Plan

## Purpose

Protect important data before changing partitions, installing virtualization tools or running lab workloads.

## Backup Target

Google Drive, approximately 5 TB available.

## Rules

- Keep personal files outside the GitHub repository.
- Store full-machine or personal backups in a private backup location.
- Do not commit backup archives to Git.
- Verify that important files can be restored before making risky system changes.
- Do not format or install Proxmox before the `SAFE TO WIPE` decision.

## Initial Checklist

- [~] Identify important local folders.
- [x] Confirm cloud or external backup location.
- [ ] Confirm available free storage.
- [ ] Test opening a backed-up file.
- [ ] Document only non-sensitive backup decisions here.

## Current Thinking

Do not back up all 945 GB automatically. Games, reinstallable programs, SDKs, IDEs, caches and old software can likely be discarded after review.

Prioritize:

- Documents
- Photos
- Videos
- Projects
- Code
- Relevant school/work files
- Desktop
- Relevant Downloads files
- Local game saves
- Important app-specific settings

## Current Storage Audit Implication

The storage audit suggests a large part of the used space is games and reinstallable data. The first backup pass should focus on the user profile and personal archives, not a full disk copy.

Before deleting or wiping anything:

- Review the user profile folders.
- Check personal archives.
- Confirm whether local game saves are cloud-synced or need backup.
- Verify the uploaded backup from the new laptop.
- Explicitly mark `SAFE TO WIPE`.
