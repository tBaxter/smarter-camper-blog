---
title: Building out the project box.
description: In which your intrepid adventurer builds out the hardware
date: 2020-02-10
tags:
  - hardware
layout: layouts/post.njk
---
This evening I put all the bits into the project box, which was pretty staightforward,although it did require thinking through some bits. 

*Full disclosure: affiliate links ahead. Also, I haven't figured out how to add photos yet. Working on that.*

I used a decent-sized [water-resistant enclosure](https://amzn.to/31TiPL3) to house everything. Honestly, it was bigger than I needed, given the tiny size of the Pi and the SSD drive, but it left some breathing room, and it will still tuck neatly into the bottom of the closet in the trailer, by the wheel well.

Additional information is in the [project repo] but here's a short version of what is, as Detective Mills might say, in the box.

Most important, of course, is the Pi 4. I bought a 4 thinking it would provide the best media server capabilities, and best handle multi-tasking other things I want to do, but I do wonder if maybe I could have used a cheaper 3. At this point, it doesn't matter. The 4 is in there and doing the job nicely.

I mounted the Pi in the box using lightweight (and corrosion resistant) [nylon stand-offs](https://amzn.to/2SfGh1w). I had to drill out the Pi mounting holes slightly to accomodate the more-common M3 size, but that's pretty trivial. And common.

The [SSD drive](https://amzn.to/37fqeFi) is a 240GB unit chosen because it was reasonably cheap, appeared to be rugged and supported fast USB 3.1. Honestly, any SSD drive should work so long as it's reasonably large and you can figure out how to mount it. I drilled out the faux bolts in the corners and then mounted it to the enclosure lid using stainless steel machine screws and acorn nuts. I had laying around.

I used a [12V-5V stepdown converter](https://amzn.to/2OKVRAb)
to take the camper's 12V system power down to something Pi-Friendly. Well, at least I planned to. While I can see that the voltage going *to* the converter is ~12V, when I hook it up I'm seeing 5v, and I'm not getting the Pi to power up. So I need to figure that out. I also had to use a [Micro-USB to USB-C adaptor](https://amzn.to/2w03OuK) so that's another potential failure point. I'm wondering if that's the right converter or if I've just got something else going on. More to come.

I also added a [Power button with LED](https://amzn.to/3bqPrQs)
to safely power the Pi up and down. The button is recessed so it won't get toggled accidentally and it incorporates an LED so I can see if the PI is on or not. Pretty spiffy.

And finally, the cellular modem. It's in the box, but I dunno. It's a giant pain to deal with, and I still don't know if I can actually get it to work or not.
[The USB modem I purchased](https://www.amazon.com/gp/product/B07X129SNS/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1) took six weeks to arrive and came with almost no instructions. It took awhile to even figure out where to put the SIM card. Definitely not recommended. But it's what I have, and it _should_ work. I've copied the Linux instructions found on the modem itself into the project repo, but so far I don't trust them. We'll see.

The instructions are hard to find because by default the modem doesn't want to mount on the Pi, and it doesn't appear as a USB drive, either. So that's fun. 

That covers pretty much everything in the box. It's all in there pretty tidily and works beautifully when powered by the stock Pi power cord, but I still need to get things working correctly on the 12V trailer wiring, and I still have to figure out that cellular modem problem.

We're in it for the journey, right?