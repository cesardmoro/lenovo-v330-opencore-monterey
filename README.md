# Lenovo v330 OpenCore 0.8.4 - Monterey

## Hardware

- Processor: Intel Core i5 8250U (Kaby Lake Refresh).
- iGPU: Intel UHD 620 Graphics. 
- RAM: 16 GB { 4 GB Soldered + 16 GB KINGSTON SODIMM DDR4 2400 MHz Socketed }.
- SSD: Kingston SA400S37/240G 240GB (Monterey)
- NVME SN350 WDS240G2G0C 240GB (Windows)
- Integrated Keyboard: PS/2 compatible.
- Touchpad: I2C Synaptics Touchpad with multi-touch.
- Wi-Fi: Intel® Wireless-AC 3165 dual band. 802.11ac 1x1, Wi-Fi + Bluetooth 4.1, M.2 Card
- Ethernet: Realtek RTL8111.
- Audio: Conexant 20672.
- Webcam: Integrated.
- BIOS: 6SCN41WW.

### I/O & integrated devices

 - 2x USB 3.0 Type A ports.
 - 1x USB 3.0 Type C port with Power Delivery and Display Port.
 - 1x VGA Output.
 - 1x HDMI Output.
 - 1x SD Card Reader.
 - 1x Ethernet port.
 - 1x Headphone jack.
 - 1x Integrated Webcam.
 - 1x Integrated microphone and speakers.

### BIOS Settings to change

 - Intel SGX:  Disabled.
 - Intel Platform Trust Technology: Disabled.
 - Boot Mode: UEFI.
 - USB Boot: Enabled.
 - PXE Boot to LAN: Disabled.
 - OS Optimized Defaults: Disabled.
 - Secure Boot: Disabled (do it after changing Boot Mode to UEFI).
 - Virtualization: Enabled (doesn't really matter).

## Software

 - macOS Monterey .app downloaded right from the App Store or anywhere else. Create a USB media from it (make sure to select GUID while formatting it in HFS+).
 - This copy of OpenCore which at the time of writing this, is the latest (v0.84).
 - Opencore configurator or ProperTree or similar to modify property list (config.plist). *(Do not autoimport kext or will stuck at boot)*
 - GenSMBIOS to get DeviceProperties for your "MacBookPro" (You must modify it in your config.plist, I suggest MacBookPro16,1 or MacBookPro15,1).
 - MountEFI to mount your device's EFI partition and copy the bootloader.
 - The latest version of all the kexts requiered for this laptop.

### Kernel Extensions

  - Airportltlwm v2.1.0 stable (Monterey).
  - AppleALC v1.7.0.
  - ECEnabler v1.0.2.
  - Lilu v1.6.0.
  - RealtekRTL8111Ethernet v2.4.2.
  - VirtualSMC v1.2.9 (With SMCBatteryManager, SMCProcessor and SMCSuperIO).
  - USBMap.
  - VoodooI2C v2.7 (With VoodooI2CHID).
  - VoodooPS2Controller v2.2.8.
  - WhateverGreen v1.5.8.

### Drivers
Taken from OpenCore v0.8.4 Debug.

- AudioDxe.efi (required only for the Boot Chime).
- HfsPlus.efi.
- OpenRuntime.efi.

### ACPI
From dortania's repository.

- SSDT-AWAC.aml.
- SSDT-EC-USBX-LAPTOP.aml.
- SSDT-PLUG-DRTNIA.aml.
- SSDT-PNLF.aml.
- SSDT-XOSI.aml.

## What works

 - Integrated display.
 - Integrated microphone and webcam.
 - VGA Output.
 - Ethernet port.
 - Wi-Fi card.
 - All the USB ports in its respective speeds.
 - Integrated Keyboard.
 - Sound (internal speakers).
 - Headphone jack (input and output).
 - CPU Power Management.
 - Sleep.
 - Battery indicator.
 - Boot Chime.

## What won't work
  - Touchpad 
  - HDMI port (It works great but the integrated display will go black. If you find a solution please let me know).
  - Bluetooth (Detected, But won't turn on)
  - Fingerprint Reader.
  - SD Card Reader (I haven't tried to make it work).
  - Function keys (I did not attempt to remap the keys).


## Credits

- [dortania](https://github.com/dortania) for the detailed installation guide and ACPI tables.
- [acidanthera](https://github.com/acidanthera) for OpenCore Bootloader and the mayority of the kexts.
- [OpenIntelWireless](https://github.com/OpenIntelWireless) for the Wi-Fi kext.
- [1Revenger1](https://github.com/1Revenger1) for the battery indicator plugin for lilu.
- [Mieze](https://github.com/Mieze) for the Ethernet kext.
- [CorpNewt](https://github.com/corpnewt) for the USBMap, GenSMBIOS, ProperTree and MountEFI tools.
- [VoodooI2C](https://github.com/VoodooI2C) for the VoodooI2C kexts.
