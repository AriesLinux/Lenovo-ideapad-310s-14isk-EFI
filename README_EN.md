<div align="center">

# 🍀 ideatosh Monterey on [ideapad-310s-14isk-EFI]
## By AriesLinux 

<img src="https://github.com/AriesLinux/-ideapad-310s-14isk-EFI/blob/main/CloverIcon.png" width="150" alt="Clover Logo">

![Clover](https://img.shields.io/badge/Clover-v5150+-green?style=for-the-badge&logo=leaf&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-Monterey%20(12.x)-white?style=for-the-badge&logo=apple)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

<p align="center">
  <strong>Hackintosh EFI based on Clover Bootloader</strong>
</p>

[English](./README_EN.md) | [简体中文](./README.md)

</div>

---

## 🖥️ Hardware Specs

| Component | Model | Notes |
| :--- | :--- | :--- |
| **CPU** | [Intel Core i3-6100U] | Native Support |
| **GPU** | [AMD Radeon R5 M430 (2GB GDDR3)] | Native/OOB |
| **RAM** | [4GB DDR4 2133MHz (Single)] | Slot recognized correctly |
| **Storage** | [500GB Seagate Blue (5400RPM)] | Recognized, running smoothly |

## 📊 Status

### ✅ Working
* [x] **UEFI Booting** * [x] **Graphics Acceleration** (Metal / H.264 / HEVC)
* [x] **Audio** (AppleALC Injection)
* [x] **Ethernet & Wi-Fi**
* [x] **Bluetooth**
* [x] **iServices** (iMessage, iCloud, etc.)
* [x] **Sleep & Wake**
* [x] **USB Ports** (Mapped via Hackintool)

### ❌ Not Working
* [ ] [AirDrop is unavailable]*
* [ ] [System Updates not working]*

---

## ⚙️ BIOS Settings

**To ensure Clover boots macOS 12 successfully, please check the following:**

* **Disable:**
    * Fast Boot
    * Secure Boot
    * CSM (Compatibility Support Module) - **Disabled for pure UEFI mode**
    * CFG Lock (If it cannot be disabled, use KernelToPatch in config.plist)

* **Enable:**
    * VT-x
    * Above 4G decoding
    * Hyper-Threading
    * EHCI/XHCI Hand-off
    * OS type: Windows 8.1/10 UEFI Mode

---

## ⚠️ Clover Specifics

**Key settings for macOS 12 Monterey:**

1.  **Quirks Settings**:
    macOS 12 relies heavily on `OpenRuntime.efi`. This EFI has been configured in `config.plist` -> `Quirks`. **Do not change the Quirks selection** unless you know exactly what you are doing.

2.  **Kext Location**:
    All drivers are located in `EFI/CLOVER/kexts/Other`. Ensure `Inject Kexts` is set to `Yes` or `Detect`.

3.  **Generate SMBIOS**:
    Although a default SMBIOS is provided, it is strongly recommended to clear the serial numbers and generate your own using **Clover Configurator**:
    * `Serial Number`
    * `Board Serial Number`
    * `SmUUID`
    * Double-check `RtVariables` -> `ROM` and `MLB`.

4.  **Maintenance Tool**:
    Use the latest version of [Clover Configurator](https://mackie100projects.altervista.org/clover-configurator/) to edit your `config.plist`.

## 👏 Credits

* [CloverHackyColor](https://github.com/CloverHackyColor/CloverBootloader) for the Clover Bootloader project.
* [Acidanthera](https://github.com/acidanthera) for OpenRuntime, Lilu, WhateverGreen, and other core kexts.
* [Slice](https://github.com/Slice) and all Clover contributors.

---

<div align="center">
  <p>If this EFI saved your Hackintosh, please follow me on bilibili! o((>ω< ))o❤</p>
</div>
