---
layout: post
title: Use your Android Phone as a display for Raspberrypi
---


I read this tutorial on how to use your Kindle as a display for your Raspberrypi [link](http://www.ponnuki.net/2012/09/kindleberry-pi/), and I thought why not use an Android phone as display and use usb ports on the Raspberry Pi for keyboard and mouse.

Things you'll need:

1. Android phone
2. A Raspberry pi

What we'll do:

1. We will install VNC on Android, I am using pocketvnc
2. Then, we will use USB tethering on Android and connect it to Raspberry pi using USB
3. Then in the Raspberry pi we will install x11vnc **(sudo apt-get install x11vnc)** so that we can connect to an exisiting X-Window server and share it using vnc, so that we can use keyboard and mouse connected to raspberry pi.
4. Change the ip address of raspbery pi **sudo ifconfig usb0 192.168.42.10** (Because android assing IP in USB tether mode in the range 192.168.42.x)
5. Start the X-Server (if you have not started it alerady) using the  ***startx*** command.
6. The share it using x11vnc, type the following command in the terminal: ***sudo x11vnc -display : 0
7. Then connect to your raspberry pi to Android using the VNC software you have downloaded: port 5900 and IP 192.168.42.10

I know it is not very detialed tutorial and a bit crude, I will soon post a detialed one with images and video.
Also we could automate a lot stuff on startup using .bash_profile so that we don't have to type in these commands everytime.
I'll post all this in the next update.

I would love to hear about you suggestions in the comments.
Thanks

(Please excuse the typos, I am very excited about this and I want to post it online ASAP, so I am not profreading it.)