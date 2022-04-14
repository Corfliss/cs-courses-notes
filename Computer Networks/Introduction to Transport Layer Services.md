---
Zettelkasten: 190322 183933 +0700
---
# Things To Learn
* Understand principles behind transport layer services
* Learn about internet transport layer protocol

# Transport Services and Protocols
* Provide logical communication between application processes running on different hosts
* Transport protocols actions in end systems
	* Sender: breaks application messages into segmets, passes to network layer
	* Receiver: reassembles segments into messages, passes to application layer
* Two transport protocols available to internet applications
	* TCP, UDP

# Transport vs Network Layer Services and protocols
* Host = houses
* Processes = kids
* App messages = letters in envelopes
* Transport protocol = A and B who demux to in-house sibilings
* Network-layer protocol = postal service
* Network layer = logcoal communicationn betweenn hosts
* Trasnport layer: Logical communication between processes
	* Relies on, enhances, network layer services

# Transport Layer Actions
* Sender:
	* Passed an application layer message
	* Determines segment header fields values
	* Creates segment
	* Passes sgement to IP
* Receiver
	* Receives segment form IP
	* Cehcks header values
	* Extracts application-layer message
	* Demultiplexes messages up to application via socket

# Two Principla Internet Transport Protocols
* TCP: Transmission Control Protocol
	* Reliable, in- order delivery
	* Congestion control
	* Flow control
	* Connection setup
* UDP: User Datagram Protocol
	* Unreliable, unordered delivery
	* No-frills extension of "best-effort" IP
* Services not available:
	* Delay guarantees
	* Bandwidth guarantees