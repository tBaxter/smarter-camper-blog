---
title: Introducing the touchscreen
description: In which your intrepid adventurer adds a 15-inch-touchscreen.
date: 2020-03-24
tags:
  - hardware
  - nuts-and-bolts
layout: layouts/post.njk
---

# Adding a touchscreen monitor
You can't really have an entertainment center without a nice screen to watch your movies on. I was long overdue adding one, for a lot of reasons.

From the start, I knew I wanted 

Initially I planned to use an old first-generation iPad I had laying around as the screen. Cost was zero, since I already had the iPad (and a first-generation iPad has nearly no value anymore). And I did manage to connect it up to the Pi and show the screen. Which felt like a win.

On the other hand, it had to connect over the network via VNC. Coupled with it being a very old iPad, that made it painfully slow. At 11 inches or so, it was also too small to comfortably watch anything on from any distance away, and since it was connecting over a network it required a network I might not have. 

It wasn't _really_ interfacing with the Pi, either. It was still running IOS, so my touchscreen abilities were kind of limited.

And on top of all that, mounting it in the door was going to tax my meager woodworking skills.

So with that experiment set aside, I got thinking about the touchscreen I really wanted.

* Bigger, but not too big. I need it to be small enough to mount on the closet door, but easily viewable from the bed.
* Standard VESA mounts for simple installation.
* Powered by 12v or less. I'm not running 110v for this thing. 
* Very thin and lightweight. Since it's mounted on the closet door, the closer to a flush mount the better.
* Simple, direct interface with the Pi.

After digging around a bit I landed on this [15.6" USB-powered touchscreen](https://amzn.to/2JaG7n5) which appeared to check every box.

Connecting it to the Pi was pretty straightforward and the monitor was mostly plug-and-play.
<img src="/img/mar-2020/monitor.png" alt="monitor" />

There was one wrinkle though: while the monitor is USB-powered, and promised to support both touch and video over a single cable, I learned a Raspberry Pi 4 does *not* support video over USB. Which means I'd need an HDMI cable. Which in turn means my closet door mounting got a bit more complicated. And ugly.

Worse yet, in the interests of making a very thin (about 3/8" thick) monitor, all the plugs come out the side. Having two cords poking a couple of inches out of the side of this thing is not the look I'm going for.

The hole in the door also had to get much bigger in order to accomodate the relatively ginormous HDMI cable.

I bought a [right-angle HDMI cord](https://amzn.to/3dqFhAw) which helped some, but it's still a very large, bulky head. Ideally, something much more low-profile (and right angle) would be better, but it was the best I could do.

I'm hoping when I couple that with a [low-profile USB-C cord](https://amzn.to/2UiYOLL) and a [wall cord pass-through plate](https://amzn.to/3boj3x7), I should have both the cables and my ugly mis-drilled hole nicely covered and looking tidy.

As for actually mounting the monitor, that part was pretty simple. I found a [VESA mount template](http://geldner.com/wp-content/uploads/2016/11/VESA-100mm-75mm-Template.pdf) online and taped it to the door to figure out where to drill.

<img src="/img/mar-2020/vesa-mount.png" alt="vesa mount template" />

Of course, it's hard finding anything level or square in one of these old trailers, and it was tricky accounting for where the hole for the cords needed to be. If I was doing it again I'd figure out how to put the template on a monitor-sized piece of paper, so I could get a better sense of the overall positioning of things, rather than just the mount points.

And of course I got the cord hole in the wrong spot on the first try. But not too bad. Again, a wall plate will fix it up.

And the VESA template was spot on. I used [stainless steel M4 screws with integrated washers](https://amzn.to/2QIm43i) to mount it up, and they slipped right into place. I make a point of using stainless as much as possible in the trailer. I want to avoid later corrosion problems as much as I can. 

And just like that, I had a working Pi touchscreen monitor on the closet door, and with a finger press (or two) could launch Plex and start watching a movie. 