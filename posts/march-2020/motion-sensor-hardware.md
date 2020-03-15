---
title: Wiring up a motion sensor
description: In which your intrepid adventurer hooks up a remote motion sensor and camera
date: 2020-03-15
tags:
  - nuts-and-bolts
  - hardware
  - sensors
layout: layouts/post.njk
---

# Wiring up a motion sensing camera
From the start, I've wanted to have a motion sensing camera by the front door to provide a layer of security when we're not at the trailer. I'd already prototyped one with a Pi Zero -- that was my first Pi project -- so it seemed like a good place to start here, too. 

First I'd need to drill two holes, one each for the PIR sensor and one for the camera. This hurt a bit, since I had already filled dozens of holes in the fiberglass since I got the trailer, but I figured I'd filled so many, what's a couple more if I should want to take it out or move it later.

I began by marking it out in an old Tic-Tac container, which I initially planned to use as a box (and still might).

   <img src="/img/mar-2020/template.png" alt="tic-tac template" />

Then I transferred the hole pattern over to a piece of paper so I could mark the holes to drill.

   <img src="/img/mar-2020/template-2.png" alt="paper template" />

A [step drill bit](https://amzn.to/2Ucun8J) really helps for these sorts of things, and it made short order of making a couple of accurately sized holes.

   <img src="/img/mar-2020/holes.png" alt="holes" />

You can see the PIR in place there. The holes are much better aligned than they appear in that photo, and the trailer is much less dingy. Some days I wish I was a better photographer.

   <img src="/img/mar-2020/putty.png" alt="butyl tape to hold the PIR in place" />

Inside the closet, I continued to ignore the long-unpainted fiberglass (you can't see it anyway) and used a bit of [butyl tape](https://amzn.to/2WgVp1m) to hold the PIR sensor in place. Butyl tape is amazing stuff. If you have an travel trailer, you really should have some on hand. It's amazingly handy.

To get from the camera and sensor at the top of closet to the Pi, which lives in a box at the bottom, I had to pick up a [two-meter Pi camera ribbon cable](https://amzn.to/2Wi8lnl) and splice in a lot of extra wire to run from the PIR sensor to the GPIO pins.

   <img src="/img/mar-2020/splice.png" alt="butyl tape to hold the PIR in place" />

With the extra wire and long ribbon cable in place, I simply used some white tape to keep it held safely in an existing sort-of channel at the side of the door.

Using a Dremel cut-off wheel, I cut a groove in the bottom of my project box and fed the wires in. I'll used some more butyl tape to seal that back up and keep dust and moisture out.

   <img src="/img/mar-2020/box-wiring.png" alt="Almost wired up" />

From there, it was just a matter of hooking up the ribbon cable and the PIR. The ribbon cable is well documented, but I unfortunately lost the docs from when I last made motion-sensing camera. Still, there are only three pins. One of them goes to a 5v pin on the GPIO, one goes to ground, and the center output pin, in my case, goes to pin 7. That's where the code expects it to be. So, fingers crossed, that will work. 

## Testing the hardware
With both the camera and the PIR motion sensor finally wired in, I wanted to check to see if it worked before going further.

When I SSH into the Pi, I _should_ be able to run `raspistill -o testshot.jpg` from the command line. But since this was a fresh Pi, I understandably got a `Camera is not enabled in this build` error. I needed to `sudo raspi-config` and turn it on.

But after doing that, I got `Camera is not detected. Please check carefully the camera module is installed correctly.` Uh-oh. Time to go check the wiring. I _always_ insert that ribbon cable backwards. [Rasperrypi.org tries to make it idiot-proof](https://projects.raspberrypi.org/en/projects/getting-started-with-picamera/2) but apparently I am a special kind of idiot.

Double-check all connections and `raspistill -o testshot.jpg` is running correct. So far, so good. But what about the motion sensor? I don't think I can check that natively with the Pi, so it's time to write some software.