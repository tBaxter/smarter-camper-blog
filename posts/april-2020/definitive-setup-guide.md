---
title: My definitive guide to setting up a Pi from scratch
description: In which your intrepid adventurer attempts to document all the setup steps to make a Pi Smart Camper-ready (updated as needed).
date: 2020-04-21
mod_date: 2020-04-21
tags:
  - pi
  - software
  - setup
layout: layouts/post.njk
---

### Setting up the Pi from scratch
There are a million and two ways to set up a Pi, but here are the steps I think need to be done every time to set up a Pi from scratch to work well as a Smart Camper media and information hub (recorded here for my own future reference as much as anything).

These steps may also be useful for other Pis acting as similar hubs, such as Magic Mirrors or car-puters.


### First, get an OS on the Pi
1. Use [Raspberry Pi Imager](https://www.raspberrypi.org/blog/raspberry-pi-imager-imaging-utility/) to install Raspbian on a good-quality, 32GB SD card. It's a wonderfully simple solution. I continue to debate using Raspian-lite and forgo the GUI in favor of more power for Plex. But for now, I keep it.
2. Put the new card in the Pi and boot up. Assuming it starts OK, go through the first-run setup steps.
3. Set a good password.
4. [Be sure to enable SSH](https://pimylifeup.com/raspberry-pi-ssh/#enablesshdesktop)
5. And [set a static IP](https://pimylifeup.com/raspberry-pi-static-ip-address/). You'll be glad you did and aren't chasing ever-changing IP addresses set by your router. Note that your ISP and router may require additional work to make this happen.

### Install Plex
1. Ensure the external drive containing the media library [is mounted and will mount automatically](https://pimylifeup.com/raspberry-pi-mount-usb-drive/).
2. [Follow the steps to prep for Plex server installation](https://pimylifeup.com/raspberry-pi-plex-server/):```sudo apt-get install apt-transport-https
curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -
echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list
deb https://downloads.plex.tv/repo/deb public main```
3. Update packages: `sudo apt-get update`.
4. Now get the Plex server: `sudo apt-get install plexmediaserver`
5. And upgrade: `sudo apt-get upgrade`. In the past I've cleaned up some unneeded packages, but honestly, it's probably not worth it. They're not hurting anything, really.

### Pi Configuration and further installations
1. Reset the resolution to 1440x900 (at 1920 it's too fine for fat fingers)
2. Enable 1-wire interfacing, either through the `raspi-config` "interfacing" option or by manually editing the config.
3. [Install xscreensaver](https://www.raspberrypi.org/documentation/configuration/screensaver.md). It's by far the easiest way to control when the Pi and display go to sleep.
4. Follow [my own instructions to re-install the web server and monitoring page](/posts/march-2020/local-web-server/)
