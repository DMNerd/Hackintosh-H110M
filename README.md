# Hackintosh_EFI

This is my personal Hackintosh repo. 

## [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases) 
Version: 0.5.9

### What works

Native Power Management ✅

Wifi/Bluetooth ✅

Hardware Acceleration (iGpu in headless mode) ✅

Apple Services ✅

## Main PC specs 

![Neofetch](https://i.imgur.com/NRFRISI.png)

I dualboot MacOS Catalina with Windows 10 (I do usually not use Windows nowadays but for the rare ocasion of playing a game it is usefull)

MoBo: [Gigabyte H110m ds2 DDR3](https://www.gigabyte.com/Motherboard/GA-H110M-DS2-DDR3-rev-10#ov)

CPU: [i5 6500 skylake](https://ark.intel.com/content/www/us/en/ark/products/88184/intel-core-i5-6500-processor-6m-cache-up-to-3-60-ghz.html)

GPU: Sapphire Radeon RX 460 4GB [bios modded](https://www.overclock.net/forum/67-amd/1633317-wip-rx460-rx560-conversion-pack-asus-gigabyte-msi-powercolor-sapphire-xfx.html "bios modded") to RX 560 4GB. Make sure your card is on the confirmed working if you feel like not risking it (this one is).

RAM: Kingston 8GB

Wifi/BT Card: [Fenvi HB1200 PCI WiFi](https://www.aliexpress.com/item/33034394024.html?spm=a2g0s.9042311.0.0.69f64c4dVPLsGp) natively supported wifi card based on the BCM94360CS2 chipset. Works like a charm, bluetooth range is slightly better if you get better antennas.

![PC](https://i.imgur.com/fc48zst.jpg)

### Disk setup 

MAC - 250gb Crucial Balistix SSD + Seagate 1TB HDD 

WIN - 250gb Samsung 950 EVO + Seagate Barracuda 1TB HDD

## Kernel Extensions 

My setup does not require many kexts. I built all from source using [Lilu-and-Friends](https://github.com/corpnewt/Lilu-and-Friends). Masive thanks to corpnewt, you are the boss!

Sound: [AppleALC](https://github.com/acidanthera/applealc/releases)

Graphics: [Lilu](https://github.com/acidanthera/lilu/releases) and [WhateverGreen](https://github.com/acidanthera/whatevergreen/releases)

LAN: [RealtekRTL8111](https://bitbucket.org/RehabMan/os-x-realtek-network/downloads/) 

USB: I used [USBMap](https://github.com/corpnewt/USBMap) to generate custom injector kext. This tool is again by the amazing corpnewt

## SMBIOS

Closest comparable iMac is [iMac 17.1](https://everymac.com/ultimate-mac-lookup/?search_keywords=iMac17,1). So that is the SMBIOS we choose. For the platform info we use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). 
Do not forget to run your generated serial number against [EveryMac.com's Ultimate Mac Lookup](https://everymac.com/ultimate-mac-lookup/) and [Apple's service coverage check](https://checkcoverage.apple.com/cz/cs/) for Apple services to work. If the result looks like the images bellow, you should be good!

![EveryMac](https://i.imgur.com/1oUg6va.png)


![Apple](https://www.tonymacx86.com/media/10-apple-right.187078/full?d=1470318026)