---
layout: post
title: Desktop Linux will never be usable as a stress-free daily driver
subtitle: I would like to be able to "read" "text" on HiDPI screens.
tags: [tech, hidpi]
comments: false
---

I have too many laptops. One of them is a Framework, which I bought solely to use Linux, because I have the freedom to use something else when it's annoying.
... But at this point I'm close to just buying a Windows license anyways.
Basically, the main source of my issues is that the Framework doesn't have a 1920x1080 screen: it's 3:2, 2256x1504. 
So when I use it, I have two choices of non-fractional scaling: 100% and 200%.
200% is tiny. Text makes me feel like I'm 60, everything is in 6 font.
100% is massive. It's the equivalent of 1128x702 - definitely not enough content on the screen.

I was initially using Fedora, the "most supported" distro, and then it somehow wouldn't let me print. I only print once every three months, but when I need it I actually do need to print things.
So I went back to Ubuntu and printing worked first try. ... But HiDPI was messed up. Slowly I stopped using it because it was annoying and I just didn't want to troubleshoot the problem.

I only really use Discord and Firefox though, so I loaded up my laptop today, and remembered this issue.
And I went through figuring out how to do this ... it took two hours or so. (This post is also me remembering these settings.)

Firefox was easy, I just had to add this line to my ~/.profile file:
export MOZ_ENABLE_WAYLAND=1

On Ubuntu, I decided to just install Discord directly and not use a snap, and then I was able to edit the Desktop setting like this:

sudo vi /usr/share/applications/discord.desktop
And then change the exec to this:
Exec=/usr/share/discord/Discord --enable-features=UseOzonePlatform --ozone-platform=wayland --enable-features=WaylandWindowDecorations

Yes, it took me two hours to find that. ... But it's absolutely absurd that this is required. These are the types of issues I run into when I try to use Linux ... and it's what makes me confident that the Linux Desktop just isn't going to happen.

There are always going to be these edge cases - not even very edge-like - that make hardware just ... not work as well. It's inherent to the project.
I'm considering dual-booting at this point - I just ... don't want to deal with my laptop occasionally breaking. It's not worth it anymore. And that's a bummer, but ... I guess it is what it is. I'm accepting it at this point.
