# Backup Classification

## Purpose

Classify current Acer data before wiping or installing Proxmox.

The goal is not to preserve the full 945 GB currently used. The goal is to preserve data that is personal, useful, hard to recreate or needed for future work.

## Classification Labels

| Label | Meaning |
| --- | --- |
| `BACKUP` | Copy before wipe. Losing this would matter. |
| `REVIEW` | Inspect manually before deciding. May contain valuable data or junk. |
| `DISCARD` | Do not back up unless a specific exception is found. Reinstall or recreate later. |

## BACKUP

Copy these before wiping:

| Category | Reason |
| --- | --- |
| Personal documents | Hard to recreate and likely important. |
| Photos and videos | Personal data, usually irreplaceable. |
| Projects and source code | May contain learning/work history. |
| School/work files | May still be useful. |
| Desktop files selected after review | Desktops often contain unsorted important files. |
| Relevant Downloads selected after review | Downloads can contain installers, documents or exports. |
| Local game saves not cloud-synced | Saves may not be recoverable after reinstall. |
| App-specific configuration that is hard to recreate | Useful if a setup took time to tune. |

## REVIEW

Inspect these manually:

| Category | Why review |
| --- | --- |
| User profile area | Large and likely mixed: personal data, caches, downloads and app data. |
| Personal archive files | May contain important material, but contents are unknown. |
| ProgramData | Can contain app state, but much of it is reinstallable. |
| Old ISO files | May be unnecessary, but check if any are rare or custom. |
| Old project folders | Keep only projects with learning, portfolio or practical value. |
| Game save folders | Confirm whether cloud sync covers them. |

## DISCARD

Do not back up by default:

| Category | Reason |
| --- | --- |
| Steam library | Reinstallable. Very large. |
| Standalone game folders | Reinstallable unless they contain local-only saves. |
| Riot/Blizzard game installs | Reinstallable. |
| Windows system folders | Recreated by install. |
| Program Files | Reinstall apps later as needed. |
| Program Files (x86) | Reinstall apps later as needed. |
| Hibernation and page files | System-generated. |
| Reinstallable SDKs, IDEs and caches | Recreate after the new lab plan is clear. |
| Recycle bin contents | Discard unless a specific recovery need is identified. |

## Manual Review Checklist

Before copying to Google Drive, review:

- [ ] Documents
- [ ] Pictures
- [ ] Videos
- [ ] Desktop
- [ ] Downloads
- [ ] Source code and project folders
- [ ] School/work folders
- [ ] Browser exports if needed
- [ ] Local game saves
- [ ] Passwords/secrets migration status
- [ ] Any app configuration that would be painful to recreate

## Backup Verification Checklist

After upload, verify from the new laptop:

- [ ] Backup folder is visible in Google Drive.
- [ ] Folder structure is understandable.
- [ ] A sample document opens.
- [ ] A sample image or video opens.
- [ ] A sample archive extracts or lists correctly.
- [ ] A sample project folder contains expected files.
- [ ] Any selected game save/configuration files are present.
- [ ] Nothing obviously sensitive was committed to GitHub.

## SAFE TO WIPE Gate

The Acer is not safe to wipe until all are true:

- [ ] `BACKUP` items were copied.
- [ ] `REVIEW` items were inspected.
- [ ] Selected `REVIEW` items were copied or explicitly discarded.
- [ ] Backup was verified from the new laptop.
- [ ] The final wipe decision was documented.
