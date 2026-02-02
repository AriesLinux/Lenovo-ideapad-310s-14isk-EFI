<div align="center">

# 🍀 ideatosh Monterey on [ideapad-310s-14isk-EFI]
## By AriesLinux 

<img src="https://github.com/AriesLinux/Lenovo-ideapad-310s-14isk-EFI/blob/main/ideatosh%20LOGO.png" width="400" alt="ideatosh Logo">


![Clover](https://img.shields.io/badge/Clover-v5150+-green?style=for-the-badge&logo=leaf&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-Monterey%20(12.x)-white?style=for-the-badge&logo=apple)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

<p align="center">
  <strong>基於 Clover 引導的黑蘋果 EFI 配置</strong>
</p>

[English](./README_EN.md) | [简体中文](./README.md) | [繁體中文](./README_TW.md) | [粵語版本](./README_HK.md)

</div>

---

## 🖥️ 硬體配置 (Hardware Specs)

| 組件 (Component) | 型號 (Model) | 備註 (Notes) |
| :--- | :--- | :--- |
| **中央處理器 (CPU)** | [Intel Core i3-6100U] | 原生驅動 |
| **顯示卡 (GPU)** | [AMD Radeon R5 M430 (2GB GDDR3)] | 免驅支援 |
| **記憶體 (RAM)** | [4GB DDR4 2133MHz (單條)] | 插槽識別正常 |
| **硬碟 (Storage)** | [500GB 希捷藍盤 (5400轉)] | 正常識別，運作順暢 |

## 📊 運行狀態 (Status)

### ✅ 正常運作 (Working)
* [x] **UEFI 引導** * [x] **顯示卡硬體加速** (Metal / H.264 / HEVC)
* [x] **音效卡** (AppleALC 注入)
* [x] **有線網路卡** & **Wi-Fi**
* [x] **藍牙**
* [x] **iServices** (iMessage / iCloud 等)
* [x] **睡眠與喚醒**
* [x] **USB 端口** (使用 Hackintool 定制)

### ❌ 尚未解決 (Not Working)
* [ ] [隔空投送 (AirDrop) 無法使用]*
* [ ] [無法更新系統]*

---

## ⚙️ BIOS 設置 (BIOS Settings)

**為了確保 Clover 能夠順利引導 macOS 12，請檢查以下設置：**

* **停用 (Disable):**
    * Fast Boot (快速啟動)
    * Secure Boot (安全啟動)
    * CSM (Compatibility Support Module) - **建議關閉，純 UEFI 模式最佳**
    * CFG Lock (如果無法關閉，請在 config.plist 的 KernelToPatch 中處理)

* **啟用 (Enable):**
    * VT-x
    * Above 4G decoding
    * Hyper-Threading
    * EHCI/XHCI Hand-off
    * OS type: Windows 8.1/10 UEFI Mode

---

## ⚠️ Clover 特別注意事項 (Clover Specifics)

**針對 macOS 12 Monterey 的關鍵設置：**

1.  **Quirks 設置**:
    macOS 12 極大依賴 `OpenRuntime.efi`，本 EFI 已在 `config.plist` -> `Quirks` 中進行了相關配置，**請勿隨意更改 Quirks 部分的勾選**，除非你非常清楚它們的作用

2.  **Kext 位置**:
    所有驅動均放置在 `EFI/CLOVER/kexts/Other` 目錄下，請確保 `Inject Kexts` 設置為 `Yes` 或 `Detect`

3.  **生成 SMBIOS**:
    雖然已經內建一個預設的 SMBIOS，但強烈建議將本配置文件中的序列號清除，並使用 **Clover Configurator** 生成新的：
    * `Serial Number`
    * `Board Serial Number`
    * `SmUUID`
    * 務必檢查 `RtVariables` -> `ROM` 和 `MLB`

4.  **維護工具**:
    建議使用最新版的 [Clover Configurator](https://mackie100projects.altervista.org/clover-configurator/) 來編輯 `config.plist`

## 👏 鳴謝 (Credits)

* [CloverHackyColor](https://github.com/CloverHackyColor/CloverBootloader) 維護的 Clover Bootloader 專案
* [Acidanthera](https://github.com/acidanthera) 提供 OpenRuntime, Lilu, WhateverGreen 等核心驅動
* [Slice](https://github.com/Slice) 及所有 Clover 的貢獻者

---

<div align="center">
  <p>如果這個 EFI 救了你的黑蘋果，請去B站關注我吧 o((>ω< ))o❤</p>
</div>
