# linux-behringer error audio stuttering (not xruns)
I buy a behringer UMC204HD and it was driving me crazy..

# OS :  Archlinux - 5.17.2-arch3-1

# #dmesg
clock source 41 is not valid, cannot use
Tested on different kernel..  distro... the same problem

Similar issue shows up with other hardware (USB DAC in general)

It is a common issue with USB DAC interfaces

# Concern ALL U-PHORIA Series 
U-PHORIA Series -  Broken linux compatibility

UM2

UMC1820

UMC202HD

UMC204HD

UMC22

UMC404


# lsusb
          Bus 001 Device 007: ID 1397:0508 BEHRINGER International GmbH UMC204HD 192k



# HOW TO FIX TEMPORARY THE BUG !

Unplug the USB interface

          sudo modprobe -r snd_usb_audio
          sudo modprobe snd_usb_audio implicit_fb=1
Plug the USB interface and test

# If the temporay fix is working, you can add rules to :

/etc/modprobe.d/UMC204HD.conf

options snd_usb_audio implicit_fb=1
