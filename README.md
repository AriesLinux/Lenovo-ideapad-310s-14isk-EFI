<div align="center">

# 🍀 ideatosh Monterey on [ideapad-310s-14isk-EFI]
## By AriesLinux 

<img src="https://github.com/AriesLinux/-ideapad-310s-14isk-EFI/blob/main/CloverIcon.png" width="150" alt="Clover Logo">

![Clover](https://img.shields.io/badge/Clover-v5150+-green?style=for-the-badge&logo=leaf&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-Monterey%20(12.x)-white?style=for-the-badge&logo=apple)

<p align="center">
  <strong>基于 Clover 引导的黑苹果EFI</strong>
</p>

[English](./README_EN.md) | [简体中文](./README.md) | [繁體中文](./README_TW.md) | [粵語版本](./README_HK.md)

</div>

---

## 🖥️ 硬件配置 (Hardware Specs)

| 组件 (Component) | 型号 (Model) | 备注 (Notes) |
| :--- | :--- | :--- |
| **CPU** | [Intel Core i3-6100U] | 原生驱动 |
| **显卡 (GPU)** | [AMD Radeon R5 M430 (2GB GDDR3显存)] | 免驱 |
| **内存 (RAM)** | [4GB DDR4 2133MHz (单条)] | 插槽识别没问题 |
| **硬盘 (Storage)** | [500GB 希捷蓝盘 (5400转)] | 正常识别，运行顺畅 |

## 📊 运行状态 (Status)

### ✅ 正常工作 (Working)
* [x] **UEFI 引导** 
* [x] **显卡硬件加速** (Metal / H.264 / HEVC)
* [x] **声卡** (AppleALC 注入)
* [x] **有线网卡** & **Wi-Fi**
* [x] **蓝牙**
* [x] **iServices** 
* [x] **睡眠与唤醒**
* [x] **USB 端口** (使用 Hackintool 定制)

### ❌ 暂未解决 (Not Working)
* [ ] [隔空投送无法使用]*
* [ ] [无法更新系统]*

---

## ⚙️ BIOS 设置 (BIOS Settings)

**为了确保 Clover 能够顺利引导 macOS 12，请检查以下设置：**

* **Disable (禁用):**
    * Fast Boot
    * Secure Boot
    * CSM (Compatibility Support Module) - **建议关闭，纯 UEFI 模式最佳**
    * CFG Lock (如果无法关闭，请在 config.plist 的 KernelToPatch 中处理)

* **Enable (启用):**
    * VT-x
    * Above 4G decoding
    * Hyper-Threading
    * EHCI/XHCI Hand-off
    * OS type: Windows 8.1/10 UEFI Mode

---

## ⚠️ Clover 特别注意事项 (Clover Specifics)

**针对 macOS 12 Monterey 的关键设置：**

1.  **Quirks 设置**:
    macOS 12 极大依赖 OpenRuntime.efi，本 EFI 已在 `config.plist` -> `Quirks` 中进行了相关配置，**请勿随意更改 Quirks 部分的勾选**，除非你非常清楚它们的作用

2.  **Kext 位置**:
    所有驱动均放置在 `EFI/CLOVER/kexts/Other` 目录下，请确保 `Inject Kexts` 设置为 `Yes` 或 `Detect`

3.  **生成 SMBIOS**:
    虽然已经生成一个默认的SMBIOS，但强烈建议将本配置文件中的序列号清空，并使用 **Clover Configurator** 生成新的：
    * `Serial Number`
    * `Board Serial Number`
    * `SmUUID`
    * 务必检查 `RtVariables` -> `ROM` 和 `MLB`。

4.  **维护工具**:
    建议使用最新版的 [Clover Configurator](https://mackie100projects.altervista.org/clover-configurator/) 来编辑 `config.plist`。


## 👏 致谢 (Credits)

* [CloverHackyColor](https://github.com/CloverHackyColor/CloverBootloader) 维护的 Clover Bootloader 项目。
* [Acidanthera](https://github.com/acidanthera) 提供 OpenRuntime, Lilu, WhateverGreen 等核心驱动。
* [Slice](https://github.com/Slice) 及所有 Clover 的贡献者。

---

<div align="center">
  <p>如果这个 EFI 救了你的黑苹果，请去B站灌注我罢o((>ω< ))o❤</p>
</div>
