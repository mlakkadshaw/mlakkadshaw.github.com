---
layout: post
title: Building command line apps in Node.js
category: nodejs
---


Node.js is becoming very popular platform for creating command line utilities, so I am writing this blog post to help you get started.


## Creating an executable script

To create an executable script you will have to add shebang at the top of the script. E.g:
{% highlight javascript %}
#!/usr/bin/env node

console.log("First program");
		
{% endhighlight %}
		
Assuming you are on a UNIX like system, you will also have to change the permission of the script and make it executable.

	chmod +x script.js
	
and now you can execute the script:

	./script
	First Program
	

## Accepting arguments

You would also want use command line tool to accept arguments, which you can do using **process.argv**. This is an array which will contain all the supplied command line arguments.

`script.js`

{% highlight javascript %}
	process.argv.forEach(function(val, index) {
		console.log(index + " : " + val);
	});
{% endhighlight %}

The above script will print out all the supplied arguments, when executed it will generate the following out:

	$ node script.js argument-1 -f -k -d 
	0: node
	1: /Users/mohammed/code/script.js
	2: argument-1
	3: -f
	4: -k
	5: -d
	
To remove 'node' and path from your script can slice out those arguments:

	var args = process.argv.slice(2);
	
There several libraries out there that will make the task of accepting arguments easier, but if you are doing something trivial, I would suggest sticking to the default method. 
One notable example of such library is [cli](https://github.com/chriso/cli).

## Colors on the command line
If you want to display messages with different colours, there is a nice library called as [colors](https://www.npmjs.org/package/colors) to do it effortlessly. 
Install it via nom:

	$ npm install colors
	 
And then include it in your script:

	var colors = require('./colors');	

	console.log('hello'.green); // outputs green text
	console.log('i like cake and pies'.underline.red) // outputs red underlined text
	console.log('inverse the color'.inverse); // inverses the color
	console.log('OMG Rainbows!'.rainbow); // rainbow (ignores spaces)

## Exit event
If you want to preform some operation on exit, you can listen to the exit event. Once the exit event is called there is no way to prevent the exiting of the event loop, hence you must only perform **synchronous** operations in this handler.

	process.on('exit', function(code) {
		console.log("About to exit");
	});




## Exit codes
Node.js provides supports for exit codes, if you script exits without any error, the exit code should be 0. If your script exits with an error it should be 1 or higher.
Exit codes in node.js are passed using **process.exit()**.

	process.exit(0)
	


## Process object

**process.uptime()**
Returns the number of seconds the script has been running


**process.memoryUsage()**
Returns an object describing the memory usage

**process.pid**
The PID of the process

If you have any questions or suggestions feel free to comment.

