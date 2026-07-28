---
layout: post
title: Trying to avoid cognitive surrender while also making neat things.
---

I'm a software engineer. If you haven't heard, there's a small new thing hitting the streets. People tell me it's called "AI" or something, but everybody who knows how the technology works is, or 
should be, well aware that this technology is not artificially intelligent - it is a model that uses massive corpuses of language in order to synthesize an expected result from a query. Think of it 
as something more akin to an incredibly supercharged ELIZA, or for a more recent simile, imagine autocorrect given 50000 times the training data that normal autocorrect ever was.
The image of it as intelligent is appealing but completely false. This doesn't mean that it isn't dangerous given some context, of course. 
Or that it can't do very interesting things in coding, for both good and ill.

The main achilles heel of LLMs is also the thing that makes them so powerful - it's that they need training data in order to be able to do anything. Current LLMs get this training data from the thing
I'm writing on now - the internet. Forums - reddit, digg, stackoverflow, etc. - have creating a training corpus so large that it means that LLMs have basically all the answers they would ever
want in their training data at this point.

And this is also why it takes so much CPU and GPU space to run them - if you're holding most of the internet in your hands, you need to hold it somewhere. Queries create cache and b:ntext, 
which you can use to build a bunch of tokens together, but the queries will generally take much less space than the model itself. This is why you can't normally run LLMs on our local machine.
Or ... can you?

... Anyways, this is a 'Run LLMs locally on Intel Iris graphics' post, since I couldn't find anyone doing it. Laptops are expensive now and I bought this laptop a little while ago, loved it, and
switched to it. But it's a twelfth-gen Intel processor without dedicated graphics, so the whole 'Running LLM' bit is a little painful. 
... But I did, after a lot of poking around, find a solution.

I'm running Fedora. Fedora 44, to be precise. There's an Intel oneapi graphics installer for Linux here: https://www.intel.com/content/www/us/en/docs/oneapi-toolkit/installation-guide-linux/latest/install-oneapi-toolkit-with-installer.html#INSTALL-ONEAPI-TOOLKIT-WITH-INSTALLER
With this installer you can get all the stuff you need, and it does, at least for me, work on Fedora.
You can then install llama:
https://llama.app
and pi:
https://pi.dev/docs/latest

And now you have a local LLM. It's not nearly as capable as the online models, since I don't have terabytes of RAM [I only have 32. Woe is me.], but it's still plenty capable for the 
small, fun tasks I'm doing [offline coding of personal projects]!
