## My Definitive Arch Linux Install Guide

A lot of people when they first install Arch Linux watch YouTube videos and guides that are often outdated and incorrect.
I have created this guide and intend to update it when each new arch release comes out. That way it will be updated.

### Why use arch?
I use Arch Linux because it gives you choice on everything, even down to the smallest things like what console emulator you use.

### Ok, how do install Arch?
Unlike many other distributions, Arch Linux does not come with an GUI and installer. Instead, they give you the essentials, namely internet utilities, disk utilities, and a package manager called pacman and let you do the rest.

### Disclaimer:
*Arch linux is great, and it is very fun to use. But because you have the ability to change ***anything***, emphasis on ***anything***, you can damage your system*

*This guide is for **educational purposes only** and **I am not responsible for any damage to hardware or loss of information!***

### First Steps.
The first thing you wan to do is download the latest ISO from [here](https://archlinux.org/download/). Scroll down to HTTP Direct Downloads and click one of the links relative to your country, using one from your country is just for faster download speed.
Then, assuming you have windows installed currently, go to [rufus.ie](https://rufus.ie) and download Rufus.
Once rufus is open, your screen should have this:

![Alt](https://rufus.ie/pics/rufus_en.png)

Click on device and select your USB drive, then click select and locate your downloaded Arch ISO file. Hit select and Rufus will do the hard work for you, partitioning the drive and copying the ISO image to it.
Now restart your computer and depending on your BIOS or Manufacturer, you will have to change the boot order to have you USB at the top, and disable secure boot.
### Installing Arch.
When arch boots for the first time, you will be greeted with this screen: ![Alt](https://itsfoss.com/wp-content/uploads/2022/05/Arch-Linux-Boot-Screen-800x611.png)

Just hit enter and it will boot to the main interface.

### Internet.
First you want to get internet access. 
If you have ethernet available, use it. WIFI is a pain in the ass to get working so its best to stick to ethernet until you get into a Desktop Environment.

If however you only have access to WIFI then I will do my best to help you use it.
First run:
`rfkill unblock all`

This should enable any WIFI chipsets, if this doesn't work, check that your WIFI card is supported and try again.
Then, run:
`iwctl`

Then:
`device list`

Then:
`station (your wifi card, typically wlan0) scan`

Then:
`station (your card again) get-networks`

Finally:
`station (your card again) connect (wifi network)`

If you have a password for WIFI it will ask for it, otherwise you should be good to go.
Type:
`exit`

To leave iwctl.

You can verify internet connection by pinging a site:
`ping google.com`

If you get responses, you are set, otherwise, check internet connection and try again.

### System Clock
Now type:
`timedatectl set-ntp true`

To setup the time
### Actually Installing (Finally!)
The easiest way to install arch is by using a utility called ArchInstall
It comes pre packaged in the live medium and simplifies the install process greatly.
To use it, type:
`archinstall`

It will guide you through:
1.  configure the  [locale](https://wiki.archlinux.org/title/Locale "Locale");
2.  select the  [mirrors](https://wiki.archlinux.org/title/Mirrors "Mirrors");
3.  [partition](https://wiki.archlinux.org/title/Partition "Partition")  the disks (use ext4);
4.  [format](https://wiki.archlinux.org/title/Format "Format")  the partitions;
5.  enable  [disk encryption](https://wiki.archlinux.org/title/Disk_encryption "Disk encryption")  (optional);
6.  set the  [hostname](https://wiki.archlinux.org/title/Hostname "Hostname");
7.  set the root password;
8.  install a  [boot loader](https://wiki.archlinux.org/title/Boot_loader "Boot loader")  (limited to  [systemd-boot](https://wiki.archlinux.org/title/Systemd-boot "Systemd-boot")  for UEFI and  [GRUB](https://wiki.archlinux.org/title/GRUB "GRUB")  for BIOS).

When you have finished setting it up through archinstall, you will have a basic budgie install and are ready to go!

Author: **Kabeeki**
