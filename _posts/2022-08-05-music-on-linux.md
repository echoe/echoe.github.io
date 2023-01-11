---
layout: post
title: Setting up REAPER on Linux: why, how, and etc.
subtitle: I think it's actually realistic now!
tags: [music, code, tech]
comments: false
---

So I bought a Framework Laptop.

https://frame.work/

Mostly this is because I want every tech product in the world (tm).

But also, I've gotten into a point in my life where I can actually buy things not because they make the most sense, but because I want to.
So with the Framework Laptop, you can replace everything really easily, and I could very easily get some overkill in the form of 64GB of RAM, and just plop it in. Since I want to support Framework's mission ... I made the purchase.
Now I also wanted to run Linux on it. Fedora is recommended as the best operating system for it (with the most 'It just works' feeling), and I've had a pretty good experience, outside of power management (I'm very particular about power management though).
I've set everything up and with some TLP settings*, it works roughly similarly to my Macbook Air, with a few changes:

* Battery life is halved. M1, it's too good.
* I have to open Discord in Chromium for the lowest CPU drain (yes, not in Firefox or in the prebuilt Electron package).

I generally use my laptops to do four things:

* Write.
* Browse the internet.
* Code.
* Make music.

Writing is really easy to do, as is browsing the internet. Coding is covered in Linux very easily (it's what I do all day for work!). That leaves ... music. I've had linux laptops in the past and they've always lacked this, so I thought it would be fun to try and set it up.

So ... here are some notes on the process for me:

- My audio editor of choice is REAPER. I own FL Studio, Logic, and Ableton, but I just prefer REAPER - the track view is very intuitive, and it's very customizable.
This is incredibly convenient for Linux as it's well-supported. Bitwig is also supported - YMMV, as I've found it more complex to set up in the past.
- Recently I bought Atlas as a drums editor, and have really enjoyed it. Happily, Atlas is /also/ Linux-compatible.
- This just leaves synths - there are a lot of possibilities here. I usually use Pigments, but it's not standard and really there aren't a ton of easily-installable synths in Linux.
I did remember Vital, and then went through a small process wherein I had to install a port of gnutils for graphics:
https://copr.fedorainfracloud.org/coprs/patrickl/libcurl-gnutls/
and then copy and paste the .vst3 folder to the same spot as Atlas. But with that ... I have a really flexible wavetable synth, and a drum machine.
- Surge XT is a free and open-source synth for Linux that's pretty good, as far as I know. I haven't really used it before, but you can install it here: https://github.com/surge-synthesizer/releases-xt/releases very easily, just downloading the 'pluginsonly' .tar.gz: surge-xt-linux-1.1.0-pluginsonly.tar.gz, unzipping it, and then placing the pertinent folders into .vst3 .
- GSnap works for some vocal correction. https://www.gvst.co.uk/gsnap.htm?pageview=selectos Just copy and pasting the .so folder into .vst3 .

So you can install and run this in an almost entirely linux-based workflow!

- Happily - and perhaps I just didn't do enough searching to find it the last time - you can install windows plugins fairly easily with https://github.com/robbert-vdh/yabridge ! It works ... really simply. I just followed the instructions, and I can now run Digitalis ( a great and strange plugin you can read more about here: https://aberrantdsp.com/plugins/digitalis/ ) without issues on Linux. So if you want you don't need to abandon your old stuff. :)

My TLP Settings are only four main things:
```
CPU_MAX_PERF_ON_BAT=0 #This ensures the CPU does not boost.
CPU_MAX_PERF_ON_AC=90 # This brings max CPU when plugged in under 100 so it does not get near boosting. This is set conservatively and sometimes when I'm plugged in I will purposefully sudo tlp bat to set max CPU back to 0.
PCIE_ASPM_ON_BAT=powersupersave # I may switch this to powersave in the future, it just forced the most power saving mode.
RUNTIME_PM_ON_AC=auto # This will enable powering down PCIe devices while plugged in.
```

Disable the built-in Fedora power management to add tlp and run the suggestions, and everything has been pretty good since then.
(Yes, I'm lowering the power of the machine substantially. I'll be honest - I don't care. I just want it to not have the fans spin up noticeably, and to remain relatively cool.)

I've been really enjoying the Framework so far and would recommend it as a way to step into Linux for the linux-curious, as long as it's affordable to you. :)
