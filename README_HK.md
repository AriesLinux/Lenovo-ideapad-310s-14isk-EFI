<div align="center">

# 🍀 ideatosh Monterey on [ideapad-310s-14isk-EFI]
## By AriesLinux 

<img src="https://github.com/AriesLinux/Lenovo-ideapad-310s-14isk-EFI/blob/main/ideatosh%20LOGO.png" width="400" alt="ideatosh Logo">

![Clover](https://img.shields.io/badge/Clover-v5150+-green?style=for-the-badge&logo=leaf&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-Monterey%20(12.x)-white?style=for-the-badge&logo=apple)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

<p align="center">
  <strong>基於 Clover 導引嘅黑蘋果 EFI</strong>
</p>

[English](./README_EN.md) | [简体中文](./README.md) | [繁體中文](./README_TW.md) | [粵語版本](./README_HK.md)

</div>

---

## 🖥️ 硬件配置 (Specs)

| 組件 | 型號 | 備註 |
| :--- | :--- | :--- |
| **CPU** | [Intel Core i3-6100U] | 原生驅動，冇病冇痛 |
| **顯卡 (GPU)** | [AMD Radeon R5 M430 (2GB GDDR3)] | 免驅，直插直用 |
| **RAM** | [4GB DDR4 2133MHz (單條)] | 插槽認得好清楚 |
| **硬碟** | [500GB 希捷藍盤 (5400轉)] | 認得倒，行得都算順 |

## 📊 運行情況 (Status)

### ✅ 搞掂咗嘅嘢 (Working)
* [x] **UEFI 引導** (成功開機入系統)
* [x] **顯卡硬件加速** (Metal / H.264 / HEVC)
* [x] **聲卡** (AppleALC 注入)
* [x] **有線網卡 & Wi-Fi** (上到網)
* [x] **藍牙** (配對到)
* [x] **iServices** (iMessage / iCloud 嗰啲都得)
* [x] **睡眠同喚醒**
* [x] **USB 端口** (用 Hackintool 定製咗喇)

### ❌ 仲未搞掂 (Not Working)
* [ ] [AirDrop 用唔到]*
* [ ] [更新唔到系統]*

---

## ⚙️ BIOS 點樣 Set (BIOS Settings)

**想 Clover 順利入到 macOS 12，記得睇下 BIOS 呢啲位：**

* **熄咗佢 (Disable):**
    * Fast Boot (快速啟動)
    * Secure Boot (安全啟動)
    * CSM (兼容模式) - **建議熄咗佢，用純 UEFI 係最好嘅**
    * CFG Lock (如果 BIOS 冇得熄，就要喺 config.plist 搞)

* **開咗佢 (Enable):**
    * VT-x
    * Above 4G decoding
    * Hyper-Threading
    * EHCI/XHCI Hand-off
    * OS type: Windows 8.1/10 UEFI Mode

---

## ⚠️ Clover 注意事項

**玩 macOS 12 Monterey 嘅重點：**

1.  **Quirks 設置**:
    macOS 12 好依賴 `OpenRuntime.efi`，呢份 EFI 已經喺 `config.plist` -> `Quirks` 度執好晒，**唔好手痕隨便改動佢**，除非你真係好清楚自己做緊乜

2.  **Kext 位置**:
    所有 Kext 驅動都擺喺 `EFI/CLOVER/kexts/Other` 入面，記得檢查 `Inject Kexts` 係咪 set 做 `Yes` 或者 `Detect`

3.  **搞返好個 SMBIOS**:
    雖然入面已經有個預設嘅 SMBIOS，但我**強烈建議**你用 **Clover Configurator** 重新整過一組新嘅序列號：
    * `Serial Number`
    * `Board Serial Number`
    * `SmUUID`
    * 記得 Check 埋 `RtVariables` 入面個 `ROM` 同 `MLB`

4.  **維護工具**:
    建議用最新版嘅 [Clover Configurator](https://mackie100projects.altervista.org/clover-configurator/) 嚟改 `config.plist`

## 👏 鳴謝 (Credits)

* [CloverHackyColor](https://github.com/CloverHackyColor/CloverBootloader) 搞出嚟嘅 Clover Bootloader
* [Acidanthera](https://github.com/acidanthera) 提供 OpenRuntime, Lilu, WhateverGreen 呢啲咁重要嘅 Kext
* [Slice](https://github.com/Slice) 同埋一眾 Clover 貢獻者

---

<div align="center">
  <p>如果呢個 EFI 幫到你開機，唔該去B站關注下我啦罷o((>ω< ))o❤</p>
</div>
