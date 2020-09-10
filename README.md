# 🍏 Hackintosh

This is my personal Hackintosh repo. 

![SysInfo](https://raw.githubusercontent.com/DMNerd/Hackintosh_EFI/master/Resources/Screenshots/SysInfo.png)

## [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) 

Version: 0.6.1

OpenCanopy bootscreen is enabled 

### ✅ What works

* Native Power Management ✅
* Wifi/Bluetooth ✅
* File Vault ✅
* Hardware Acceleration (iGpu in headless mode) ✅
* Apple Services ✅

## ⚙️ Hardware 
| Part | Info/Link |
| --- | --- |
| **MoBo** | [Gigabyte H110m ds2 DDR3](https://www.gigabyte.com/Motherboard/GA-H110M-DS2-DDR3-rev-10#ov) |
| **CPU** | [i5 6500 skylake](https://ark.intel.com/content/www/us/en/ark/products/88184/intel-core-i5-6500-processor-6m-cache-up-to-3-60-ghz.html) |
| **GPU** | Sapphire Radeon RX 460 4GB [bios modded](https://www.overclock.net/forum/67-amd/1633317-wip-rx460-rx560-conversion-pack-asus-gigabyte-msi-powercolor-sapphire-xfx.html "bios modded") to RX 560 4GB. Make sure your card is on the confirmed working if you feel like not risking it (this one is) |
| **RAM** | Kingston 8GB |
| **Wifi/BT Card** | [Fenvi HB1200 PCI WiFi](https://www.aliexpress.com/item/33034394024.html?spm=a2g0s.9042311.0.0.69f64c4dVPLsGp) natively supported wifi card based on the BCM94360CS2 chipset |
| **Storage for MAC** | 250gb Crucial Balistix SSD + Seagate 1TB HDD |
| **Storage for Mindows** | 250gb Samsung 950 EVO + Seagate Barracuda 1TB HDD |
| **Case** | [Fortron CMT240](https://www.fsp-europe.com/CS/cmt240/) |

![PC](https://i.imgur.com/fc48zst.jpg)

## 🛠️ Kernel Extensions 

My setup does not require many kexts. I built all from source using [Lilu-and-Friends](https://github.com/corpnewt/Lilu-and-Friends). Masive thanks to @corpnewt, you are the boss!

**SMC:** [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases)

**Sound:** [AppleALC](https://github.com/acidanthera/applealc/releases)

**Graphics:** [Lilu](https://github.com/acidanthera/lilu/releases) and [WhateverGreen](https://github.com/acidanthera/whatevergreen/releases)

**LAN:** [RealtekRTL8111](https://bitbucket.org/RehabMan/os-x-realtek-network/downloads/) 

## USB

Strictly speaking, these comonents **do not** need USB mapping. You do not get over the arbitrary limit imposed by MacOS. But there are some advantages, like marking the port bluetooth hub is connected to as internal and making sure your usb 3 runs on the maximum speed. 

I used [Hackintool](https://github.com/headkaze/Hackintool) to generate custom injector kext. This just seemed to work much better for me. 

1. Identifying ports - I have done tho work for you on this board

![USBMap](https://github.com/DMNerd/Hackintosh/blob/master/Resources/Extra/USBmap/USBMap.png)

2. Setting up Hackintool accordingly

![HackintoolPNG](https://raw.githubusercontent.com/DMNerd/Hackintosh/master/Resources/Screenshots/HackintoolUSB.png)

3. Export and use the USBPorts.kext

## OS switching through bootcamp

So one of the coolest features to OpenCore in my opinion is the ability to switch OS using native methods such as Bootcamp. 

1. Boot to windows and download CorpNewt's [brigadier](https://github.com/corpnewt/brigadier) 

2. Run the tool. It will download Bootcamp with version native to your SMBIOS - SOME OF THEM USE OLDER VERSION WITHOUT APPFS SUPPORT! In that case do not reboot straight after instalation.

3. Install Bootcamp by double clicking Setup found in the downloaded folder (in the script's location directory). 

4. Run the Apple Update software and let bootcamp update. It appears in the start menu.

5. Restart back to MacOS. You will see BOOTCAMP as option in Startup Disk settings. If it is not there, check that the disk is mounted by MacOS. 

![Bootcamp](https://raw.githubusercontent.com/DMNerd/Hackintosh/master/Resources/Screenshots/Bootcamp.png)

I however found problem for people that use second HDD on their Windows. Since Bootcamp was never meant to be run with multiple drives, the setup just sets attributes of every other disk to Hidden. Instructuions on how to fix it can be found [here](https://github.com/DMNerd/Hackintosh/blob/master/Resources/Extra/Bootcamp/BOOTCAMPDRIVEFIX.md)

## CFG-Lock

This board does not have the abilitty to disable cfg-lock from bios - meaning it has to be done manually by finding the offset and applying it through the modified grub shell. The process can be found [here](https://dortania.github.io/OpenCore-Post-Install/misc/msr-lock.html#disabling-cfg-lock). 

## SMBIOS

Closest comparable iMac is [iMac 17.1](https://everymac.com/ultimate-mac-lookup/?search_keywords=iMac17,1). So that is the SMBIOS we choose. For the platform info we use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). For more info follow [iDiot's guide to iMessage](https://www.tonymacx86.com/threads/an-idiots-guide-to-imessage.196827/)

## Big Sur

I am happy to report that Big Sur will work. I tested it on a second SSD and it works seamlessly (Even though the beta supposedly doesn't work on the mac my SMBIOS is based on). Waiting for the full release to update though.

![BigSur](https://raw.githubusercontent.com/DMNerd/Hackintosh/master/Resources/Screenshots/bigsur.png)