# Architecture

## Current Physical Host

| Component | Value |
| --- | --- |
| Machine | Acer Nitro 5 AN515-54 |
| CPU | Intel Core i5-9300H, 4 cores / 8 threads |
| RAM | 16 GB DDR4-2666 |
| Storage 1 | WDC PC SN520, approximately 477 GB |
| Storage 2 | Kingston NV2, approximately 932 GB |
| Ethernet | Realtek Gaming GbE, 1 Gbps |
| Wi-Fi | Intel Wi-Fi 6 AX200 |
| Current OS | Proxmox VE |
| Secure Boot | Enabled |
| Firmware virtualization | Intel VT-x/VT-d enabled in BIOS; Task Manager shows virtualization enabled |

## Current State

The Acer is running Proxmox VE bare metal.

```text
Acer Nitro 5
└── Proxmox VE
    ├── WDC PC SN520 ~477 GB: Proxmox system disk
    └── Kingston NV2 ~932 GB: planned lab storage
```

Backup and new-laptop verification are complete. Proxmox has been installed and the web UI is reachable on the current management VLAN.

Current management endpoint:

```text
https://10.0.2.50:8006
```

## Intended Direction

The current intent is to evaluate Proxmox VE as the bare-metal hypervisor and manage the Nitro remotely from another laptop.

Possible future shape:

```text
Home router
    │
    │ Ethernet
    ▼
Proxmox VE
    │
    ├── Management
    ├── LAB-LAN
    ├── DMZ
    └── ATTACK
```

Potential core VM set:

- OPNsense
- Ubuntu Server
- Kali Linux
- Windows Server
- Windows Client
- Docker host
- Monitoring host
- SIEM host
- Vulnerable targets
- Kubernetes/K3s nodes
- AI/JARVIS host

## Storage Plan

The machine has two NVMe SSDs, which allows separating the Proxmox system disk from most lab storage.

Current layout:

```text
WDC 512 GB
├── Proxmox VE system
└── initial local storage

Kingston 1 TB
└── planned lab storage
```

Detailed storage pools still need to be configured.

## Constraints And Unknowns

- RAM is 16 GB, not the initially assumed 32 GB, so VM concurrency must be planned carefully.
- CIM/WMI virtualization reporting from Windows was inconsistent before wipe, but BIOS and Task Manager showed virtualization enabled.
- GPU passthrough is not guaranteed on this notebook and needs research because of Optimus, IOMMU groups and laptop PCIe topology.
- OPNsense, network segmentation and attack lab isolation must be designed before implementation.

## Safety Principle

Offensive security activity must stay inside owned or explicitly authorized environments.
