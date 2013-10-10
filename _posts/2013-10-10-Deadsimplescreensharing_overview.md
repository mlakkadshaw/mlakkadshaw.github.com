---
layout: post
title: Dead Simple Screen sharing (DSS) - Overview
---
**Grab source on [GitHub](https://github.com/mlakkadshaw/DeadSimpleScreeSharing)**

**Project [site](http://deadsimplescreensharing.com)**

Sometime ago a developed an open-source screen sharing application called as [DeadSimpleScreenSharing](http://deadsimplescreensharing.com) which allows you to share your screen with anyone right from your browser. 
It requires you to install an extension, when you click "Share your Screen" button on that extension, it will gives you a unique url which you can share with any number of people, and they can view your screen.
In this blog post I will give a brief overview on how this application works.

### The Extension:
The DSS requires you to install an extension, a extension is required because there has to be some application running background which listens to tab changes and transmits this data to the server.
The extension uses the chrome extension api's **caputreVisibleTab()** method get the visible tab and attaches **mutationObservers** and listen for DOM changes, when there is a change in the DOM, it transmits the data to the server via web sockets.

### The Server:
The server is written in Javascript(node.js) and uses web sockets (socket.io), each session is namespace by unique id which is generate when the user presses the "Share your screen" button on the extension.
The server just receives the data and forwards it to all the connected clients in that namespace.

### Get it working locally:
If you want to run DSS locally, you need to have:
1. Node.js installed
2. Install express using 'npm install express'
3. Install socket.io run 'npm install socket.io'
and follow along the video.
<iframe width="840" height="520" src="//www.youtube.com/embed/-0ifc3SuZZk" frameborder="0" allowfullscreen></iframe>

