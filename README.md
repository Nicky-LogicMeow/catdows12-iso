# Catdows 12 — Official ISO & Image Releases

Catdows 12 (Windows 11 24H2 Cat Edition) is a lightweight, high-performance operating system modeled after Windows 11 with a Catppuccin Mocha visual aesthetic, built with a 100% native C11 desktop shell and system utilities.

---

## Release Images

| Image | Format | Target Platform | Description |
|---|---|---|---|
| `catdows12-real-hardware.img.xz` | Compressed Hybrid Disk Image | Real x86_64 PCs (UEFI + BIOS) | Bootable live USB installation medium for physical PC hardware. |
| `windows-cat-edition.qcow2` | QCOW2 Virtual Disk | QEMU / KVM / Proxmox | Pre-configured virtual disk image for virtual machine testing. |

---

## Flashing to Physical Storage Media

### Method 1: Linux Command Line (`dd`)
```bash
# Decompress and flash directly to target USB device (e.g. /dev/sdX)
xz -dc catdows12-real-hardware.img.xz | sudo dd of=/dev/sdX bs=4M status=progress conv=fdatasync
sudo sync
```

### Method 2: Rufus (Windows)
1. Download Rufus from https://rufus.ie/
2. Select target USB flash drive (minimum 16 GB).
3. Select `catdows12-real-hardware.img` (extracted).
4. Partition scheme: GPT, Target system: UEFI (non-CSM) or BIOS.
5. Click Start (select Write in DD Image mode if prompted).

### Method 3: BalenaEtcher (Cross-Platform)
1. Download BalenaEtcher from https://etcher.balena.io/
2. Select the disk image file.
3. Select the target USB flash drive.
4. Click Flash.

---

## Hardware Specifications

- Processor: 64-bit x86_64 dual-core or faster (Intel Core / Xeon, AMD Athlon / Ryzen)
- RAM: Minimum 2 GB (4 GB recommended)
- Graphics: Intel HD / Iris / Xe, AMD Radeon, or NVIDIA GeForce
- Boot Firmware: UEFI (x86_64-efi) or Legacy BIOS (i386-pc)
- Target Disk: SATA, NVMe, AHCI, or IDE internal drive (16 GB minimum)

---

## Source Repository

The complete native C11 operating system shell, device drivers, and system supervisors are maintained at:
https://github.com/Nicky-LogicMeow/catdows12
