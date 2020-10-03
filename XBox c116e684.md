## Orignal XBOX

### Homebrew

* [Digiex](http://digiex.net/downloads/download-center-2-0/xbox-original-content/) - Forum full of links to homebrew apps including emulators, apps and original content DLC

### Soft Modding

* [xbox-scene](http://forums.xbox-scene.com/index.php?/topic/650961-duplicating-kingroachs-ndure-script-effects-with-xplorer360/) - Duplicating Kingroach's Ndure Script Effects With Xplorer360
* [xbox-scene](http://forums.xbox-scene.com/index.php?/topic/690646-xboxhdm-22-usb-edition/) - XboxHDM 2.2 (USB Edition)
* [racketBOY](http://www.racketboy.com/forum/viewtopic.php?f=25&t=32505) - A more recent thread explaining a variety of methods.
* [Instructables](http://www.instructables.com/id/How-to-softmod-your-xbox...for-FREE/) - How to softmod your xbox…for FREE!
* [xbox-scene](http://forums.xbox-scene.com/index.php?/topic/332179-the-art-of-hotswapping/page-22) - The Art of Hotswapping…not much of an art but it gets interesting around page 22.
* [Chimp](http://theisozone.com/tutorials/xbox/hardware-and-modding/how-to-upgrade-your-hdd-using-chimp-on-a-v16-xbox/) - Allows you to swap for a larger hard drive using just the Xbox itself and a screwdriver. This is not a soft-mod however, and you'll still need to do that using a different method.

### Hard Drives

SATA to IDE adapter thread: [http://www.xbmc4xbox.org.uk/forum/viewtopic.php?f=13&t=612&start=140](http://www.xbmc4xbox.org.uk/forum/viewtopic.php?f=13&t=612&start=140)\
Hard drive compatibility list: [http://xboxdrives.x-pec.com/?p=list](http://xboxdrives.x-pec.com/?p=list)\
2TB HD Tutorial: [http://www.xbmc4xbox.org.uk/forum/viewtopic.php?f=14&t=649#p5593](http://www.xbmc4xbox.org.uk/forum/viewtopic.php?f=14&t=649#p5593)\

Edit

### CoinOPS

* [coinops.vision](http://coinops.vision/) - Quick access list for CoinOPS and Vision (Premium) packs

```
Section 1: Softmod the Xbox

https://www.youtube.com/watch?v=pMkRAlMlFJU

- Xbox: Update Xbox live to 5960
    - Check your dash version
        - Settings > Info > Needs to be 1.00.5960.01
    - Get an Xbox live compatible title: List the titles
    - Let the Xbox live game update dash to 5960
    - Confirm 5960 update
- Xbox: Prepare the thumb drive
    - Using the USB cable (source), attach a compatible thumb drive to 2nd port (provide list)
    - XBOX > Memory > Select “Controller 2"
        - Hit A again to select “Memory Unit 2A"
        - Select “Erase” and “Yes” to format the thumb drive
- PC: Copy exploit to thumb drive
    - I needed Virtualbox
        - Get XP here (works for 10): http://www.fixedbyvonnie.com/2014/03/legally-install-windows-xp-free-windows-8-using-virtualbox/
        - Networking fix here: http://www.hecticgeek.com/2016/02/enable-internet-windows-xp-virtualbox/
        - Repair DLL here: http://www.addictivetips.com/windows-tips/fix-msvcp71-dll-and-msvcr71-dll-missing-error-in-windows-7/
        - Ensure Xplorer360 and the Ndure SC directory are in the shared drive (you created in the networking step above) before continuing so you’ll have access to them in XP
    - PC/VB: Unzip XBOX Krayzie Ndure pack2 file using jZIP (or similar)
    - Attach thumb drive to PC, choose not to format it when Windows asks
    - Open Xplorer360
        - Click Drive > Open > Hard card or disk
    - Find the game exploits in the Ndure Pack directory (SC directory for Splinter Cell)
        - Open the SC save 2 folder, then UDATA
    - Copy the two files to Partition 0 in Xplorer360 (drag directly to Partition 0)
    - Reopen hard card to verify files written to thumb drive
- Xbox: Install exploit on Xbox
    - Delete existing game saves in the Xbox memory manager
    - Plug in the USB drive
    - Memory > Controller 2
    - Scroll down to Linux Installer
        - Click to the right to select the smaller icon, hit A, copy, copy to HD
    - B back to menu, scroll down to Splinter Cell and copy the same way
    - Once complete, insert Splinter Cell disc
- Xbox: Splinter Cell hack
    - Once the game launces
        - Main Menu > Start game
        - Profiles > Linux
        - Load Check Point > Check Points
    - You’ll be dropped to a new menu and are ready to install the softmod
- Xbox: Softmod the Xbox
    - Backup eprom
    - Install Ndure Softmod
    - Choose nkpatcher.67 for large HDs
    - Choose a dashboard (I used UleashX)
    - Activate shadow C
    - Backup eprom bin externally

Section 2: Install a bigger drive in the Xbox

- Need network and FTP enabled and tested before continuing
- Disassemble the Xbox
- Use a molex splitter to connect your old HD and new HD to Xbox power
- Place new hard drive on top of DVD
- Power up the Xbox, connect to it via FTP
- Download Chimp: http://www.theisozone.com/downloads/xbox/tools/chimp-26/
- FTP the Chimp2618 directory which contains the 4 files to the E:\apps folder
- Copy the LINUXBOOT.CFG file to the E:\ directory
- Refresh the apps list on the Xbox (or reboot), verify Chimp is present
- Run Chimp by running LPARTX
    - Choose option 1 to verify the drives
    - Choose option 2 to clone the drives
        - Select whole disk copy (use the thumbstick to select)
        - Select fastest mode
        - Commence the cloning
    - Choose option 3 to lock slave drive
        - Choose lock from motherboard
    - Choose option 5 to display slave status
        - Security enabled: YES
        - Security level: HIGH
- Replace stock drive with new drive and test
- Reassemble Xbox

Section 3: Install CoinOps
```

[krayzie_ndure_pack.zip](http://www.unretro.com/lib/exe/fetch.php?media=gaming:krayzie_ndure_pack.zip)\
[xplorer360.zip](http://www.unretro.com/lib/exe/fetch.php?media=gaming:xplorer360.zip)\
[chimp2618.zip](http://www.unretro.com/lib/exe/fetch.php?media=gaming:chimp2618.zip)\
[msvcp71.dll-and-msvcr71.dll-files.zip](http://www.unretro.com/lib/exe/fetch.php?media=gaming:msvcp71.dll-and-msvcr71.dll-files.zip)\

```
CoinOPS massive 7 & 8 was very slow to start games for me (Waited a good 40 seconds for games to load while on the black screen). This fixed it for me:

From http://CoinOPS.vision/readme_coinops.html

Q - My Games take so long to boot?
A - The XBOX saves all info about roms when you launch a game some Hardrives struggle to do this well.
You can disable the saving of info to speed this up in the advanced settings "Disable Info Tracking For Slow Game Loading"
```