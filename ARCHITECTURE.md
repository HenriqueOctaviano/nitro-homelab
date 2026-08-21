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
| Current OS | Windows 11 Pro |
| Secure Boot | Enabled |
| Firmware virtualization | Currently detected as disabled |

## Current State

The Acer is still running Windows 11 Pro. No destructive changes have been made.

```text
Acer Nitro 5
└── Windows 11 Pro
    ├── C: WDC NVMe, current Windows installation
    └── D: Kingston NVMe, existing data
```

Backup and new-laptop verification are complete. The current priority is firmware preparation before Proxmox installation.

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

## Storage Considerations

The machine has two NVMe SSDs, which may allow separation between system, templates, virtual machines, databases, AI models and lab storage.

One possible future layout:

```text
WDC 512 GB
├── Proxmox
├── ISOs
├── templates
└── selected VMs

Kingston 1 TB
├── VMs
├── containers
├── databases
├── AI models
└── lab storage
```

This is not a final decision.

## Constraints And Unknowns

- RAM is 16 GB, not the initially assumed 32 GB, so VM concurrency must be planned carefully.
- Firmware virtualization is currently detected as disabled and must be enabled before a serious virtualization build.
- GPU passthrough is not guaranteed on this notebook and needs research because of Optimus, IOMMU groups and laptop PCIe topology.
- Secure Boot behavior must be reviewed before installing Proxmox.
- OPNsense, network segmentation and attack lab isolation must be designed before implementation.

## Safety Principle

Offensive security activity must stay inside owned or explicitly authorized environments.
