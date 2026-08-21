# Storage Audit

## Purpose

Track available storage and decide how much space can be safely assigned to virtual machines, containers, datasets and AI models.

## Current Storage Baseline

| Volume | Approximate total | Approximate free | Notes |
| --- | ---: | ---: | --- |
| C: | 475.54 GB | 64.16 GB | Current Windows installation |
| D: | 931.50 GB | 398.17 GB | Existing data |

Approximate total used across both volumes: 945 GB.

## Current Audit

The Acer is currently running a storage audit that will generate:

```text
nitro-homelab-storage-audit/
├── c-drive-folders.csv
├── d-drive-folders.csv
└── files-over-1gb.csv
```

After the audit completes, results will be classified as:

```text
BACKUP
REVIEW
DISCARD
```

## Backup Priority

Backup priority is for data that is hard or impossible to recreate:

- Personal documents
- Photos and videos
- Projects and source code
- Relevant school/work files
- Desktop files
- Relevant Downloads files
- Local game saves
- Important app-specific configuration

## Notes

- VM disks, snapshots, Docker images and local AI models can grow quickly.
- Do not enable large automated downloads without checking free space first.
- Do not delete files until backup classification and verification are complete.
