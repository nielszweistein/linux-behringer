# linux-behringer error 

I buy a behringer UMC204HD and it wad driving me crazy... !!!

OS :  Archlinux - 5.17.2-arch3-1

if i look dmesg message error :

#dmesg
clock source 41 is not valid, cannot use

Tested on different kernel..  distro... the same problem

Similar issue shows up with other hardware (USB DAC in general)
It is a common issue with USB DAC interfaces, needing some delay between the usb interface start and the playback / bitrate/frequency...

(history patch with same problem was removed/modified recently in kernel..)
https://github.com/torvalds/linux/commit/5a4ff9ec8d6edd2ab1cfe8ce6a080d6e57cbea9a


#############################################
U-PHORIA Series -  Broken linux compatibility
-UM2
-UMC1820
-UMC202HD
-UMC204HD
-UMC22
-UMC404

lsusb
Bus 001 Device 007: ID 1397:0508 BEHRINGER International GmbH UMC204HD 192k



#####################################################
HOW TO FIX TEMPORARY THE BUG !!!

Unplug the USB interface

          sudo modprobe -r snd_usb_audio
          sudo modprobe snd_usb_audio implicit_fb=1
#####################################################


