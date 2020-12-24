---
template: blog-post
title: Winlink over VHF on FTM-400
slug: /winlink-ftm-400
date: 2020-12-22 06:41
description: "Emails over Radio"
featuredImage: /assets/bench-accounting-nvzvopqw0gc-unsplash.jpg
---

My local club (NCARC), and the neighboring club (LRA) both have VHF Winlink
over Packet Radio endpoints setup. I've managed to send messages to & from
both of them now.

## Hardware

My radio is a Yaesu FTM-400. Sadly, the APRS radio does packet, but doesn't
expose that feature to the outside. All it can do is APRS.

To connect it to a computer, you need a way to pipe encoded audio in and out
of the radio, and trigger PTT. That can all be done with the DATA port on the
back of the radio, and an appropriate control unit.

I used a CT-164 to adapt from Yaesu's custom DIN to a mini 6 pin DIN,
and a RigBlaster Plug N Play as the middleman for everything.

In addition I bought a cheap USB soundcard. It's tiny, and has distinct audio
& mic jacks. Less than $10 on Amazon. You need the audio and mic ports
separate to work with the RigBlaster's distinct cables. My laptop only had a
combo mic & stereo audio port, so I needed either a cable to split, or a
separate sound card. The separate soundcard is a better solution since it
lets you use the built-in audio on the laptop for whatever other uses, and
keeps windows beeps & boops from interfering with the radio.

Otherwise, just a windows PC. I use an old laptop for all my ham radio
digital work.

## Wiring

* FTM-400 rear data port -> CT-164 Adapter -> Included Rigblaster Cable -> Rigblaster
* Rigblaster -> USB -> Computer
* Rigblaster -> Audio Cables -> USB SoundCard -> Computer

## Software

### Winlink Express

Go ahead and set this up so you can send email via the Telnet (internet)
connector. There are lots of tutorials.

Now select Packet Winlink mode, and start a session. Update list from
internet to get your local repeaters. 

### Soundmodem

Download [SoundModem](http://uz7.ho.ua/packetradio.htm). It's the tool that
takes digital commands from Winlink, and turns them into the literal audio to
send over the VHF radio.

* Input/Output devices: Select the USB Soundcard
* PTT: The Rigblaster will show up as a com port for PTT operation
* Turn on the KISS server, with its default 8100 port.

All default modem settings except I added KISS Optimization. Not sure why,
but found that on another tutorial, and it seems to work fine.

## Conclusion

Hopefully that helped the next ham setup packet radio over the yaesu ftm-400.
It's a great radio, and setting this up was reasonably simple once I
understood all the pieces & adapters. Shoot me an email if you think there's
something I should add to this article, and I can get it updated.

kf0chf@gmail.com or kf0chf@winlink.org