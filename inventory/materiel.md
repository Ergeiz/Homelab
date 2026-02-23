# 📦 Inventaire matériel – Infrastructure Homelab

---

## 🔌 Commutateur administrable  
### Cisco Catalyst 1300-8T-E-2G

- Type : Switch manageable
- Ports :
  - 8x 10/100/1000 Mbps RJ45
  - 2x Gigabit Copper/SFP Combo
- Rôle : Segmentation VLAN & backbone interne
- Firmware : À compléter

---

## 🖥️ Hyperviseur principal  
### Minisforum MS-01

- CPU : Intel Core i9-13900H
- GPU : NVIDIA GeForce RTX 3050 6 Go
- RAM : 128 Go
- Stockage :
  - 2x NVMe 4 To (ZFS RAID1 – VM critiques)
  - 1x NVMe 4 To (ext4 – ISO & VM de test)
- IP WAN: 192.168.1.10/24
- IP LAN: 10.0.0.1/16
- Rôle : Hyperviseur principal (Proxmox VE)
- Firmware : À compléter

---

## 🖥️ Hyperviseur Backup  
### Starlabs Byte

- CPU : Intel Core 3 N355 (8 cores)
- RAM : 32 Go
- Stockage :
  - NVMe 2 To (XFS – VM locales)
  - SATA SSD 2 To (ext4 – ISO & stockage secondaire)
- Rôle : Hyperviseur secondaire & sauvegarde (TrueNAS / PBS)
- Firmware : À compléter
