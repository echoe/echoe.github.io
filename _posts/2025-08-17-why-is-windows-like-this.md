---
layout: post
title: Active and Passive cooling options in Windows are hidden behind a registry flag, because Windows hates its users.
subtitle: :|
comments: false
---

It's been a minute! ... I found something frustrating about windows, and NixOS, so figured I'd make a post. 

For Windows: in another episode of 'Posting about bullshit I've found out on the internet', Windows has an option to reduce fan noise built into it.
As someone who really, really cares about fan noise, this is absolutely massive???
It's mentioned here:
https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/passive-and-active-cooling-modes
To enable seeing it as an option, though, you have to edit the Windows Registry like this:
https://www.tenforums.com/tutorials/107953-add-remove-system-cooling-policy-power-options-windows.html
I did this tweak and my laptop simply stopped doing the fan noise hiss at me. That's all I really want. Why is this so difficult to get otherwise?!?! And why is this option /hidden/?? Seriously???
... Windows is ... exasperating sometimes. But MacOS charges so much for storage that I've started to get used to Windows again.

Also, I had an issue with my NixOS install - the keyring was not unlocking. ... I ended up just tempirarily installing seahorse (a utility to edit keyrings) and just setting the keyring blank, because this is not a computer that I am worried about people grabbing secrets from (I use it to stream to twitch, record youtube videos, and nothing else: if you have physical access, I am having a severe problem, and if you have access via the internet, I also am having a severe problem). Before this, I would open Nextcloud, and it would tell me I haven't logged in before. And when I attempted to log in, it would pop up a keyring password question. I didn't know the keyring password - it's not the computer password - and it wouldn't fail to doing nothing. So I had to ... restart ... to avoid the keyring password dialog box.

........

Anyways, it's resolved now. I suppose I could've also opened up a terminal-only Linux screen with alt+f1 and then killed the process but ... I didn't. And ... ugh. I'm just happy I can use that again.

So. Two small problems, two small solutions. Onwards and upwards. :)
