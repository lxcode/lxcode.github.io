---
layout: post
title: Stealth teleconference
---

So, I oftentimes find myself in a place where I can't really take a
confidential phone call, or I have to step away from the computer to take a
conference call where I'm mostly just listening. I have found a way to take
calls from wherever I'm sitting without being concerned about being overheard.

This is on OS X, but you could probably accomplish the same thing with
Pulseaudio and/or Jack.

First, grab a copy of Soundflower:

<https://code.google.com/p/soundflower/>

Reboot.

Start Skype, and change your microphone input to be the 2ch Soundflower device.

Now, open the terminal and type:

    say -a "?"

It will give you an audio device list. Pick the number of the Soundflower
device. Let's say it's 199.

Now, you can speak using:

    say -a 199

    Yes, I was listening intently, but have no comments.

Ta-da.
