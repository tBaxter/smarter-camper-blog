---
title: More touchscreen functionality
description: In which your intrepid adventurer creates a dashboard to monitor and control things.
date: 2020-03-24
tags:
  - software
  - web
  - interface
layout: layouts/post.njk
---

# Creating a dashboard
With the monitor now in place a lot of things are starting to come together. And I'm putting them all in a dashboard control center for the trailer.

I'm going to skip most of the gory details of the code -- [it's all available on Github](https://github.com/tBaxter/pi-smart-camper) -- and instead just talk about what it does.

The first trick is to [turn the Pi's Chromium Browser into a full-screen kiosk](https://pimylifeup.com/raspberry-pi-kiosk/), which lets us build a web page that looks and acts like a full-screen experience. 

From there, we'll use the [Flask web app we set up earlier](/posts/march-2020/local-web-server/) to both talk to the Pi's hardware and to serve the "web page" that forms the basis of our dashboard. That's made up of multiple modules (with more to come):

<img src="/img/mar-2020/dashboard.png" alt="dashboard" />

## Weather
The weather module first geolocates the trailer, so it automatically knows where to get the weather for. Then it uses OpenWeather to get the local weather for that area. I need to add in weather alerts still, but this works pretty well.

## Plex
The Plex module, so far, is the trickiest. It's easy enough to get Plex basic info from 
the Plex API, but harder to get images, and I'm still working through how to best play a video from there. Even so, it alreaady can show what you were last watching and unwatched movies. I'm still working on this one.

## Camera
A nice interfact to turn the motion-sensing camera on and off, and to report on its status.

## Wifi Status
Shows the current Wifi network and it's strength. I've written the code to show nearby networks, too, but I'm not displaying that part yet. This will be the stub for building out more robust Wifi & virtual private network functionality in order to provide safer, stronger wifi for the trailer.

## Time/date/messages
Doesn't do a whole lot yet other than show the local date and time. But it's a useful start.

I've got a lot of work to do on all these modules still, but it's not a bad start for a weekend's worth of work! If you have questions, comments, suggestions or whatever, [file an issue on Github](https://github.com/tBaxter/pi-smart-camper/issues).

