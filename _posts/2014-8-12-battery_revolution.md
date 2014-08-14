---
layout: post
title: AngularJS + Underscore The ultimate web-development toolkit
---


Before starting my latest web-development project I was looking for some robust javascript frameworks that I could use. I was familiar with AngularJS and I loved it, but it doesn't have a lot of utility methods and I was looking for some solution to solve that problem. 

So, I thought about using underscoreJS, which is collection of utility methods with angularJS and I got myself a killer web development toolkit, in this blog post I have summed up underscoreJS methods which I find useful. visit [underscorejs.org](http://underscorejs.org/#) to view all the available methods.

## Using Underscore with Angular:

Combining angular and underscore is pretty straightforward, want you can do it add import underscore in your index.html, then add it as a service.

<script src="https://gist.github.com/mlakkadshaw/6850612.js"></script>

And then we could inject it into our controllers:
<script src="https://gist.github.com/mlakkadshaw/6850655.js"></script>

## Useful Underscore methods:

I have compiled a list of my favourite underscoreJS methods, you can always visit [underscorejs.org](http://underscorejs.org/) to view all the methods that are available in underscore.

###_.isUndefined:
This method is used to determine weather the specified value is undefined or not, I know you could always do **typeof value === "undefined"** to check weather it is undefined or not, but I find this neater.
		
		_.isUndefined(value)
	
	
	
###_.defaults:
This is also a very useful method, it allows you define a default values for something if they are not present.
	
	var data = {"model":"T", "manufacturer": "Ford", "price": "200"};
	_.defaults(data, {"model":"N/A", "N/A": "Ford", "price": "0"})
	
	output: ---> {"model":"T", "manufacturer": "Ford", "price": "200"}
	
	_.defaults({},{"model":"N/A", "N/A": "Ford", "price": "0"})	
	output: ---> {"model":"N/A", "N/A": "Ford", "price": "0"}
	
### _.where:
This method comes handy when you want to search something in the array of objects using some attributes present in the object.
consider the example below.
<script src="https://gist.github.com/mlakkadshaw/6850250.js"></script>

### _.uniq:
This method operates on arrays, and it removes duplicates in the array.
Consider the following example:
<script src="https://gist.github.com/mlakkadshaw/6850524.js"></script>
 
###_.pluck:
if you ever wanted to extract some values from an array of objects, well the pluck method let's to do that.
Here is the example:
<script src="https://gist.github.com/mlakkadshaw/6bc81a35e33dbcfcc1bc.js"></script>



By merging these two awesome web development frameworks together we can get a pretty nice web development experience, as angular serves as an awesome MVC, and underscore provides a very useful collection of utility methods. 