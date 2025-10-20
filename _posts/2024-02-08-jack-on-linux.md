---
layout: post
title: Realtime audio on Linux? It's actually not that bad if you know the secret invocations!
subtitle:
tags: [music, code, tech]
comments: false
---

So I wrote a post like this about my framework laptop. We are now a year and a half into the future, and I've bought windows for that laptop. I couldn't deal with it.

However, I bought a mac mini for a project. The project didn't work, but I still have the mac mini, and it's so old it can't run a current version of MacOS!

So I wiped MacOS and installed ElementaryOS, but it was such a pain in the ass that I installed Kubuntu instead. And that's been much better.

Anyways, after installing Kubuntu, it's been way beter! And I figured ... I bet I could set up Jack properly. And my brain wanted to try ... and ... after some work I got it working! So I wanted to record the steps:

Step 1:
Install a bunch of stuff. 

`sudo apt-get install jackd qjackctl pulseaudio-module-jack a2jmidid`

Step 2:
Set up qjackctl, and open it. You'll be starting it before you open your DAW.

Step 3:
Add this line to qjackctl in options > execute script on startup:

`pactl load-module module-jack-sink channels=2; pactl load-module module-jack-source; pacmd set-default-sink jack_out; a2jmidid -e &`

Step 4:
Before using your DAW (I use Reaper), open up qjackctl and press start. This will set your sink module, and will enable the alsa midi layer through jack. Everything should now work as you expect!

This loads and deals with the pulseaudio shim (which allows music to be played before and after reaper) and also enables passing midi from alsa into jack.
Why is it a pulseaudio shim? Look, this works. I don't wanna think about it anymore.

Hopefully it helps if you are looking for this. :)
