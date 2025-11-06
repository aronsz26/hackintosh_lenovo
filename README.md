# 🖥️ Lenovo ThinkCentre M83 Hackintosh (macOS 12 Monterey)

This repository contains the **EFI folder** for running **macOS 12 Monterey** on a **Lenovo ThinkCentre M83**.  
It’s a stable and fully working configuration tested on real hardware — including full graphics acceleration with Intel HD 4600.

---

## ⚙️ System Specifications

| Component | Details |
|------------|----------|
| **Model** | Lenovo ThinkCentre M83 (SFF) |
| **CPU** | Intel Core i5-4670S (Haswell, 4 C / 4 T) |
| **iGPU** | Intel HD 4600 |
| **RAM** | 16 GB DDR3 1600 MHz |
| **Storage** | 256 GB SSD |
| **Ethernet** | Intel I217-LM (working with IntelMausi.kext) |
| **Audio** | Realtek ALC283 |
| **macOS Version** | macOS 12 Monterey (12.7.x) |
| **Bootloader** | OpenCore 1.0.5 |

---

## ✅ Working

- Full **macOS Monterey** installation (no kernel patches required)  
- **Intel HD 4600** graphics acceleration (QE/CI fully functional)  
- **Ethernet (IntelMausi)**  
- **Audio (AppleALC, layout-id = 1)**  
- **USB 2.0/3.0 ports**  
- **Sleep, Restart, Shutdown**  
- **App Store, iCloud, iMessage, FaceTime** (with valid SMBIOS serials)  

---

## ⚠️ Known Issues

- **VGA output not supported** (use HDMI or DP → HDMI active adapter)  
- **Dual-monitor** setup can cause both screens to go black on wake; use boot-arg `igfxonln=1`  
- **AirDrop / Continuity** not available (no native Wi-Fi / BT card)  
- **macOS updates beyond Monterey** require additional root patches (use OCLP ≥ 2.3.0 for Sonoma/Tahoe)  

---

## 🧩 Kexts Used

| Kext | Function |
|------|-----------|
| **Lilu.kext** | Core patch framework |
| **WhateverGreen.kext** | Graphics & iGPU patches |
| **VirtualSMC.kext** | Emulates SMC hardware |
| **AppleALC.kext** | Audio for ALC283 |
| **IntelMausi.kext** | Ethernet driver |
| *(Optional)* **SMCBatteryManager.kext** | Only for mobile boards |

---

## 🖥️ BIOS Settings

- **CSM Support** → Disabled  
- **Secure Boot** → Disabled  
- **SATA Mode** → AHCI  
- **Intel Virtualization** → Enabled  
- **Integrated Graphics** → Enabled  

---

## 🧠 SMBIOS

Using **iMac15,1** (Haswell 27" 2014).  
Make sure to generate your own serials with **GenSMBIOS** to avoid iCloud / Apple ID issues.

---

## 🧰 Software Compatibility

| Application | Status |
|--------------|---------|
| Final Cut Pro X | ✅ Works with HD 4600 |
| Logic Pro X | ✅ |
| Xcode | ✅ |
| Chrome / Safari | ✅ |
| Adobe Photoshop 2023 | ⚠️ Slight UI lag on heavy effects |
| DaVinci Resolve | ⚠️ Basic playback only (no Metal GPU) |
| Steam / Proton Games | ❌ Not supported on HD 4600 |

---

## 💬 Notes

- Always rebuild OpenCore with the latest version before applying macOS updates.  
- If you lose display output after reset, re-apply the correct iGPU properties:  

---

## 📸 Screenshots

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d765f8f8-ba19-4bb7-898e-652d12657a74" />


---

### 🔗 Credits

- [Dortania OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [Acidanthera Team](https://github.com/acidanthera)
- [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher)
- Community testers who helped debug HD4600 framebuffer issues 🙌

---

> **Disclaimer:**  
> This EFI is provided for educational purposes only.  
> Use at your own risk. All Apple trademarks are property of Apple Inc.
