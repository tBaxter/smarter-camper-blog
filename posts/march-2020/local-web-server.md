---
title: Setting up a local web server on your Raspberry Pi
description: In which your intrepid adventurer begins setting up a web page to monitor things
date: 2020-03-17
tags:
  - web
  - software
  - interface
layout: layouts/post.njk
---

# Setting up a web app
With the first [sensor wired in](../motion-sensor-hardware) it was time to shift attention to software. The overall goal is to be able to monitor the status of things from anywhere, anytime. The easiest way I know to make that happen is with a web app.

Normally, Django is my go-to framework for web app work, but in this case I decided to use Flask. 

Like Django, Flask is a Python-based web framework, with a couple of key differences:

1. It's really lightweight, which makes sense with the modest demands of the app and the modest resources of the Pi.
2. I haven't used it before, so there's a nice learning opportunity.

Keep #2 in mind, though, when I write terrible Flask code. I don't claim it's good -- I'm learning too!

There are quite a few tutorials online to [set up Flask on a Pi](https://randomnerdtutorials.com/raspberry-pi-web-server-using-flask-to-control-gpios/), but really, it's pretty straightforward. 

First, make sure everything is updated and upgraded, and install Flask:
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python-pip python-flask
sudo pip install flask
```

Now, if you were starting from scratch, at this point you'd want to follow a Flask tutorial. But since I've done this once before to prototype it, I have an existing Github repository I can use that will save me a ton of time.

so, first I navigate to where I want the code to live:

`cd /var`

I want the code to live in `/var/www` but the `www` folder doesn't exist by default. That works well, though, as it gives me a clean place to clone my repository:

`sudo git clone https://github.com/tBaxter/pi-smart-camper.git www`

You have to run that as `sudo` to be able to create the `www` folder you're cloning into, but once you've done that, you can transfer ownership to the regular `pi` user:

`sudo chown -R -f pi /var/www/`

If you `cd www` to go into your new `www` directory, and then use `ls` you should see 
 `cellular_modem`, `LICENSE`, `monitoring`, `README.md` and `webapp` just like you would if you visited https://github.com/tBaxter/pi-smart-camper

From there, you can move into the `webapp` directory (`cd webapp`) and start up your Flask app:

`python3 app.py`

If everything is working correctly, you should see something like

```
 * Serving Flask app "app" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
 ```
 From there, go to your browser and substitute  the IP address for your Pi (the one you SSH'ed into) for 0.0.0.0 and you should see your new site, running on your Pi web server.

 Next time I'll explain what's going on in the code.


### Helpful links:

https://www.raspberrypi-spy.co.uk/2013/01/cheap-pir-sensors-and-the-raspberry-pi-part-1/
https://www.hackster.io/mjrobot/playing-with-electronics-rpi-gpio-zero-library-tutorial-f984c9


