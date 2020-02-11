---
title: Details on wiring a Pi power switch
description: In which your intrepid adventurer connects a power switch
date: 2020-02-10
tags:
  - hardware
layout: layouts/post.njk
---

# Details on wiring a Pi power switch
Wiring up a Pi power switch seems like it should be the simplest thing imaginable. It is not. There's a surprising large number of things you'll need to work through. That said, it's not *that* hard once you sort through a gazillion how-to guides to find the one that makes sense. 

The key is to use a momentary switch with a resistor built in, so you're protecting the Pi. I used this [power button with LED](https://amzn.to/3bqPrQs) and have been happy with the results. 

There are nice, helpful scripts in the the [Pi Power Button repo](https://github.com/Howchoo/pi-power-button) and 
[related instructions](https://howchoo.com/g/mwnlytk3zmm/how-to-add-a-power-button-to-your-raspberry-pi), which make the scripting part pretty straightforward.

Note when you're following the instructions, the files don't have to be written -- they're in the repo. Just use `cp` to move them where you need them and be sure to `chmod` them to set the permissions.
[A simple tutorial](https://howchoo.com/g/ytzjyzy4m2e/build-a-simple-raspberry-pi-led-power-status-indicator) 
took care of the LED portion of the switch. 

One catch: because there's a power switch and an LED, you have to think through the GPIO pins a little more. I used 5 and 6 for the Power button, as outlined in the instructions, then used 8 and 14 for the LED.