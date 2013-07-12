---
layout: post
title: Handling custom tags in Android using Html.TagHandler()
---

While working on my app [Android app Ken](https://play.google.com/store/apps/details?id=com.mohammedlakkadshaw.ken&hl=en), I needed to render HTML in Android, I was very much delighted when I found out that android's TextView supports HTML rendering and it can be easily achived by converting html into [Spannable](http://developer.android.com/reference/android/text/Spannable.html) using **Html.fromHtml(<html_Content)** method and sending it to TextView's setText method.
   
    TextView myTxt = (TextView)findViewById(R.id.textView);
    myTxt.setText(Html.fromHtml(htmlContent,ImageHandler,TagHandler));


But there is catch with Html.fromHtml method, it doesn't support all tags; well that was a killjoy, but html.fromHtml method accpets a TagHandler which is class we can implement to handle custom html tags, but it is not well documented, after struggling for a while and reading the source code of HTML class method I was finally able to define my own tagHandler class which is able to handle ul, ol and code tags.

## Handling Html

Here is my custom tagHandler:
<script src="https://gist.github.com/mlakkadshaw/5983704.js"></script>

The above Java file HtmlTagHandler handles, ul, ol, and code tags. 
The **handleTagList()** method handles the list tags, and handling of code tag was pretty easy, I just need to find the start of the code tag, I do this by adding a flag on the start of the tag **Spannable.SPAN_MARK_MARK** and when the tag on end I just find the object where I marked **Spannable.SPAN_MARK_MARK** using **getLast()** and find its position, and store it in the variable name **"where"**; that's the start of the code tag, and I get the end of the code tag using output.length() and set the font face of that text fragment to "monospace" using **(new TypefaceSpan("monospace")**.

That's it! If you want to use it in your project create a java class with content of this file and create a object of HtmlTagHandler and pass it to your fromHtml method.

Also try out my app [Ken which is available on Google Play](https://play.google.com/store/apps/details?id=com.mohammedlakkadshaw.ken&hl=en) which a free magazine for programmers, you have to select your interest (e.g Javascript, Android, Ruby etc.) and it will show you all the latest news, articles, tutorials related to your interests.

P.S: For handling image I using a nice library called **"URLImageParser"** [Github link](https://gist.github.com/Antarix/4167655)
