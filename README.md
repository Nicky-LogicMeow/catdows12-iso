# Catdows 12 — Official ISO & Image Releases

> **Catdows 12 (Windows 11 24H2 Cat Edition)** is a lightweight, high-performance operating system modeled after Windows 11 with a Catppuccin Mocha aesthetic, built with a 100% native C11 desktop shell and system utilities.

---

## 💿 Available Images

| Image | Format | Target Hardware | Description |
|---|---|---|---|
| `catdows12-real-hardware.img` | Hybrid GPT/MBR Disk Image | Real x86_64 PCs (UEFI + BIOS) | Full bootable live USB installation medium for physical hardware. |
| `windows-cat-edition.qcow2` | QCOW2 Virtual Disk | QEMU / KVM / Proxmox | Pre-configured virtual disk image for virtual machine testing. |

---

## 🚀 How to Flash to USB Drive

### Option 1: Rufus (Windows)
1. Download **Rufus** (https://rufus.ie/).
2. Select your USB flash drive (minimum 16 GB recommended).
3. Select `catdows12-real-hardware.img`.
4. Partition scheme: **GPT**, Target system: **UEFI (non-CSM)** or BIOS.
5. Click **Start** (write in DD image mode if prompted).

### Option 2: BalenaEtcher (Windows, macOS, Linux)
1. Download **BalenaEtcher** (https://etcher.balena.io/).
2. Select `catdows12-real-hardware.img`.
3. Select your USB drive.
4. Click **Flash!**.

### Option 3: Linux Command Line (`dd`)
```bash
# Identify your USB drive (e.g. /dev/sdb)
lsblk

# Flash directly to raw block device (replace /dev/sdX with your actual USB device)
sudo dd if=catdows12-real-hardware.img of=/dev/sdX bs=4M status=progress conv=fdatasync
sudo sync
```

---

## 🖥️ System Requirements
- **CPU**: 64-bit x86_64 Dual-Core or faster (Intel Core 2 Duo / Core i3/i5/i7 / AMD Ryzen or newer).
- **RAM**: 2 GB minimum (4 GB+ recommended).
- **Graphics**: Intel HD Graphics (Skylake, Kaby Lake, Comet Lake, Iris Xe), AMD Radeon, or NVIDIA GeForce.
- **Storage**: 16 GB USB flash drive or internal SATA/NVMe drive.

---

## 🔒 Source Code
The complete native C11 operating system shell, drivers, and supervisor source code is maintained privately at:
👉 **[Nicky-LogicMeow/catdows12](https://github.com/Nicky-LogicMeow/catdows12)**
