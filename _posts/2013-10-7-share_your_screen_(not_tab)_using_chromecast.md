---
title: Share your entire screen using Chromecast
layout: post
---

Google's chrome cast allows you to bream content from your computer/phone to TV, and you can play youtube videos, music, etc. It allows also a really nice feature called as tab sharing, it allows you to share your Google chrome tab to the TV.
But it doesn't allows you to share your whole screen, in the post I'll explain how you can do that.

## Things required
1. Latest version of Google Chrome
2. Chromecast
3. [Google Cast extension](https://chrome.google.com/webstore/detail/google-cast/boadgeojelhgndaghljhdicfkmllpafd?hl=en) installed in google chrome 


## Procedure

1. Visit https://html5-demos.appspot.com/static/getusermedia/screenshare.html
2. Click on "Capture your screen button"
3. Click on Chromecast extension and share the current tab
4. Minimise Google chrome and enjoy.

Now can see your screen, but you can also a white border which is not nice, and you can't get a full screen, to get past that you need to do a bit of extra work.

Download the [zip package](https://dl.dropboxusercontent.com/u/4095659/server.zip) and extract it's contents, and install Node.JS if you don't have already.
Then open terminal in mac or Command Prompt in windows and type "cd " and drag and drop the "server" folder into the terminal window.

Then run "sudo node app.js" and visit **https://localhost** (Note:It's **https** not http), Google Chrome will give you a warning, and you can safely ignore it, because the certificates which I have created for https to work are not verified by any recognised issuing authority.

You'll now see your screen, now share this tab with chrome cast and minimise the Google chrome.
Enjoy!

If you have any questions, ask them in comments below.