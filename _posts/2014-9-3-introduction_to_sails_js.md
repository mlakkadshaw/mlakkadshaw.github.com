---
layout: post
title: Introduction to SalisJS
category: nodejs
---

I was looking for a Node.JS web framework for my project, and in my quest for finding the best framework, I stumbled across Sails.JS, and I have been using it for a few months now and it is pretty awesome at most of the part, so if you need something like Rails for Node.js, Sails is the way to go.

The Sails.JS is an MVC framework, so there are Models, Views and Controllers.

## Models:
In Sails.JS you can create models, and model represents the data model, so if for each table you would have a model and in case of no-sql databases, each collection is represented by a model.
Inside a model you can describe, the attributes present in that model, their datatype and validation rules.

Example of a User Model:
	user.js
	
		module.exports = {
			attributes: {
				firstName: 'string',
				lastName: 'string',
				email: 'email',
				role: {
					type: 'string',
					enum: ['admin', 'user']
				}
		}

In the above example we have a user model, which has a number of attributes, like firstName, lastName, email and role.
The model structure is pretty straightforward, and Sails.js provides some useful helpers in modules like the `enum`.
We have added an `enum` attribute in role, now Sails will accept only the values present in the enum array.

### Magic:
The magical part is sails is **blueprints**. Sails will create CRUD routes based on the data model. 
Sails will look at your data-model and will create blueprint routes and REST api.
So, by looking at the model we have created above sails will create REST APIs.
**Create User**:		HTTP POST:		/user 
**Update User**:		HTTP PUT: 		/user/:id
**Delete User**:		HTTP DELETE: /user/:id
**Fetch User**:			HTTP GET: 		/user/:id
**Get All Users**:	HTTP GET: 		/user 
 
### Associations in Model
In Sails you can associate one model with another model, and associations can span across databases.
So if you have user data stored in Postgres and photos stored in Mongodb, you can interact with the data if they lived in the same database.

#### Many to Many
In this type of association, one model can be associated with many other models and vice versa.
Lets consider an example of a Real Estate, a Real Estate can be owned by multiple people, a person can own multiple Real Estates.
Thus we can create a many to many relationship between people and real-estate.
So, let's begin:

	estate.js
	
	module.exports = {
			attributes: {
				propertyName: 'string',
				Address: 'string',
				owners: {
					collection: 'user',
					via: 'estates'
				}
			}

	user.js

	module.exports = {
		attributes; {
			firstName: 'string',
			lastName: 'string',
			estates: {
				collection: 'estates',
				via: 'owner'
			}
		}
	}

So, in the above example we have created two models, one is user model and another one is estate model.

In the estate model we have created a property named owner, which reference the user model model and points to the owners of the property, so this will be an array containing all the owners of the property.

In the User model we have created a property named estates, and it points to the estate model and it will contain all the estates owned by the user.

### LifeCycle callbacks in Models
There are lifecycle call-backs present in the models which are very helpful, for e.g: If want to can write some cleanup code when an item in a model is deleted, so you can write the code for that inside the `afterDestroy` method.

**Callbacks on create**

	beforeValidate: fn(values, cb)
	afterValidate: fn(values, cb)
	beforeCreate: fn(values, cb)
	afterCreate: fn(newlyInsertedRecord, cb)

**Callbacks on update**

	beforeValidate: fn(valuesToUpdate, cb)
	afterValidate: fn(valuesToUpdate, cb)
	beforeUpdate: fn(valuesToUpdate, cb)
	afterUpdate: fn(updatedRecord, cb)

**Callbacks on destroy**

	beforeDestroy: fn(criteria, cb)
	afterDestroy: fn(destroyedRecords, cb)

Consider the example:

		module.exports = {
			attributes; {
				firstName: 'string',
				lastName: 'string',
				estates: {
					collection: 'estates',
					via: 'owner'
				}
			},
			afterDestroy: function(values, cb) {
				//Write you cleanup code here...

				cb();
				}
		}

To learn more about the lifecycle callbacks, see the [official documentation](http://sailsjs.org/#/documentation/concepts/ORM/Lifecyclecallbacks.html).

## Controllers
The main logic of your application will be present in the controllers, the controllers are responsible for responding to the requests.
Although, some magic is provided by Sails, using blueprints to create automatic CRUD API, often times it is not enough and you will want to add more functionality and more types of routes.

Consider an example controller file name greeting.js:

		module.exports = {
			hello: function(req, res) {
					return res.send("Hello world");
			},
			hi: function(req, res) {
					return res.send("hi user");
			}
		}
	
The above file contains two actions, namely `hello` and `hi`, inside these actions we can write the code to do whatever we want, in the above example we are sending messages, "hello world" and "hi user" respectively.

Sails has automatic routing, so the controllers and actions that you have created will be routed automatically, by the following format `/:controller/:nameOfAction`.

So routes for our above actions will be `/greeting/hello` and `/greeting/hi`.

### Overriding blueprint actions
If you want override the blueprint actions, like create, update or delete, just create actions in the controller with that name and it will override the default functionality.
Suppose we want override the `create` functionality for user, so in user controller, we will create an action having the name `create`.

	module.exports = {
			create: function(req, res) {
					return res.send("Hello world");
			}
	}

The above code overrides the create functionally, now if we send a http post request at url /user, instead of creating a new user it will send a response "Hello world".

In the similar manner we can override the default behaviour by creating actions having the name `create`, `update	` and `delete`.


## Policies
You don't want anyone accessing and performing unintended activity, like deleting all your real estates, so for that we have policies.
If you are familiar with ExpressJS, polices are similar to ExpressJS middle-wares.
The [official SailsJS documentation](http://sailsjs.org/#/documentation/concepts/Policies) explains policies in great detail, be sure to head over there and read about it in details.

# Conclusion
That's my take on SailsJS, it's a great framework to build apps in Node.JS.
Let me know if you have any suggestions, questions about this in the comments.



