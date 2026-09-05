# Lenovo ThinkPad T530 macOS Sequoia EFI

This repository contains the OpenCore EFI configuration files required to run **macOS Sequoia 15.7.9 natively on a Lenovo ThinkPad T530**. 

## 💻 Hardware Configuration

| Component | Specification & Hackintosh Notes |
| :--- | :--- |
| **Laptop Model** | Lenovo ThinkPad T530 |
| **Processor (CPU)** | Intel Core 3rd Generation (Ivy Bridge - Core i5-3380M) |
| **Chipset** | Intel QM77 Express Mobile PCH |
| **Graphics (GPU)** | Intel HD Graphics 4000 *(Requires OCLP-X root patching)* |
| **Wi-Fi Chip** | Intel Centrino Ultimate-N 6300 
| **Bluetooth** | Broadcom Bluetooth 4.0 module
| **LAN (Ethernet)** | Intel 82579LM Gigabit Network Connection
| **Bootloader** | OpenCore v1.0.7 |

## ⚙️ What Works & What Doesn't
> ⚠️ **Note:** Running macOS Sequoia on Ivy Bridge hardware requires specific root patching (via OpenCore Legacy Patcher X) for graphics acceleration and wireless networking, as Apple dropped native support for this architecture in recent macOS versions. 

### Working
* Graphic acceleration and metal support on intel HD 4000 using OCLP-X
* native WIFI support after OCLP-X root patch 
* Native boot via OpenCore
* Audio and internal microphone
* Bluetooth
* Battery status indicator
* USB Ports (3.0 and 2.0)
* Ethernet port
* Keyboard and TrackPad / TrackPoint

### Requires Post-Install Patching
* **Graphics:** Intel HD 4000 graphics acceleration requires OpenCore Legacy Patcher-X (OCLP-X) root patches.
* **Wi-Fi/Bluetooth:** Depends on your specific card; Broadcom or Intel cards will require matching kexts and OCLP root patching.

## 🚀 Getting Started
1. **Bios Settings:** Ensure your BIOS is unlocked with 1virain. Set SATA Controller to `AHCI`, disable `Secure Boot`, and set Boot Mode to `UEFI Only or Both with CSM Enable or disable`.
2. **Generate SMBIOS:** Before booting, use **GenSMBIOS** to generate a unique serial number, Board Serial, and UUID.
     link: https://github.com/corpnewt/GenSMBIOS 
4. **Installation:** Use a standard macOS Sequoia  vanilla installer, copy this EFI to your USB drive's EFI partition, and boot.
5. **Post-Installation:** Download the latest version of **OpenCore Legacy Patcher-X** using this link "https://github.com/JeoJay127/OCLP-X/releases" to apply the necessary volume root patches for graphics and wireless networking.
    (note: only use OCLP-X only if you have a intel wireless card otherwise use dortania version: https://github.com/dortania/OpenCore-Legacy-Patcher/releases)

## 🤝 Credits
* @Acidanthera for OpenCore and essential kexts.
* @corpnewt for SSDTTime, GenSMBIOS, ProperTree.
* @Dortania for the comprehensive OpenCore Install Guide and Kexts.
* @USBToolBox for USB mapping tool and Kext
* The OpenCore Legacy Patcher team for making macOS Sequoia possible on legacy hardware.
