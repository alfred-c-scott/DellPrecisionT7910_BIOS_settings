# Dell Precision T7910 BIOS Settings and Instructions
INFO: This guide assumes that proxomox has alread been installed.

## Initial BIOS settings
1. Boot machine
2. When Dell logo appears press F12.
3. Navigate to BIOS Setup and press Enter
4. Settings -> General
    - Boot Sequence - Proxmox radio button checked
    - Boot List Option - UEFI radio button checked
    - Enable Legacy Option ROMS - unchecked
5. Settings -> System Configuration
    - SATA Operation - AHCI checked
    - SAS RAID Controller - Enabled checked
    - Memory Map IO above 4G - Memory Map IO above 4G checked

click Apply and then Exit

## Check for drives after reboot
1. After clicking Apply and then Exit from bios the machine will reboot
2. When Dell logo appears press F12
3. Navigate to BIOS and press Enter

Navigate to Settings -> System Configuration -> Drives
* SATA Drives might be present in the list of Drives at this point. If not you may need to delete any Virtual Drive settings in Device Configuration menu.
* If SATA drives do not appear do the following:
    1. Exit button at the bottom of the BIOS page, system will reboot.
    2. When Dell Logo appears press F12.
    3. Instead of going into BIOS navigate to Device Configuration.
    4. You will see the SAS3 MPT Controller and need to navigate to it and press enter.
    5. Delete any configurations under Virtual Disk Management
    6. Press F4 to save and exit.
    7. Press power button to power down the machine

## Final Verification
1. Boot machine
2. When Dell logo appears press F12
3. Navigate to BIOS and press Enter

Navigate to Settings -> System Configuration -> Drives. If everything above was done correctly you should now see the SATA drives listed here, and should be free to provision in ZFS pools in Proxmox


