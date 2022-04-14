---
Zettelkasten: 190322 185746 +0700
---
# Difference
* Demultiplexing
	* In short, one to many. Dispersing.
* Multiplexing
	* In short, many to one. Funneling.

# Multiplexing/Demultiplexing
* Multiplexing at sender:
	* Handle data from multiple sockets, add transport header (later used for demultiplexing)
* Demultiplexing at receiver:
* Use header info to deliver received segments to correct socket

# How Demultiplexing Works
## Nutshell
* Host receives IP datagrams
	* Each datagram has source IP address, destination IP address
	* Each datagram carries on transport-layer segment
	* Each segment has source destination port number
* Host uses IP addresses and port numbers to direct segment to appropriate socket
## Conectionless Demultiplexing
* When creating socket, must specify host-local port #:
* When creating datagramto send into UDP socket, must specify
	* Destination IP adress
	* Destination port # 
* When receiving host receives UDP segment
	* Checks destination port # in segment
	* Directs UDP segment to socket with that port # 
		* IP/UDP datagrams with same destination port number
		* Different source IP addresses and/or port numbers will be directed to same socket at receiving host
## Connection-oriented Demultiplexing
* TCP socket identified by 4-tuple:
	* Source IP address
	* Source port number
	* Destination IP address
	* Destination port number
* Demux: receiver uses all four values to direct segment to appropriate socket
* Server may support many simulatneous TCP sockets:
	* Each socket identifiedd by its own 4-tuple
	* Each socket associated with a different connecting client
