---
layout: post
title: PeerJS How does it work?

---

I was very excited about the latest Web RTC API's on Peer-To-Peer video calling and file transfer, and when I reading about these new API's I came accorss a awesome javascirpt plugin PeerJS, which allows to use the p2p data transfer easily.

I decided to use it for my screensharing app **deadsimplescreensharing**, becuase I am hosting the server on heroku and I am facing huge latency issues and I thought using peer-2-peer would be perfect to solve my problem, but sadly it didn't work!

### The Problem:
I modified my screensharing app's chrome extension to work with peerJS and also the client webpage.
Then I launched the localserver to test it, I got a connection with the extension I could see data being transmitted from the extension but not being recived at the client side.

I then tried to send small messages like "Hello", "Hi" etc. and I was able to recive them at the client just fine, so I figure out the problem was peerJS was unable to send large files (around 700 KB), and that part totally sucks!

### The Solution:
The possible soloution I could think about is converting the data:uri (screensharing fetch's the current tab image using data:uri) into an array and then dividing the array into smaller chunks and send them.
At the client side, recieve the chunks, join and assemble them and then display the image.

Here is the code which I used:

	var partialArray = []
	var partitionSize = 1000 //Size of each sub-array
	for(i=0; i < originalArray.length; i += partitionSize) {
		partitionArray.push(originalArray.slice(i, Math.min( i, partitionSize+1 )))
	}

The above code divides a large array into smaller arrays of size 1000 each which can be transmitter over the network.

### Conclusion
There is still lot of work that needs to be done in p2p file transfer or there is some serious issue with peerJS, as it cannot send large files and if it could the file transfer speed is very slow.
Still the thought of p2p connection is exiciting and I am wating for this new technology to develope so that we all can build cool applications using it
