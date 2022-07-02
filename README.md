# Hackintosh-OptiPlex-7080-MT

![](https://raw.githubusercontent.com/webleon/Hackintosh-OptiPlex-7080-MT/main/images/iShot2022-05.png)

**Opencore Bootloader 0.8.1. Tested on Monterey 12.4**



## Introdution
You will have to [**generate a new SMIBIOS**](https://github.com/corpnewt/GenSMBIOS) before login to your iCloud account.



## Hardware Specs
* **Desktop Computer**: [Dell OptiPlex 7080 Tower](https://www.dell.com/en-us/work/shop/desktops-all-in-one-pcs/optiplex-7080-tower-and-small-form-factor/spd/optiplex-7080-desktop) 
* **CPU**:  [Intel® Core™ i7-10700](https://ark.intel.com/content/www/us/en/ark/products/199316/intel-core-i710700-processor-16m-cache-up-to-4-80-ghz.html)
* **iGPU**: Intel® UHD Graphics 630
* **GPU**: [ASRock AMD Radeon RX 6600 XT Challenger ITX 8GB](https://www.asrock.com/Graphics-Card/AMD/Radeon%20RX%206600%20XT%20Challenger%20ITX%208GB/)
* **RAM**: 64GB DDR4 2933 Daul Channel
* **HDD**: WD Blue SN550 NVMe SSD 1T
* **LAN**: Intel X540-T2 / AQC107 / Intel I219LM11
* **Wi-Fi & Bluetooth**: BCM94360NG



## Working
* CPU Turbo Boost & SpeedStep
* Radeon™ RX 6600 XT & iGPU acceleration
* Internal Speaker / Front panel headphone out / Back panel lineout
* USB Ports (rear USB 2.0 ports disabled due to macOS ports limit)
* 10G LAN & Wireless Network
* Sleep & Wakeup
* Airdrop / Airplay /  Handoff

## Not working
* Sidecar (needs T2 chip)
* DRM Content in Safari (needs T2 chip)



## UEFI Settings
* System Configuration → Serial Port: ***Disabled***
* System Configuration → SATA Operation: ***AHCI***
* Video → Multi Display: ***Enable Multi-Display***
* Video → Primary Display: ***Auto***
* Security → PTT Security: ***uncheck***
* Secure Boot → Secure Boot Enable: ***uncheck***
* Intel® Software Guard Extensions™ → Intel® SGX™ Enable: ***uncheck***
* Virtualization Support → VT for Direct I/O: ***check***



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
* ~~Add [SSDT-Shutdown.aml](https://dortania.github.io/OpenCore-Post-Install/usb/misc/shutdown.html) to fix shutdown~~ no longer needed
* Add [SSDT-GPRW.aml](https://dortania.github.io/OpenCore-Post-Install/usb/misc/instant-wake.html) to improve sleep / wake
* Add [SSDT-HPET.aml](https://dortania.github.io/Getting-Started-With-ACPI/Universal/irq.html) to fix IRQ conflicts



## X540-T2 eeprom modification
### Flashing eeprom could brick the NIC card, do it at your own risk.
* [Original Guide](https://forums.macrumors.com/threads/modify-retail-intel-10gbe-nics-to-use-small-tree-macos-drivers.1968456/)
* For my X540-T2 cards, the commands look like this:
```
sudo ethtool -E <eth1 name> magic 0x15288086 offset 0x48e value 0x0a
sudo ethtool -E <eth1 name> magic 0x15288086 offset 0x48f value 0x00
sudo ethtool -E <eth2 name> magic 0x15288086 offset 0x48e value 0x0a
sudo ethtool -E <eth2 name> magic 0x15288086 offset 0x48f value 0x00
```



## Changelog

**2022-07-02**
* suport AQC107 10GbE LAN (VT for Direct I/O need to be enabled in UEFI)
* update to Opencore 0.8.1
* KEXTs up to date
* other minor updates

**2022-05-23**
* update to Opencore 0.8.0
* tested on Monterey 12.4 release
* minor updates

**2021-12-15**
* update to Opencore 0.7.6
* tested on Monterey 12.1 release
* add iGPU config
* minor updates

**2021-12-04**
* remove no longer needed SSDT-Shutdown.aml 
* add [RadeonSensor](https://github.com/aluveitie/RadeonSensor) to show Radeon GPU temperature

**2021-11-27**
* initial upload
