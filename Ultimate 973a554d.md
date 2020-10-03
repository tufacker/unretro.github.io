### Incognito

* [http://atariage.com/forums/topic/212773-incognito-install-a-collectors-perspective/](http://atariage.com/forums/topic/212773-incognito-install-a-collectors-perspective/)

Edit

### Ultimate 1MB

* [Capacitor fix](http://atariage.com/forums/topic/224151-ultimate-1mb-in-1200xl/page-3) for U1MB that may help with BIOS resets
* Updating the CPLD (Xilinx) in the U1MB and Incognito [AtariAge](http://atariage.com/forums/topic/206610-ultimate-1mb-upgrade)
* Installing an Ultimate 1MB in an 800XL [spiflash.org](http://spiflash.org/index.php/block/26.html) [Lotharek](http://lotharek.pl/product.php?pid=67)
* Super MMU Adapter by Dropcheck for Ultimate 1MB [Bits of the Past](http://www.bitsofthepast.com/?product=super-mmu-adapter)
* [RealDOS.net](http://www.realdos.net/Ultimate%201%20Meg%20Side%202%20Cart.html) - Steven Carden's review of the U1MB + SIDE2

Quick install of Ultimate 1MB for 800XL (Candle version)

 1. Remove MMU and OS ROM
 2. If you unsoldered them to get them out, install some sockets
 3. Insert a Dropcheck [Super MMU Adapter](https://www.bitsofthepast.com/?product=super-mmu-adapter) in the MMU socket (otherwise you'll have to use the resistors) - here's the directions [Bits of the Past](http://www.bitsofthepast.com/wp-content/uploads/2013/11/Super-MMU-Adapter.pdf)
 4. Assemble a jumper cable - you'll need 4 wires \~12 inches long (you can cut them to exact length as you install) and use an XXXX molex header with some XXXX crimp things (you can also always solder directly to the Ultimate and avoid making the header - try from the bottom for a cleaner install)
 5. Using the picture to the right, solder the 4 jumper wires to your motherboard making sure they line up with the pins in the header cable you assembled - this should match the labels on the Ultimate

    ![](http://www.unretro.com/lib/exe/fetch.php?w=100&tok=851514&media=computers:ultimate_1mb_-_800_xl_-_rev._c.jpg)
 6. Plug the OS ROM cable and MMU cable into the motherboard sockets
 7. Locate your Ultimate in the upper right corner of the 800XL, hovering over the OS ROM - you'll be able to line up a standoff with the upper right corner of the board which will hold it in place perfectly with the single standoff
 8. Connect all cables to the Ultimate
 9. Insert a battery
10. Power on and test!

Ultimate JTAG and FLASH

* [http://atariage.com/forums/topic/210066-u1mb-flasher-timeout-error/?p=2863129](http://atariage.com/forums/topic/210066-u1mb-flasher-timeout-error/?p=2863129)
* [http://atariage.com/forums/topic/218746-looking-for-someone-to-flash-u1mb/#entry2880809](http://atariage.com/forums/topic/218746-looking-for-someone-to-flash-u1mb/#entry2880809)
* [http://atari8.co.uk/firmware/ultimate-1mb/](http://atari8.co.uk/firmware/ultimate-1mb/)
* [http://davejmurphy.com/xilinx_ise_14-7_labtools_on_windows_8/](http://davejmurphy.com/xilinx_ise_14-7_labtools_on_windows_8/)

Updating CPLD on early U1MB (Candle version)

* Grab the v2 JED file from Candle's site: [www.spiflash.org/atari/ultimate1mb-v2.jed](www.spiflash.org/atari/ultimate1mb-v2.jed)
* Assuming you don't have a Xilinx cable for programming, order the following:
  * Xilinx Platform Cable USB
  * Model DLC9G [Amazon](https://www.amazon.com/dp/B010NXXL2M?psc=1) [Newegg](http://www.newegg.com/Product/Product.aspx?Item=9SIA7BF37Z1762) [AliExpress](http://www.aliexpress.com/item/Platform-Cable-USB-XILINX-FPGA-CPLD-JTAG-DLC9G-in-circuit-Debugger-Programmer-XILINX-FPGA-CPLD-configuring/1443432269.html)
* You'll also need some additional cables because the U1MB uses a non-standard JTAG header. Buy yourself the following because you're going to need to make a cable (no way around it, unless you want to solder directly to the U1MB to program it):
  * [HQ 2x5 10-Pin 2.0mm IDC JTAG ISP Cable Multiple Color Ribbon Wire](https://www.amazon.com/gp/product/B00XSD9E9O)
  * [HQ 2x5 10 pins IDC Male to Female JTAG ISP Cable](https://www.amazon.com/gp/product/B01FTM4I7E)
* Create your cable. Some background on what to do here can be found on [AtariAge](http://atariage.com/forums/topic/206610-ultimate-1mb-upgrade/), but it does not specifically cover this programmer which has a different pinout configuration from the one mentioned there.
* Use my [awesome diagram](http://www.unretro.com/lib/exe/fetch.php?media=computers:img_5493_1_.jpg) for the wiring configuration for your two cables. In general you should expect to chop the two cables you purchased in half and solder them together using the diagram I've provided. This will vary on individual skillsets and preferences so I won't bother going into detail on how to properly make a cable. I will add that mine looked like Frankenstein on a bad morning and it still worked fine.
* Next you'll need a PC running Windows 7 thru 10 with USB. Be forewarned if you're running Windows 8 or 10 you'll have a few extra steps below as the Xilinx software does not yet (or ever will) support the latest Windows versions.
  * Download the Xilinx Labtools 14.7 package from [Xilinx](http://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/design-tools.html). Prepare to go through a painful registration process, but in the end this is all you'll need as it includes iMPACT, which you'll use to program the Xilinx on the U1MB. Also in my case I used 64 bit Windows 10 on a Toshiba laptop.
  * If you are running Windows 8-10, you'll need to do the following otherwise iMPACT will crash when attempting to load a ROM file:

```
1. Rename <install location>\Xilinx\14.7\LabTools\LabTools\lib\nt64\libportability.dll to libportability.dll.orig
2. Rename <install location>\Xilinx\14.7\LabTools\common\lib\nt64\libportability.dll to libportability.dll.orig
3. Copy <install location>\Xilinx\14.7\LabTools\LabTools\lib\nt64\libportabilityNOSH.dll to <install location>\Xilinx\14.7\LabTools\LabTools\lib\nt64\libportability.dll
4. Copy <install location>\Xilinx\14.7\LabTools\LabTools\lib\nt64\libportabilityNOSH.dll to <install location>\Xilinx\14.7\LabTools\common\lib\nt64\libportability.dll
```

* At this point you should have your USB Xilinx programmer, your custom made 14 pin to 10 pin JTAG cable, and a Windows machine with LabTools 14.7 installed and patched using the instructions above. It's now time to grab your U1MB and program it.

<note warning>You'll need the U1MB partially installed in your 8 bit to provide power during programming. If you haven't actually installed the U1MB then this may be an issue. My suggestion at this point is to either fully install and test the U1MB, or partially install the MMU cable (and resistors if you don't have an MMU adapter from Dropcheck) as this will fully power the U1MB during programming.</note>

* Connect your JTAG cable to the U1MB and the Xilinx programmer. Connect the USB cable from the programmer to the Windows machine. Finally, power on your 8 bit. You should see the red light turn green on the Xilinx programmer indicating proper voltage and most likely a successful cable build. Congrats on this small victory!
* Using the iMPACT software (in my case the 64 bit version), program the U1MB:
  * Launch iMPACT, and say yes when it asks to automatically create a project
  * Select Configure devices using Boundary-Scan (JTAG) from the next screen that appears, and hit ok (leave the Auto connect and identity option in the pull down alone)
  * You should see a large blue box “Identify Succeeded,” at this point right click the greek Xilinx chip icon and select Launch File Assignment Wizard
  * Navigate to your jed file and open it using the browser. If iMPACT suddenly crashed on you at this step go back and confirm the patch you made above was correct.
  * The next screen shows you programming properties, and it's fine to accept the defaults here. It should have verify and erase before programming selected.
  * Now right click the green Xilinx icon again, and select Program from the menu that appears (very top)
  * You'll see a very rewarding green progress bar as the command is executed
  * And finally you'll be rewarded with a Program Succeeded status box.
* That's it! With any luck your U1MB is now version 2. You can safely flash to the latest U1MB versions without fear of bricking!