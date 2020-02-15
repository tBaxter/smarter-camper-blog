---
title: Test fitting
description: In which your intrepid adventurer test fits the Pi and related components into the trailer
date: 2020-02-15
tags:
  - hardware
layout: layouts/post.njk
---

# Test fitting the Pi into the trailer
When [I built the project box](/posts/feb-2020/project-box/) we made an attempt at wiring everything into the trailer, only to be met with nothing. No boot, no nothing. 

Testing the supply wires indicated just a hair under 12V, which seemed like it should be enough, but nothing was working. Was my [12V-5V stepdown converter](https://amzn.to/2OKVRAb) working OK? How do you test a USB output with a multimeter? 

Beats me. I took the easy route and picked up a [cheap USB voltage tester](https://amzn.to/38rxkrI), plugged the 12V-5v converter into it and got -- nothing.

OK, so let's plug it into the [voltmeter/USB charger](https://amzn.to/39zS14X) I'd picked up previously. It showed 13.5v, so maybe I just had a voltage drop problem? Sure enough, the USB tester worked perfectly there, and patching into those 12v supply wires indicated the converter was working too. So maybe it was a voltage drop problem.

But wait a minute... checking the wires that were running to the trailer closet, where I intended to install the Pi, I'm seeing less than 12V, *even near the power supply*. Something is wrong here.

So checking the lines coming from the power supply, it looks like I had hooked into the wrong one out of two possible supply lines. Flip them around and now I'm seeing 13 volts again, even all the way over by the closet. Now we're getting somewhere, and there's no voltage drop problem after all.

After test fitting everything, I was still seeing a clean 5v coming out of the converter. This is progress So -- fingers crossed -- I plugged in the Pi. Success!