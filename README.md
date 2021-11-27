# Hackintosh-OptiPlex-7080-MT

![](https://raw.githubusercontent.com/webleon/Hackintosh-OptiPlex-7080-MT/main/images/iShot2021-11-27.png)

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


## Modify DVMT & CFG_lock settings
* BIOS/UEFI editor [ru.efi](https://github.com/JamesAmiTw/ru-uefi)
* Disable CFG lock: 
set ***003E*** to ***0x00*** under ***CPUSetup***
* 64M Pre-Allocated DVMT: 
set ***00F5*** to ***0x02*** under ***SASetup***



## USB Mapping
USB ports map:
![](https://raw.githubusercontent.com/webleon/Hackintosh-OptiPlex-7080-MT/main/images/Dell_OptiPlex_7080_MT.png)

* HS09 and HS10 disabled due to the MacOS USB ports limit.
* Check [Dortania's guide](https://dortania.github.io/OpenCore-Post-Install/usb/manual/manual.html) for more infos on USB mapping.


## ACPI tweaks
* Create general SSDTs using [SSDTTime](https://dortania.github.io/Getting-Started-With-ACPI/ssdt-methods/ssdt-easy.html#running-ssdttime) 
* Add [SSDT-Shutdown.aml](https://dortania.github.io/OpenCore-Post-Install/usb/misc/shutdown.html) to fix shutdown
* Add [SSDT-GPRW.aml](https://dortania.github.io/OpenCore-Post-Install/usb/misc/instant-wake.html) to improve sleep / wake



## Changelog

**2021-11-27**
* initial upload
