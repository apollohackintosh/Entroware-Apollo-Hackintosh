# Entroware Apollo Hackintosh

![apollo-r3-open_front_right](https://github.com/apollohackintosh/Entroware-Apollo-Big-Sur/assets/9867529/f14e5e87-6f5e-4473-8c9e-34be3d6b4405)

This is a project I started myself since I have been using the entroware apollo laptop since last year and it is a phenomenal machine. I wanted to really push the hardware and at present I have quad boot set up with Mac OS as well. I have the Whikeylake version of the laptop but the newer ones with the 10th gen chips can be purchased in the following link:

https://www.entroware.com/store/

## My hardware is as follows:

- [x] Motherboard: Apollo Entroware - InsydeH20 Bios 1.07.02TPCS
- [x] Chipset: Intel(R) Core(TM) i7-8586U CPU @ 1.80Ghz
- [x] Graphics: Intel UHD Graphics 620
- [x] DRAM Frequency: 2400 MHz
- [x] Memory Size: 32768 MB
- [x] Storage: 1tb NVME SSD, 1tb SATA SSD (Big Sur is on this one)
- [x] Setup: Quad-boot => Ubuntu, Win10, WinSer2019, Big Sur
- [x] DSDT.aml attached in the root for more details.

### Tested macOS Version

- macOS Big Sur 11.2.1

NOTE: I have kept my EFI for Mac on a separate drive where I installed Big Sur. So in the event the bootloader causes issues with other OS, I can boot from
the original EFI by selecting the drive upon boot and I would recommend this method unless you are only install MacOS and nothing else on the laptop.

#### Requirements to hackintosh:
  1. Follow the opencore guide as strictly as possible:
  https://dortania.github.io/OpenCore-Install-Guide/
  2. Builds depend on the chipset and general hardware you have
  3. My EFI has the necessary kexts and SSDTs for this particular laptop with the i7-8565U generation which is whiskey lake, newer models will have a slightly different set up
  4. Any questions then respond on the following threads:
    https://www.reddit.com/r/hackintosh/comments/kecoih/entroware_apollo_catalina_compatible/
    https://www.tonymacx86.com/threads/entroware-apollo-hackintosh-big-sur-battery-power-detection-issue.309093/

##### Bootloader

OpenCore 0.6.5

###### SMBIOS

MacBookPro15,4

####### Change Log

   UPDATE: 02-01-2021
   - Everything sorted out except battery and power management. I am using SMCBatteryManager 
   kext and my battery is already on 8-bit with naming of EC so it should not require a patch
    
   UPDATE: 12-01-2021
   - Battery status seems to be working fine and discharging real-time
   - Seems to be discharging very quick which is a power management issue still and the charger
     is not being detected still so working to see what the issue is
    
   UPDATE 28-01-2021
   - Power Management works perfectly with the issue being the incorrect
   - GPU details so the laptop is working nicely without needlessly throttling. Now the battery and power charging most likely will be fixed by the FakeSMC_3 so will try that and upload the result.
    
   UPDATE 29-01-2021
   - USBMap.kext enabled for SDcard support. Will be uploaded in V4.0 along with other fixes for battery indicator
    
   UPDATE 14-02-2021
   - Replaced VirtualSMC with FakeSMC (2017 Version since newer ones do not work) kext
   - Replaced SMCBatteryManager with ACPIBatteryManager kext
   - Added FakePCIID kext for sensory support
   - Added undervolt kext to manage voltage and extend battery life
   - CPU management working now
   - MacOS updated to 11.2.1 and working perfectly in this set up
   - In this version, the battery management is working perfectly with all the sensors as well but unfortunately the sleep/wake functions broke with FakeSMC so will try to have that sorted out in the next release. For now this version is the pre-cursor to the final release once everything is working


