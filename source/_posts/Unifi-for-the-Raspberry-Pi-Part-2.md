---
title: Unifi for the Raspberry Pi Part 2
date: 2018-08-29 11:43:41
tags: Raspberry Pi, unifi, pi, raspbian
---
Alright, lets assume you installed Raspbian with SSH and did the tweaks you would need to run it, you're at the point where you want to get this show on the road and start working with the Unifi controller. Don't blame you.
<!-- more -->
We want to get right to the "fight of the night", so we're again working off the assumption that you have set up your Pi as you see fit, it has raspbian on it, you've set up a language locale (this may or may not be the reason the mongoDB installation fails FYI), set a static IP (if you see fit, I would as it is your controller), set your user/pass and SSH information. Done? No? Go back and do that, then come back here.

Alright, grab the package for the Unifi Controller, debian package. 
https://www.ubnt.com/download/unifi/default/default/unifi-sdn-controller-5639-lts-debianubuntu-linux

I'l skip over needing etcher and whatnot, but this might help if you're running into troubles with it.
https://www.omgubuntu.co.uk/2017/05/how-to-install-etcher-on-ubuntu

Now if you're a bit newer or just feel more comfortable with a GUI (no judgements) you can just double click the .DEB package that you downloaded in the first link, and walk through setting things up. Its a rather painless install. If you want to hit the command line, pretty easy as well.

You'll need the Oracle Java 8 JDK, first. Not thrilled, but what are you going to do?
'sudo apt-get -y install oracle-java8-jdk'
Now go ahead and add your UBNT Unifi repo:
`echo 'deb http://www.ubnt.com/downloads/unifi/debian stable ubiquiti' | sudo tee -a /etc/apt/sources.list.d/100-ubnt.list > /dev/null`
Now:
`sudo apt-get update`
`sudo apt-get install unifi -y`

The Pi obviously isn't the most powerful device in the world, consider looking at your mongoDB setup and removing the default DB. 
`sudo systemctl stop mongodb`
`sudo systemctl disable mongodb`

Reboot that beast and hit the link - I addressed mine with a .200 address. 
https://192.168.1.200:8443

Now excuse me while I attempt to purchase more hardware without fully disclosing it to my wife.

-Bryan