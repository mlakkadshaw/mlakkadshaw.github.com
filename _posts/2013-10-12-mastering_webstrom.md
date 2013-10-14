---
title: Mastering web-storm
layout: post
---

I am big fan of sublime text, and I use it extensively. Then I came across WebStorm, I like it and I want to learn more about it, because any craftsman should know how to use his tools effectively. 
So I was looking for some tutorial and videos on mastering web storm and I came across this excellent video by John Lindquist. I highly recommend that you [watch the video](http://www.youtube.com/watch?v=LJOyrSh1kDU&feature=youtu.be).
<iframe width="560" height="315" src="//www.youtube.com/embed/LJOyrSh1kDU" frameborder="0" allowfullscreen></iframe>
I have also tried to summarise what's there in the video, but I recommend that you watch the whole thing, but for those who cannot spare the time to watch the whole thing, here is the excerpt:

### Code Inspect:
Webstorm offers a nice code inspector, and to inspect code, right click on any directory inside Webstorm and click inspect Code.
It will give you a list of the issues and warnings and improvements which you can make, and is kind of really useful when your are doing code reviews and stuff like that.

**Autocomplete Shortcut**: Whenever a small bulb appears in Web storm, it indicated that Webstorm has some suggestions, and you can hit  *alt+Enter* to bring the menu which shows the suggestions.

**Go back in time**: Webstorm has a nice auto-save feature, you don't have to manually save things in Webstorm, and when you have changed something and want to revert your change you can go back in time by: *Right-click-> local history*

**Getting things from CDN**: When using CDN in script tags and stylesheets src, Webstorm will show a warning, you can hit *alt+Enter->Download locally*, by doing that it will download the linked file and show autocomplete off that.

**Fine tune suggestions**: In Webstorm you can fine tune the settings about auto-complete, suggestions, warning and errors.
Click on the lower right hand side corner->on hector the inspector and fine tune the inspection

### Keyboard shortcuts:
To learn about keyboard shortcuts, go to 
[Shorcut Foo](https://www.shortcutfoo.com/app/tutorial/webstorm)

### Actions:
*Cmd + Shift + A* bring the action bar.
Select content, and press *cmd+shit+a* and select *create live template.*
And add variable by $name$ and $end$ to specify where the cursor ends.
Webstorm uses velocity template language.

### Refactoring
Refactor this shortcut CMD+SHIFT+ALT+T
/**+tab automatically generate the document
**Cmd+Alt+V** to pulling out variable.

### Navigation
Open up the file structure: can also be invoked by cmd+f12

To navigate project: cmd+shift+n, wildcard are also supported 
s/a/*.js -> source/auto/ and all the javascript
cmd+alt+shift -> type the name of the method
and cmd+shift+i while doing this, will also show preview of the file, and cmd+shift+j while doing that will show documentation if available.

### Version control:
Webstrom also has an integrated VCS manager, to bring the VCS Popup hit *Ctrl+V*.
Webstorm is also integrated with Github, you can easily import your github repos in Web-storm.

### External tools:
To add external tools, go to *Preference -> External tools* and add details about the external tools you want to add, for e.g. Yeoman

### File launchers:
If you create a coffee script file, it will ask you to add a watcher, and it will generate the corresponding js file, same if for sass etc. 

