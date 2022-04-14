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
* 
# DASH (Dynamic Client-Driven Streaming)
# CDN and Example

# Reference
[Jim Kurose's Video About Video Streaming and Content Distribution Network](https://www.youtube.com/watch?v=ak5bbb-xHLI)

