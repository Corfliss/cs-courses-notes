---
Zettelkasten: 260322 222443 +0700
---
# Video Characteristics
* In internet
	* Major users of internet bandwith
	* Covers 80% of residential ISP traffic (2020)
	* 1B users
* Challenge of Video Streaming
	* How to acommodate 1B users?
	* How to cover the heterogeneity of the video streaming?
	* Server-to-client bandwidth will vary over time
	* Packet loss, delay due to traffic congestion
* Solution
	* Distributed, application-level infrastructure
* In A Description
	* Video: sequence of images displayed at constant rate.
	* Image: Array of array of pixels
	* Encoding: Use redundancy within and between images to decrease the number of bits
		* Example: Spatial coding
		* Example: Temporal coding
		* Type: CBR (Constant bit rate)
		* Type: VBR (Variable bit rate)

# Streaming Stored Video
## How It Works
* Video recorded
* Video record done
* Video broadcasted
* Before the video is finish broadcasting, the video received in the "end" device
* Streaming
	* End device is receiving early part
	* Server still sending later part

## Challenge
### Continuous Playout Constraint
* Client video playout = playout original timing
* Network delays are variable (jitter)
* Need client-side buffer to match the playout timing

### Other Challenge
#### Client Interactivity
* Pause
* Fast-forwad
* Jump
* Rewind

#### Video Packet Loss
* How to transmit it back with minimum delay.

##  Playout Buffering
* Using buffering time on the client-side
* To fix the jittery video transmission
* The buffering time may vary

# DASH (Dynamic, Adaptive Streaming over HTTP)
## Server-side
* Divides video file into multiple chunks
* Each chunk encoded at multiple different rates
* Different rate encodings stored in different files
* Manifest file: provides URLs for different chunks

## Client-side
* Periodically estimates server-to-client bandwidth
* Consulting manifest, requests one chunk at a time
	* Chooses maximum coding rate sustainable given current bandwidth
	* Can choose different coding rates at different points in time (depending on available bandwidth at time), and from different servers
* Client determines
	* When to request chunk
	* What encoding rate
	* Where to request chunk (can request from URL server that is "close" to client or has high available bandwidth)

# CDN and Example
## Challenge: how to stream content (selected from millions of videos to hundreds of thousands of simultaneous users)?
* Option 1: single, large "mega-server"
	* Single point of failure
	* Point of network congestion
	* Long (and possibly congested) path to distant clients
	* Cons: doesn't scale
* Options 2: store/serve multiple copies of videos at multiple geographically distributed sites (CDN)
	* Enter deep: push CDN servers deep into many access networks, close to users.
	* Bring home: smaller number (10's) of larger clusters in POPs near access nets

# Reference
[Jim Kurose's Video About Video Streaming and Content Distribution Network](https://www.youtube.com/watch?v=ak5bbb-xHLI)

