---
Zettelkasten: 150222 083217 +0700
---
# Client-Server Paradigm
## Server
* Always-on host
* Permanent IP address
* Often in data centers, for scaling

## Clients
* Contact, communicate to the server
* May be intermittenly connected
* May have dynamic IP addresses
* Do not communicate directly with each other
* e.g.: HTTP IMAP FTP

# Peer to Peer Paradigm
* No always-on server
* Arbitrary end systems directly communicate
* Peers request service from other peers
* Provide service in return to other peers
* Peers are intermittently connected and change IP addresses
* e.g.: P2P file sharing

# Processes Communicating
* Process: program running within a host
* Within same host, two processes communicate using inter-process communication (defined by OS)
* Processes in different hosts communicate by exchanging messages.
* Client process initiates communication
* Server process waits to be contacted

# Sockets
* Process sends/receives messages to/from its socket
* Socket analogous to door
	* Sending process shoves mesage out door
	* Sending process relies on transport infrastructure on other side of door to deliver message to socket at receiving process
	* Two sockets involved: one on each side.

# Addressing Processes
* To receive messages, process must have identifier
* Host device has unique 32-bit IP address
* Identifier of address including IP address and port numbers

# What Defines Application-layer Protocol
* Types of messages exhanges
	* Request
	* Response
* Message syntax
	* Fields in messages
	* How fields are delineated
* Message semantics
	* Information in fields meaning
* Rules
	* When to process
	* How to process
	* When to respond
	* How to respond
* Open protocols
	* Defined in RFC (Respond for Comments)
	* Everyone has access to protocol definition
	* Allows for interoperability
		* HTTP
		* SMTP
	* Propriertary protocols
		* Skype
		* Zoom

# Needed Service for An App
* Data Integrity
	* Some apps requires 100% reliable data transfer
	* Other apps can tolerate some loss
* Timing integrity
	* Some apps requires low latency
* Throughput
	* Some apps requires certain bitrates
	* Other apps can be flexible
* Security
	* Encryption
	* Data integrity
# Internet Transport Protocols Services
## TCP Service
* Reliable Transport
	* Sending process
	* Receiving process
* Flow control
	* Sender don't overwhelm the receiver
* Congestion control
	* Throttle sender when network overloaded
* Connection-oriented
	* Setup required between client and server processes
* Does not provide
	* Timing
	* Minimum throughput guarantee
	* Security
## UDP Service
* Unreliable data transfer
* Does not provide
	* The rest of the TCP
	* Q: Why?
	* A: The rest of those TCP-like services can be build up

