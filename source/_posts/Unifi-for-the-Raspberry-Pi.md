---
title: Unifi for the Raspberry Pi
date: 2018-08-29 10:58:56
tags:
---
Continuing the trend of being a cheapskate, I decided my homelab is mostly going to consist of Ubiquiti networking equipment with a Unifi controller, but without a cloud key. Basically, I'm opposed to spending $100usd on the cloud key which is likely just comparable hardware in a fancy case. So, I can leave a Pi on the network for minimal cost (and may likely clone it, put it in a VPC on AWS) and control all of my hardware. Lets explore.
<!-- more -->

Unifi has a debian package that should install easily on Raspbian/Ubuntu/Mint/CentOS and while I know a bit about all of these, i've never put CentOS on a Pi and it looks like the install would have some extra, unsavory steps so i'll be lazy and skip that. I have a RPi Model B, 1.2. 

First, I grabbed the latest Raspbian image from the net, grabbed the Yoga with the SD card slot, and got to work. I'll spare you some of the extra details as I don't feel like typing them, and honestly, you likely know how to do this part. For whatever is left, there are tons of resources on how to do this elsewhere online.

Once you're installed, you'll want to set up SSH on the device as well as update the environment before continuing. Once you're installed and have the device connected to a keyboard/mouse/monitor, you'll want to change passwords and generally harden the device, from there we'll move on to part 2.