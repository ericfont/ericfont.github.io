---
layout: post
title: MythTV Personal TV Recorder setup
---

[MythTV](http://mythtv.org) is a free open-source digital video recording system, easy to use with many features such as auto-scheduling recordings, and most importantly removing commercials. All you need is to install the mythtv backend program on a computer with a linux compatible TV tuner (a list of USB devices that work with the US ATSC standard is [here](http://linuxtv.org/wiki/index.php/ATSC_USB_Devices) but there are also PCI-based or Ethernet-based tuners).  I am actually using a [Mygica A680B USB HDTV Tuner](http://www.ebay.com/itm/360796376689) I bought off ebay new for $25 which works fine on linux even though they don't provide any linux drivers (it turns out it is very similar to other other devices which have linux support).  I connected this tuner to my home antenna and plugged into an ancient Dell Latitude D600 labtop from circa 2002 (60 GB, Celeron M, 1.6 GHz, 512 MB) and did a minimal Arch Linux install with LXDE which turns out to be plenty fast enough to run the backened recording server as well as the frontend player (and can output S-Video to my CRT tv):

![Alt labtop](/img/IMG_20140125_mythtv_labtop.jpg "MythTV labtop frontend/backend labtop")

Sidenote: Using an old labtop as a server is great because they are usually low power (esp if you set display to timeout) and have a built-in battery incase power is momentarily disconnected.

I soon discovered that the 60GB disk was being filled up after about a week's worth of recording (an hour of 1080p TV mpg is about 4gb or so), so I did add an extra 100GB used external usb harddrive which works fine (note 1080p video only really needs a maximum r/w speed of 2MB/sec).  The frontend is easy enough for my mom to navigate recordings, although it did take a bit of time to setup the backend properly...see the guides for installing mythtv or for easier setup try a pre-setup linux distro like [Mythbuntu](http://mythbuntu.org) which is based on the noobie-friendly Ubuntu.

Again, you don't need a fast computer to run mythTV: the backend doesn't need much CPU power as it mainly only needs to copy pre-compressed mpeg data from the Tuner to a disk and just needs to be fast enough to uncompress this mpeg and flag commercials in a reasonable amount of time (which works by looking for tell-tale fade-outs, blanks, and abrupt volume increases in the mpg). The front end can run on a seperate computer connected to the backend via LAN. I even managed to get my $25 Raspberry PI (note: the only way I could get the PI to decompress 1080p mpeg was to utilize the hardware MPEG decoder, requiring me to purchase a $2 license specific for my PI's serial number, as no amount of overclocking was sufficient).  Instead of installing a full linux distro like raspbian on my PI, I am using a much more efficient ~128mb specialized embedded build of [XBMC](http://xbmc.org) called [OpenElec](http://openelec.tv), shown connected to an old CRT tv below:

![Alt CRT](/img/IMG_20140125_RaspberryPI_CRT.jpg "XBMC running on Raspberry PI")

And since the Raspberry PI has HDMI output, it is able to output 1080p video to any HDMI screen, for example to a projector below:

![Alt Projector](/img/IMG_20140125_RaspberryPI_Projector.jpg "XBMC to projector")

There are many other ways to display the video as they are just MPG (VLC and even Windows Media Player work fine over network) although you won't get the commercial-removal feature of MythTV.  You can even play videos on your android phone with [MythTV Android frontend](https://play.google.com/store/apps/details?id=org.mythtv). Also I found some remote controls for xbmc and myth so you can just use your phone to remotely control the frontend (no need to use a wireless keyboard/mouse for controlling from your couch)!

In summary: you can setup your own personal automated TV recording system using MythTV with very little expenses, as the only necessary piece of hardware is a HDTV tuner. The rest of the hardware can be salvaged from an old computer or run as a background processes on your current machine (provided you are willing to leave it powered on all day) and all the software is open source.
