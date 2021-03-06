---
Zettelkasten: 140222 141120 +0700
---
# Why Layering?
* Explicit structure allows identification, relationship of system's pieces
	* Layered reference model for dicusssion
* Modularization ease maintenance, updating system
	* Change in layer's service implementation: transparent to rest of system
	* Change in a procedure doesn't affect rest of system

# Stack of Internet Protocol
* Start at the top of the layer
* Go to bottom
* Move to another "end" device
* Start at the bottom of the layer
* Go to top

## Layers of Internet Protocol
### Application
* For network application
* HTTP
* IMAP
* SMTP
* DNS

### Transport
* Process-process data transfer
* TCP
* UDP

### Network
* Routing of datagram from source to destination
* Also considered as "best-effort" service, no guarantee to find the best routing
* IP
* Routing protocols

### Link
* Connecting either two ends of the same communication range
* Data transfer between two of it
* Ethernet
* Wifi (802.11)
* Point-to-Point Protocol (PPP)

### Physical: Bits "on the wire"

# Encapsulation of Internet Protocol
## Message
* Generated by application layer
* Contains message only.

## Segment
* Generated by the transport layer
* Contains message from application layer but added with header of the transport layer

## Datagram
* Generated by the network layer
* Contains segment from transport layer but added with header of the network layer

## Frame
* Generated by the link layer
* Contains datagram from the network layer but added with header of the link layer
* To be sent to destination via physical layer

# Encapsulation Stacking Example Journey
## Source
* Generate message
* Generate segment
* Generate datagram
* Generate frame
* Send to switch

## Switch
* Read the frame, making sure it's correct
* Continue to router

## Router
* Read the frame, making sure it's correct
* Read the datagram, making sure it's correct
* Pass the datagram
* Pass the frame
* Continue to destination

## Destination
* Read the frame
* Read the datagram
* Read the segment
* Read the message
* Display the message

# Reference
* [Jim Kurose's Video About Layering and Encapsulation](https://www.youtube.com/watch?v=IZ_PnVXtMeY)