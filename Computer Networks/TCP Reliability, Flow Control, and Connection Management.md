---
Zettelkasten: 210322 090330 +0700
---
# TCP
## Overview
* Point-to-point
	* One sender, one receiver
* Reliable, in-order byte steam
	* no "message boundaries"
* Full duplex data
	* bi-directioal data flow in same connection
	* MSS: maximum segment size
* Cumulative ACKs
* Pipelining
	* TCP congestion and flow control set window size
* Connectionn-oriented
	* Handshaking (exchange of control messages) initializes sender
	* Receiver state before data exchange
* Flow controlled
	* Sender will not overwhelm receiver

## Segement Structure
* Source port # 
* Destination port #
* Sequence number
	* Byte stream "number" of first byte in segment's data
* Acknowledgement number
	* Seq # of next expectedd byte; A bit: this is an ACK
* Internet cheksum
* TCP options
* Data sent by appliation into TCP socket

## The RTT Timeout
* How to set TCP timeout value?
	* Longer than RTT, but RTT varies
	* Too short: premature timeout, unnecessary retransmissions
	* Too long: Slow reaction to segment loss
* How to estimate RTT?
	* SampleRTT: measured time from segment transmission until ACK receipt
	* We can estimate "smoother" RTT by average several recent measuremets, not just current SampleRTT
		* Estimated = (1-alpha) * EstimatedRTT + alpha * SampleRTT
		* Typically alpha = 0.125
	* Timeout interval of EstimatedRTT plus "safety margin"
		* TimeoutInterval = EstimatedRTT + 4 * DevRTT
		* DevRTT = (1-beta) * DevRTT + beta * | SampleRTT - EstimatedRTT |
		* Typically, beta = 0.25
## Sender
### When data received from application
* Create segment with seq #
* seq # is byte-stream number of first data byte in segment
* Start timer if not already running
	* Think of timer as for oldest unACKed segment
	* Expiration interval: TimeoutInterval

### When Timeout
* Retransmit segment that caused timeout
* Restart timer

### When ACK Received
* If ACK acknowledges previously unACKed segments
	* Update what is know to be ACKed
	* Start timer if there are still unACKed segments

## Receiver: ACK Generation
* ![[TCP Receiver - ACK Generation.png]]

## Flow Control
### In A Nutshell
* Receiver controls sender
* Sender won't overflow receiver's buffer
* No transmitting too much too fast

### How It Works
* TCP receiver "advertises" free buffer space in rwnd field in TCP header
	* RcvBuffer size set via socket options (Typical default is 4096 bytes)
	* Many operating systems autoadjust RcvBuffer
* Sender limit amount of unACKed ("in-flight") data to received rwnd
* Guarantees receive buffe will not overflow

## Connnection Management
### Before Exchanging Data
* Sender/Receiver "handshake":
* Agree to establish connection (each knowing the other willing to establish connection)
* Agree on connection parameters (e.g., starting seq numbers)
### Agreeing to Establish A Connection
* Will 2-way handshake always work in network?
	* Variable delays
	* Retransmitted messages due to messge loss
	* Message ordering
	* Can't "see" other side
* Solution: TCP 3-way handshake
### Closing a TCP Connection
* Client,s erver each close their side of connection
	* Send TCP segment with FIN bit = 1
* Respond to received FIN with ACK
	* On receiving FIN, ACK can be combined with own FIN
* Simultaneous FIN exchanges can be handled