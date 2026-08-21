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

The Acer storage audit generated:

```text
nitro-homelab-storage-audit/
├── c-drive-folders.csv
├── d-drive-folders.csv
└── files-over-1gb.csv
```

The raw CSV files can contain personal paths and should not be committed directly.

## Sanitized Findings

Top-level folder sizes:

| Location | Approximate size | Initial classification |
| --- | ---: | --- |
| C: user profile area | 237.19 GB | REVIEW / BACKUP |
| C: Windows | 64.97 GB | DISCARD / reinstall |
| C: Program Files | 50.80 GB | DISCARD / reinstall |
| C: Program Files (x86) | 25.81 GB | DISCARD / reinstall |
| C: ProgramData | 16.80 GB | REVIEW |
| D: Steam library | 323.61 GB | DISCARD / reinstall |
| D: World of Warcraft | 89.42 GB | DISCARD / reinstall |
| D: Diablo IV | 86.46 GB | DISCARD / reinstall |
| D: Riot Games | 33.20 GB | DISCARD / reinstall |

Large files summary:

| Category | Count | Approximate size | Initial classification |
| --- | ---: | ---: | --- |
| Games and game data | 42 | 181.19 GB | DISCARD / reinstall |
| Needs review | 6 | 93.94 GB | REVIEW |
| System files | 2 | 12.59 GB | DISCARD |
| ISO files | 2 | 8.60 GB | REVIEW / DISCARD |
| Personal archive needing review | 1 | 6.25 GB | REVIEW / BACKUP |

Files larger than 1 GB:

```text
Count: 53
Total: 302.57 GB
C: total: 160.36 GB
D: total: 142.21 GB
```

## Initial Classification

Use this classification before backup:

```text
BACKUP
REVIEW
DISCARD
```

Initial direction:

- `BACKUP`: documents, photos, videos, code, projects, school/work files, local saves and hard-to-recreate configuration.
- `REVIEW`: user profile, personal archives, old ISO files, app data with unknown value.
- `DISCARD`: games, reinstallable programs, caches, Windows system files, hibernation/page files and old installers that can be downloaded again.

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
