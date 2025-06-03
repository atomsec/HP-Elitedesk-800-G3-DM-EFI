# OpenCore on HP ELite Desk 800 G3 DM

Minimum & Fully-Fixed EFI in HP elitedesk 800 G3 DM

Complete the configuration according to [OpenCore-Install-Guide](https://dortania.github.io/OpenCore-Install-Guide/).

## MacOs Version

---

- MacOS Sonoma 14.7.6

## System Configuration

---

- CPU: intel COre i7-6700T
- IGPU: Intel HD Graphics 530
- Memory: 16GB (8GB x 2) DDR4 2133 MHz
- WLAN & BT: **Intel Wireless-AC 8265**
- LAN: Intel I219-LM

### Bootloader

- OPenCore 1.0.4

### SMBIOS

- MacMini8,1

## Minimum EFI

---

- ACPI
    - [SSDT-AWAC-HPET-RTC.aml](https://github.com/corpnewt/SSDTTime)
    - [SSDT-EC-USBX.aml](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix.html)
    - [SSDT-PLUG.aml](https://dortania.github.io/Getting-Started-With-ACPI/Universal/plug.html)
- Drivers
    - HfsPlus.efi
    - OpenRuntime.efi
- Kexts
    - [Lilu.kext](https://github.com/acidanthera/Lilu)
    - [VirtualSMC.text](https://github.com/acidanthera/VirtualSMC)
    - [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen)
        
        > **Required Kexts**
        > 
    - [IntelMausi.kext](https://github.com/acidanthera/IntelMausi)
        
        > LAN Fixed
        > 
    - [USBToolBox.kext](https://github.com/USBToolBox/kext)
    - [USBMap.kext](https://github.com/corpnewt/USBMap)
        
        > USB Fixed
        > 

## Fully-Repaired EFI

---

- Kexts
    - [NVMeFix.kext](https://github.com/acidanthera/NVMeFix)
        
        > NVMe Fixed
        > 
    - [Airportitlwm.kext](https://github.com/OpenIntelWireless/itlwm)
        
        > WLAN Fixed
        > 
    - SMCSuperIO.kext
    - SMCProcessor.kext
        
        > CPU Temperature & Fan Speed Fixed
        > 
    - IntelBTpatcher.kext
    - [IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
    - [BlueToolFixup.kext](https://github.com/acidanthera/BrcmPatchRAM)
        
        > BT fixed
        > 

## Working

---

- iGPU Acceleration
    - If the screen has no signal, please try to change the input interface (if changing the input interface does not solve the problem, please find the port patch that suits you according to [Intel iGPU Patching](https://dortania.github.io/OpenCore-Post-Install/gpu-patching/intel-patching/#terminology))
- Auido (internal speaker, headphone jack)
    - Monitor volume adjustment requires the use of other software
        - [**MonitorControl**](https://github.com/MonitorControl/MonitorControl)
- LAN, WLAN & BT
- DRM

## Not Working

---

- Sleep/Wake

## Note

---

Get your own [SMBIOS](https://github.com/corpnewt/GenSMBIOS) and fill in config.plist-platform.

## Credits

---

Thanks to the authors of the linked content.
Thanks to everyone in the Hackintosh community.