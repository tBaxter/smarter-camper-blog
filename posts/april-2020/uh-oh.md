---
title: Uh-oh
description: In which your intrepid adventurer breaks everything and learns the hard way about some quirks of the Raspberry Pi.
date: 2020-04-08
tags:
  - pi
  - software
layout: layouts/post.njk
---

# Uh-oh
I knew just unplugging the Pi wasn't a great idea and could eventually lead to SD card corruption. I knew that intermittent short in the power lines was creating hard shutdowns way more than was smart. I thought it would be OK until I got it sorted out.

I was wrong. 

Yup, I corrupted the SD card. Reformatting it didn't resolve it. It had a bad block. So let this be a lesson. 

1. Treat your card kindly, or you will corrupt it.
2. Have a backup strategy in place.
3. Don't ignore the little problems, or they will become bigger problems.

I get some small slack because the power supply issues were largely due to the installation of an amp -- more on that to come -- but still. Everything had to come to a halt while I dismantled the box, pulled the Pi out, pulled the SD card out and worked through it. 

And then I had to remember all the steps I had taken to set that card up. For future reference, I'm trying to document those steps here...

### Setting up the Pi from scratch
There are a million and two ways to do it, but here are my steps (recorded here for my own future reference as much as anything).

1. Use [Raspberry Pi Imager](https://www.raspberrypi.org/blog/raspberry-pi-imager-imaging-utility/) to install Raspbian on a good-quality, 32GB SD card. It's a wonderfully simple solution. I continue to debate using Raspian-lite and forgo the GUI in favor of more power for Plex. But for now, I keep it.
2. Put the new card in the Pi and boot up. Assuming it starts OK, go through the first-run setup steps.
3. Set a good password.
4. [Be sure to enable SSH](https://pimylifeup.com/raspberry-pi-ssh/#enablesshdesktop)
5. [Follow the steps to prep for Plex server installation](https://pimylifeup.com/raspberry-pi-plex-server/):```sudo apt-get install apt-transport-https
curl https://downloads.plex.tv/plex-keys/PlexSign.key | sudo apt-key add -
echo deb https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plexmediaserver.list
deb https://downloads.plex.tv/repo/deb public main```
6. Update packages: `sudo apt-get update`.
7. Now get the Plex server: `sudo apt-get install plexmediaserver`
8. And upgrade: `sudo apt-get upgrade`. In the past I've cleaned up some unneeded packages, but honestly, it's probably not worth it. They're not hurting anything, really.
9. Ensure the external drive [is mounted and will mount automatically](https://www.raspberrypi.org/documentation/configuration/external-storage.md).
10. Ensure Plex can read AND write to the folder the movies are in, so I can optimize them and such later. `sudo chmod 775 /mnt/Movies`
