---
Zettelkasten: 090222 233405 +0700
---
# What is Network Core?
Basically, mesh of interconnected routers on the internet.

# Network Core Function
There are two functions of network core

## Forwarding 
* AKA Switching
* Move arriving package from routers to the appropriate router output lik
* Local action

## Routing
* Determine the source-destination paths taken by packets
* Using routing algorithms
* Global action

# Packet-switching
* Store and forward
	* putting every package at router before it is transmitted on the next link.
* Queuing
	* When many edges transmit chunks of different data in the same router, hence making a queue.
	* Happens because transmission to another router is slower than the edge to a router.
	* The chunk can be queued first in first out (FIFO), depending on the transmission arrival.
	* If that happens, it can:
		* queue, waiting to be transmitted
		* loss, if memory (buffer) in router fills up

# Circuit-switching
* Alternative to packet-switching
* Make a dedicated path from source-to destination
* No interference
* Like a "call"
* Makes it unable to do another transmission
* Commonly in traditional telephones

## Types of Circuit-switching
### Frequency Division Mutliplexing
* "Horizontal" division
* Divided into narrower frequency bannds
* Max rate: that narrow band.

### Time Division Multiplexing
* "Vertical" division
* Max rate: the whole band
* Available for only certain amount of time

# Packet-switching vs Circuit-switching
Packet swtiching is good for "bursty" data.
* Resource sharing.
* Simpler no call setup
* Excessive congestion possible

# Internet Structure
* With millions of ISP, connecting each other will requires bazillion amount of connection
* Alternative: global ISP
* Reality: many ISP businesses, so requires Internet Exchange Points (IXP)
## Components of Internet Business
* Tier-1 commercial ISPs
* Content provider networks

Reference:
[Jim Kurose's YouTube video: The Network Core](https://www.youtube.com/watch?v=f1nUcCdQJ8Y)