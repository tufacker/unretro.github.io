Building a RetroPie

* [https://howchoo.com/g/n2qyzdk5zdm/build-your-own-raspberry-pi-retro-gaming-rig](https://howchoo.com/g/n2qyzdk5zdm/build-your-own-raspberry-pi-retro-gaming-rig)

DOSBox

* [http://dosonthepi.blogspot.co.uk/2015/01/run-dos-games-in-retropie_15.html#add-dosgames](http://dosonthepi.blogspot.co.uk/2015/01/run-dos-games-in-retropie_15.html#add-dosgames)

Installing Handbrake for RPI2/3

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install gdebi-core
wget http://steinerdatenbank.de/software/ghb_0.10.5-1_armhf.deb
sudo gdebi ghb_0.10.5-1_armhf.deb
```

Converting MAME videos to something ES can play via OMX

```
for f in *.mp4;do HandBrakeCLI -e x264 -B 64 -r 25 --gain -20.0 -X 320 -q 20 -i "$f" -o "./converted/$f";done
```

### Links

Pre-made PI Images: [https://www.arcadepunks.com/pi-images-downloads-page-latest-first/](https://www.arcadepunks.com/pi-images-downloads-page-latest-first/)

* [https://howchoo.com/g/n2qyzdk5zdm/build-your-own-raspberry-pi-retro-gaming-rig](https://howchoo.com/g/n2qyzdk5zdm/build-your-own-raspberry-pi-retro-gaming-rig)
* [https://github.com/retropie/retropie-setup/wiki/X-Arcade](https://github.com/retropie/retropie-setup/wiki/X-Arcade)
* [http://dosonthepi.blogspot.co.uk/2015/01/run-dos-games-in-retropie_15.html#add-dosgames](http://dosonthepi.blogspot.co.uk/2015/01/run-dos-games-in-retropie_15.html#add-dosgames)
* [https://www.maketecheasier.com/emulate-crt-displays-with-retropie-shaders/](https://www.maketecheasier.com/emulate-crt-displays-with-retropie-shaders/)
* [http://www.doperoms.com/roms/dos](http://www.doperoms.com/roms/dos)
* [http://www.arcadepunks.com/retro-pi-downloads-page/](http://www.arcadepunks.com/retro-pi-downloads-page/)
* [https://retropie.org.uk/forum/topic/13095/controllers-order-how-swap/8](https://retropie.org.uk/forum/topic/13095/controllers-order-how-swap/8)
* [https://github.com/meleu/RetroPie-joystick-selection/#installation](https://github.com/meleu/RetroPie-joystick-selection/#installation)
* [https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=36564&p=487878&hilit=retrobit#p487878](https://www.raspberrypi.org/forums/viewtopic.php?f=78&t=36564&p=487878&hilit=retrobit#p487878)
* [https://retropie.org.uk/forum/topic/5275/list-of-working-usb-adapters-for-original-console-controllers/2](https://retropie.org.uk/forum/topic/5275/list-of-working-usb-adapters-for-original-console-controllers/2)
* [attractmode.org](http://attractmode.org/) - Front end for cabinets, spinner style - looks awesome
* [retropie.org.uk](https://retropie.org.uk/forum/topic/776/improving-the-atari-800-5200-install/12) - Atari 5200/8-Bit thread of relevance

Edit

### ROM Sets

* [EMUPARADISE](https://www.emuparadise.me/Complete_ROM_Sets_(Full_Sets_in_One_File)_ROMs/List-All-Titles/37) - All full romsets on one page
* [ROM Shepherd](http://romshepherd.com/index.php/topic,4376.msg66484.html#msg66484) - s4nQy29A's No-Intro uploads
* [Doperoms](http://www.doperoms.com/) - Epic collection of ROMs