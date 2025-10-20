---
layout: post
title: ... Nextcloud on Windows can be annoying with spaces in the front of your files sometimes. But you can fix it!
subtitle: Just a little tip!
comments: false
---

So I have a 1TB Nextcloud instance. This is what I use to store all my personal files, and back up purchases.
However, sometimes I download files, and it's a large bank of things, and half of them are named " 1.txt" or something.
Let's say you buy a large pack of music samples and then they won't sync to your computer because of this. You know, totally randomly.
...
If you've used Nextcloud on Windows, you'll realize that this actually sort of breaks syncing and it shows you a bunch of error messages.
I hate error messages!

... So I fixed it, in bash. First, find the files:

`find . -type f -iname '/ *'`

Then rename them:

`rename 's|/ |/|'`

Run it with the -n flag to make sure everything won't break:

`find . -type f -iname '/ *' -exec rename -n 's|/ |/|' {} +`

And then you can just run it for real! And ... no errors. The yellow checkmark went to green. That's all I wanted, haha.
(And no: I refused to hand edit 1800 files to solve this. Thank god for bash scripting.)
