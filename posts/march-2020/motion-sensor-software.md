---
title: Coding a motion sensor
description: In which your intrepid adventurer writes the code to use the remote motion sensor and camera
date: 2020-03-16
tags:
  - software
  - sensors
layout: layouts/post.njk
---

# How do we use that motion sensor and camera, anyway?
I have the [PIR sensor wired in](../motion-sensor-hardware) and have set up a [simple web app](../local-web-server) to see what's happening. Now, how do I make the sensor actually do anything so I can monitor it?

I've got the important bits in two files, both of which we pulled down in the repo for the Flask web app.

First up, in the [Flask app.py file](https://github.com/tBaxter/pi-smart-camper/blob/master/webapp/app.py) there's a lot of setup going on. 

In `index` (line 22) we're creating a lot of variables that are, by default, nothing. But if they get set later we'll be able to show the status.

The real meat of it, though, is happening down in `action` (line 59), which lets us toggle the camera off and on.

In particular, if we're turning the camera and motion detection on, we're starting it in a thread in the background, so the webapp can go ahead and continue to do its thing.

When we start the camera, we're calling `start_motion_detection` from `monitoring/motion_sensing.py`. It's really pretty simple, thanks to the `gpiozero` library.

Basically, the `start_motion_detection` function just initializes things, starting up the motion detection and configuring the camera. Then, when some movement is detected it uses a lambda to call `take_photo` and actually store a photo locally.

Currently, there's a function that would send an email, but I think I'm going to go a different route and will end up removing it.

Back in the `app.py` actions function, the second half just handles clean shutdown. If we turn the camera off, we want to be sure we cleanup on the Pi and leave everything as tidy as possible.

Either way, we redirect back to `index`, now with those variables populated so we can show what we just did.

