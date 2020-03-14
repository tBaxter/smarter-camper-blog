---
title: Troubleshooting power part 2 - The powerening
description: In which your intrepid adventurer finds still more missing electrons
date: 2020-03-14
tags:
  - nuts-and-bolts
  - restoration
layout: layouts/post.njk
---

# Troubleshooting power issues - Part 2

With the <a href="/posts/march-2020/troubleshooting-power-issues/">new power center wired in</a>I had usable electricity whenever I was hooked up to shore power. Unfortunately, as soon as I disconnected from shore power I still had no juice.

This would be a problem, especially since I planned to run the onboard Raspberry Pi in headless, always-on mode. 

So what gives? Surely I wired up something wrong. So out comes the multimeter and I begin checking everything. The power center instructions came with surprisingly good troubleshooting instructions, including multiple points at which to check the 12-volt converter, and I diligently checked every fuse.

Nothing.

In an attempt to get a better idea of what the battery was doing (and pick up some extra USB 3.0 ports in the process) I grabbed this [inexpensive voltmeter & power plug](https://amzn.to/2IJe11R) and installed it in the upper cabinet by the dinette, where I already had 12V wires handy.

Which was nice to have, but wasn't helping me understand what was going on -- it did help with the Pi install debugging though!

So finally, fresh out of ideas, I called up Progressive Dynamics. Their very friendly and helpful tech support began walking me through it again when I touched a wire from the battery and... had light!

Turns out there's a plug on those wires that run from the battery to the power center.

   <img src="/img/mar-2020/plug.png" alt="plug" />

And the contacts in that plug weren't making a good connection. A little bit of polishing and everything was fine.

   <img src="/img/mar-2020/plug-shiny.png" alt="plug cleaned up" />

The lesson, I suppose, is to check even the littlest things twice, because that solved the problem. Now that I had reliable power to the Raspberry Pi at all times, I felt like I could begin moving forward again and ordered a [15.6" touchscreen monitor](https://amzn.to/2QcVRJR).

In theory, it checks all the boxes:
* Touchscreen, so it can act as a control center 
* Large enough and high enough resolution (1920x1080) to comfortably watch movies
* Will fit on the closet door
* Single USB-C cord for power and data

We'll see when the delivery truck comes around.