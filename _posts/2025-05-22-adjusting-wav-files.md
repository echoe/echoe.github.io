---
layout: post
title: Oh no! Once again a file is not the right format.
subtitle: it took me longer than I hoped for this, heh.
comments: false
---

Long time no talk! I've been good, honestly. Took a long amount of time offline and I don't hate coding anymore, which is /pretty great/!! Still on sabbatical, but I caught covid.
... And I made a small technical string to do something I wanted to do, so I figured I would share it ... here, which is somewhere.
Why did I figure it out? ... I'll tell the story real quick.

First: I bought a sample pack from 'Star Powered Drums'. (They're an amazing drummer, honestly.) It's a fun pack, but it didn't work on my SP-404mk2 because of the format of the file.
I have been learning how to actually use it after owning it for three years, so ... that seems not great. I want to use the samples!
But how do I convert them? I could drag them all into audacity or reaper and hand-convert them all, but it's like ... 300 samples. God.

... So instead I could look up a bunch of stuff about how the zsh terminal works in MacOS, and write this small snippet:

  IFS=$'\n'; for file in `find . -maxdepth 2 -type f -name \*.wav`; do sox $file -b 16 ${file/.wav/-16.wav} rate 44100; done

Go to the folder you want, run this, and you should be good. :) I thought it was a little ... messy afterwards, so I ran this to delete the non -16 bit wav files:

  IFS=$'\n'; for file in `find . -maxdepth 2 -type f \! \( -name \*16.wav \)`; do rm $file; done

And I am happily resampling every loop to go +1600% speed so it stretches over four minutes now. :p I hope this helps if you need it!
