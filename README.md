# Entroware-Apollo-Hackintosh

This is a project I started myself since I have been using the entroware apollo laptop since last year and it is a phenomenal machine. I wanted to really push the hardware and at present I have quad boot set up with Mac OS as well.

A breakdown of what is needed if you do have this laptop and want to hackintosh it:
  1. Follow the opencore guide as strictly as possible:
  https://dortania.github.io/OpenCore-Install-Guide/
  2. Builds depend on the chipset and general hardware you have
  3. My EFI has the necessary kexts and SSDTs for this particular laptop with the i7-8565U generation which is whiskey lake, newer models will have a slightly different set up
  4. Any questions then respond on the following threads:
    https://www.reddit.com/r/hackintosh/comments/kecoih/entroware_apollo_catalina_compatible/
    https://www.tonymacx86.com/threads/entroware-apollo-hackintosh-big-sur-battery-power-detection-issue.309093/
    
    ******************************************************************************************
    
    UPDATE: Everything sorted out except battery and power management. I am using SMCBatteryManager 
    kext and my battery is already on 8-bit with naming of EC so it should not require a patch.
    
    UPDATE: 12-01-2021 - Battery status seems to be working fine and discharging real-time.
    Seems to be discharging very quick which is a power management issue still and the charger
    is not being detected still so working to see what the issue is.
    
    UPDATE 28-01-2021 - Power Management works perfectly with the issue being the incorrect
    GPU details so the laptop is working nicely without needlessly throttling. Now the battery and
    power charging most likely will be fixed by the FakeSMC_3 so will try that and upload the result.
