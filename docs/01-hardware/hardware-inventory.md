# Hardware Inventory

## Machine

Acer Nitro 5 AN515-54

## Known Hardware

| Component | Value |
| --- | --- |
| CPU | Intel Core i5-9300H |
| Cores / threads | 4 cores / 8 threads |
| RAM | 16 GB DDR4-2666, dual channel |
| RAM slot 1 | 8 GB, A-Data / SK Hynix |
| RAM slot 2 | 8 GB, Crucial / Micron |
| Integrated GPU | Intel UHD Graphics 630 |
| Dedicated GPU | NVIDIA GeForce GTX 1650, 4 GB GDDR5 |
| Motherboard / chipset | Acer CFL Octavia_CFS, Intel HM370 |
| BIOS | Insyde V1.33, 2020-11-17 |
| Ethernet | Realtek Gaming GbE, 1 Gbps |
| Wi-Fi | Intel Wi-Fi 6 AX200 |
| Current OS | Windows 11 Pro |
| Secure Boot | Enabled |
| Firmware virtualization | Enabled in BIOS and Task Manager; CIM/WMI returned inconsistent values |

## Storage

| Disk | Approximate size | Current role |
| --- | ---: | --- |
| WDC PC SN520 | 477 GB | Windows disk |
| Kingston NV2 | 932 GB | Data disk |

Approximate total physical NVMe storage: 1.5 TB.

## Important Correction

The machine was initially assumed to have 32 GB RAM and 1 TB storage. Inventory showed 16 GB RAM and two NVMe SSDs totaling approximately 1.5 TB.

## To Verify

- [x] Exact CPU model
- [x] Core and thread count
- [x] GPU model
- [x] Windows edition
- [x] Available storage devices
- [x] Confirm Intel VT-x setting in BIOS
- [x] Confirm Intel VT-d setting in BIOS
- [ ] Extra SSD expansion option
- [ ] Proxmox hardware compatibility details

## Notes

This file should contain stable, sanitized hardware facts. Command-by-command discovery belongs in `docs/journal/`.
