---
layout: post
title: Mixpanel Tracking in AngularJS
category: angularjs
---

For my recent angularJS application, I needed to integrate Mixpanel.
I didn’t found any light-weight directives which I could include in the application that would allow me to easily track events using Mixpanel in the application, so I built Mixular. 
Mixualr is a lightweight angularJS directive which you can use to track events in your application.

## Installation
You can install mixular via bower 

		bower install mixular

Or you can clone the repo from [Github](https://github.com/mlakkadshaw/Mixular)

## How to use it 

To use mixular in your application include the Mixpanel javascript tracking library, and the `angular-mixular-directive.js` in your index.html

Then add mixular dependency in your AngularJS application:

	var app = angular.module(“yourApp”, [“mixular-directive”]);

Once you have added the dependency, you can start tracking events in your application, e.g:

	<a href=“#/feedback” mixular=“click” eventLabel=“Feedback Clicked” prop-user=“James”>Feedback</a>	

Add the property `mixular` and specify the events on which you want to trigger the tracking, supported event types are:

+ click
+ focus
3. hover
4. keydown
5. keypress
6. keyup
7. mousedown
8. mouseenter
9. mouseleave
10. mouseout
11. mouseover
12. mouseup
13. scroll
14. select

The `eventLabel` can be used to specify a label for the event e.g “Banner Ad clicked”.

### Passing properties

To pass multiple properties for a event you can type the keyword prop followed by the property name e.g `prop-product=“Laptop” prop-price=“500”`

### That’s all
If you have any questions or suggestions regarding the directive, leave them in the comment section below.

Thanks

	
