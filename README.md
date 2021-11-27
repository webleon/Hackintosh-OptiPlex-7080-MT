# Hackintosh-OptiPlex-7080-MT

![](https://raw.png)

**Opencore Bootloader 0.7.5. Tested on Monterey 12.1 beta**


## Introdution
You will have to [**generate a new SMIBIOS**](https://github.com/corpnewt/GenSMBIOS) before login to your iCloud account.


## Hardware Specs
* **Desktop Computer**: [Dell OptiPlex 7080 Tower](https://www.dell.com/en-us/work/shop/desktops-all-in-one-pcs/optiplex-7080-tower-and-small-form-factor/spd/optiplex-7080-desktop) 
* **CPU**:  [Intel® Core™ i7-10700](https://ark.intel.com/content/www/us/en/ark/products/199316/intel-core-i710700-processor-16m-cache-up-to-4-80-ghz.html)
* **iGPU**: Intel® UHD Graphics 630
* **GPU**: [AMD Radeon RX 6600 XT Challenger ITX 8GB](https://www.asrock.com/Graphics-Card/AMD/Radeon%20RX%206600%20XT%20Challenger%20ITX%208GB/)
* **RAM**: 64GB DDR4 2933 Daul Channel
* **HDD**: WD Blue SN550 NVMe SSD 1T
* **LAN**: Intel X540-T2 / Intel I219LM11
* **Wi-Fi & Bluetooth**: BCM94360NG


## Working
* CPU Turbo Boost & SpeedStep
* Radeon™ RX 6600 XT & iGPU acceleration
* ALC 256 audio
* USB Ports (exept 2 rear USB 2.0 ports due to 15 ports limit)
* 10G LAN & Wireless Network
* Sleep & Wakeup


## Not working
* 


## BIOS Settings
* General → Advanced Boot Options: ***uncheck***
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ Enable: ***Disabled***
* ~~Power Management → Block Sleep: ***check***~~
* Virtualization Support → VT for Direct I/O: ***uncheck***


## BIOS Settings via RU
* Set Pre-Allocated DVMT to 64M: 
***00F5 0x02***
* Disable CFG lock: 
***003E 0x00***


## USB Mapping
USB ports map:
![](https://raw.githubusercontent.com/webleon/Hackintosh-OptiPlex-7070-SFF/master/images/usbports.png)

* HS01 and HS10 have been blocked due to the MacOS USB ports limit.
* Check [Dortania's guide](https://dortania.github.io/OpenCore-Post-Install/usb/manual/manual.html) for more infos on USB mapping.


## Changelog

**2021-11-27**
* initial upload
