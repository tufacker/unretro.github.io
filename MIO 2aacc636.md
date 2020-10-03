* [AtariAge](http://atariage.com/forums/topic/254512-icd-mio-and-acard-aec-7720u-with-375-firmware/) - ICD MIO and Acard AEC-7720u with 3.75 Firmware
* [http://atariage.com/forums/topic/141914-new-drives-for-mio/](http://atariage.com/forums/topic/141914-new-drives-for-mio/)
* [https://sourceforge.net/projects/u1mbrombuilder/](https://sourceforge.net/projects/u1mbrombuilder/)
* [http://atari8warez.com/manuals/U1MB%20130XE%20Installation.pdf](http://atari8warez.com/manuals/U1MB%20130XE%20Installation.pdf)

```
Note: Setup of Compact Flash for Black Box (or MIO) with ACARD Adapter

Date: May, 2008 updated December 2010

I used the geometry data from the Sandisk CF card to plug into the Controller List Page. 
In my case it is 

I.D. A
Type SCSI
Unit, LUN 0,0
Heads 0 (which means 16)
Cyl. 993
Step 07
SecSize 512

Then on the Partition List:
1 A is "SANDISK01" (my name for this partition) and it is assigned as D1:.
I have only assigned one partition, but the BB allows up to 99 (IIRC) partitions of user-selectable sizes. But one suggestion -- make all partitions the same number of sectors. I use 60000 -- then I never have to remember differing partition sizes to tell MyDos.

Power:
The Acard adapter supplies power sufficient for a compact flash, so connect +5VDC to the Acard adapter only.    Mine is powered from the power and ground pins on the BB.  Important: when powering up, the Acard requires several seconds to run it’s internal diagnostics and to wait for a drive to “spin up.”.  The “busy” light will flicker briefly when the checks are complete.  So do not falsely “give up” thinking that something is amiss during this pre-boot period.  


Order of Powering Up:

1) Make all connections of Atari to BB, CF adapter to Acard, Acard to BB.

2) Power the Acard.  The small activity LED from the CF adapter will light.  When the light goes off, then the Acard has sensed the CF media and is ready.  

3) Then power up the Black Box (or MIO).

4) Finally, boot the Atari

For the MIO, powering up is the same, but the media/disk setup is easier -- the MIO hardware will determine the geometry.  All that must be done is to provide the sectors and sector size used for the drive(s).
```

```
˚0,70
      Some Notes on using Hard Drive(s) with MIO                
                             Russ Gilbert

These notes cannot/do not replace the MIO owner's manual. It is
intended to give some helpful hints that the owner manual may leave a
bit unclear.

The MIO can only use hard drives with 256 byte sectors. These would be
only the older MFM, RLL and SCSI hard drives, probably less than 100
megs in size.

For MFM and RLL hard drives, a SCSI to MFM or SCSI to RLL
adapter/controller must be used. The most common is the Adaptec 4000A,
aka ACB-4000A controller, used with a Seagate ST225 20 meg hard drive.
Any 256 byte/sector mfm hard drive can be used with the MIO and 4000A,
however. The RLL Adaptec controller is the ACB-4070. I don't think
using RLL drives with the 4000A or a MFM with a 4070 is a good idea.
256 byte/sector SCSI hard drives exist, such as the Seagate ST225N.
SCSI hard drives have the controller built into them, so no 'in
between' controller is needed.

SCSI uses a convention of ID number and Logical Unit Number (LUN). It
seems the ID number is always 0 for a setup with a single controller.
ie. the ID number identifies the controller number. I suppose you can
somehow daisy chain controllers. You'd have to daisy chain controllers
if you used two SCSI drives, which would have two separate controllers
(remember the SCSI has built in controllers).

The LUN is the physical drive number. You must set a jumper on the
drive itself to indicate which drive it is. 0, 1, 2, 3 etc.

So, drive 1 on the controller is ID 0, LUN 0. Drive 2, attached to the
same controller would be ID 0, LUN 1.

The MIO also can use SASI drives. I have no idea what these are.

Ok, now to my notes on specifics of setting up.

I. THE CABLES. POWER SUPPLY AND JUMPER SETTINGS:

Keep your cables short. No more than about one foot in length is
probably best. Any pc power supply can be used that has the 'standard'
four hole 'D' shaped power plugs. Newer power supplies may not have
the correct plug, or an adapter may be needed. The power requirements
of the controller and HDs should be carefully determined, and matching
power given to them.

There must always be a drive 0. If more than one drive is to be used,
the termination resistor, somewhere on the hard drive itself, must be
removed. Only the last drive MUST have this termination resistor and
no other drives can have it, as I understand. There are no termination
resistors on the cables themselves (the MIO documentation seems to
indicate there should be.)  Sometimes the termination resistor isn't
where you can get at it, it is inside the drive someplace. Possibly a
drive like this would have to be the last drive.

Set the jumper which selects the drive number. The first one for drive
one. These jumpers can often be identified by searching for drive
information from the drive manufacturer on the www (eg.
www.seagate.com).

A fifty pin ribbon cable connects to the MIO. The red 'line' on the
cable is wire #1 and goes to pin 1. Pin one is at the top back of the
MIO. It is possible to put this ribbon on backwards. With the pin type
headers, great care and patience should be taken to line up the holes
and pins and gently push the cable connector on the pins. Removing the
connector should be done slowly, probably prying with a small screw
driver, first one side then the other. It is VERY easy to bend and
break the head pins, great care must be taken installing and removing
the cables.

For MFM and RLL drives, there is a 34 pin and a 20 pin ribbon cable to
the drives, coming from the adapter.  The 34 pin can be daisy chained.
Each drive gets a separate 20 pin ribbon. The J0 on the 4000A is for
drive 1 and J1 is for drive 2. Be sure the 20 pin connections and the
jumper settings on the HD match. And be certain of the pin 1s on your
connections. More than one connection can be done backwards. The slot
connectors with a notch are nice because you can't put them on
backwards.

II. WITH CONNECTIONS MADE, YOU ARE READY TO POWER UP:

The sequence is first hds, then MIO and finally computer.
The hard drive lights should blink a few times and the controller
light should blink a few times, then all hd and controller lights
should go out (if they don't, something is wrong with your setup or
hardware). With lights out on the hd and controller, turn on the MIO.

Finally turn on the computer. Hold SELECT and hit RESET to enter the
MIO menu.  Select 'T' for drive type, and hit 'N' to select the number
of the drive you want the hd partition to be. The MIO menu determines
a hd partition. A partition cannot be larger than 16 megs. You can
partition a single hd to be more than one 'Drive #' in order to use
more of the hard drive over 16 megs.

I'm only going to describe a single hard drive setup. If you
understand this, you can add another one.  

Say the hard drive is a 20 meg. You want a 16 meg partition and a 4
meg partition. You select, say, drive # 3 to be a Hard drive. I forget
when you hit SPACE and when you hit ENTER, but you go thru the
interface, ID, LUN, Cylinders (Drive size is automatically computed),
Heads, Start Sector and End+1 sector. For a 16 meg partition, the
start sector should be 1 and the End+1 sector 65536. The number of
cylinders and heads you have to know from the hard drive
manufacturer. Often, this is printed on the hd.  For a second
partition on the same physical hd, you would start with sector 65536
and end with the about 81180 (for 20 meg drive).

Ok, you can't save the configuration yet, the hd hasn't been low level
formatted. For this use the hdfmtph6.com on the MIO disk you got. I
had best, actually only, success with hdfmtph6. Other hds may do
better with one of the other hdfmtphX, but hdfmtph6 worked best for
me.  You will be asked the ID, LUN you want to format. 0, 0 for the
first partition.  Then you'll be asked what type of controller you
have. Finally you'll be asked 'buffered' or 'unbuffered'.  You might
get a hint from hard drive tech specs on this, but 'Buffered' worked
best for me for a ST225 and Olivetti XM 5220/2.

The behavior of hdfmtph6 isn't very friendly, it doesn't let you know
if it is hung or what is going on.  Normally you begin the low level
format and the hd light comes on for some time.  Then the screen shows
verifying blocks and the # of blocks to verify.  If an error occurs,
the whole process starts over. If lots and lots of errors occur, there
is probably something wrong with your setup. Also, if the initial
stage, before the verify, takes longer than, say, five minutes,
something is wrong. I waited an hour once, I think. Everything could
burn up, or something, the program just keeps going, saying nothing.

A successful completion of hdfmtph6 will tell you success and tell you
also the number of sectors on the hd. Write this down, as it is the
last sector you can use for partitioning in the MIO menu.

Finally, you go into the MIO menu, save the configuration and then run
hdfmtdir.com to put the Atari Directory structure on the hd.   
All above is with SpartaDOS. MyDOS may have some differences, and,
actually I suggest using MyDOS with the Black Box and SpartaDOS with
the MIO.

Copy DOS (say x32d.dos) to the hd, type 'boot x32d.dos' and now you
can boot from the hd.  The MIO configuration will load from the hd
when you do a power up sequence. Other than the first time, you can
leave the MIO on all the time. Just be sure the hd is up to speed and
finished initializing before turning on the computer.

Russ Gilbert
April 19, 1998
russg@en.com
or 
cb541@cleveland.freenet.edu

```