---
title: Uh-oh
description: In which your intrepid adventurer breaks everything and learns the hard way about some quirks of the Raspberry Pi.
date: 2020-04-08
mod_date: 2020-04-11
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

_Edit: Originally I included setup instructions here, but they've grown enought to [merit their own page](../definitive-setup-guide.md)._
