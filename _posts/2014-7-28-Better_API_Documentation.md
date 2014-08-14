---
title: Better API documentations
layout: post
---

[![image](http://imgs.xkcd.com/comics/rtfm.png)](http://xkcd.com/293/)

It is a tedious job to write api documentations, and we have been using word documents and excel spreadsheets to create api documents.
But they are difficult to follow and search though, what if there was an easier and cleaner way to create API documents? When I started working on my latest project I was searching for an efficient way to write API documents and a way to generate beautiful documentations, my quest for finding the best api documentation tool lead me to [**API Blueprint**](http://apiblueprint.org).

## What is API Blueprint?
API blueprint is a language based on [Markdown](http://daringfireball.net/projects/markdown/) which allows you to write API documents clearly, moreover it has great tools which takes in your api blueprint document and convert it into beautiful html API documentation and much more.

### Useful tools:
Here are some tools which I find useful, that you can use with your api documentation written using [**API Blueprint**](http://apiblueprint.org). These tools make the API blueprint documents very powerful. There are tools generate beautify html documentations to even create mock api servers.

#### Creating Online documentation:
There is a web app called as [Apiary](http://apiary.io), which allows you to write in api blueprint format, and it generate beautiful online documentations, it also provide mock api server which will emulate your API based on the documentation, which is pretty useful if you don't have the API server ready yet and want to use the APIs for prototype the applications.
It will allow you to quickly build and test the API, without writing a single line of code.

#### API blueprint document into html documentation
There is an awesome tool called as [Aligo](https://github.com/danielgtaylor/aglio) which will allows to create beautiful html documentation from the api blueprint document.

#### API blueprint document into POSTMAN collection
A utility called as [Blueman](http://git.io/blueman) allows you to convert the api blueprint domination into [POSTMAN](https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm?hl=en) collection, which you can import into your [POSTMAN REST Client](https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm?hl=en).

#### Local Mock Server
[API Blueprint Mock Server](https://bitbucket.org/outofcoffee/api-blueprint-mockserver) create a local api mock server using the api blueprint which you have provided, which you can use to prototype REST APIs.
