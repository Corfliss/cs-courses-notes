---
Zettelkasten: 200322 103542 +0700
---
# UDP: User Datagram Protocol
* "No frilss", "bare bones" internet transport protocol
* "Best effort" service, UDP segemetns may be:
	* Lost
	* Delivered out-of-order to app
* **Connectionless**
	* No handshaking between UDP sender and receiver
	* Each UDDP segment handle indepenently of others
* Why is there a UDP?
	* No connection establishment (which can add RTT delay)
	* Simple: no connectinon state at sender, receiver
	* Small headder size
	* No congestion control
		* UDP can blast away as fast as desired
		* Can function in the face of congestion
* UDP use:
	* Streaming multimedia apps (loss tolerant, rate senstitive)
	* DNS
	* SNMP
	* HTTP/3
* If reliable transfer needed over UDDP (e.g., HTTP/3):
	* Add neededd reliability at application layer
	* Acc congestion control at application layer

# UDP: Transport Layer Actions
* UDP Sender actions:
	* Is passed an application-layer message
	* Determines UP segment header fields values
	* Creates UDP segment
	* Passes segment to IP
* UDP receiver actions:
	* Receives segment from IP
	* Checks UDP  checksum header value
	* Extracts application-layer message
	* Demultiplexes message up to application via socket

# UDP Segment Header
## UDP Segment Format
* Source port #
* Destination port #
* Length, in bytes of UDP segment including header
* Checksum
* Application data (payload), data to/from application layer

## UDP Checksum
* Goal is to detect errors like flipped bits in transmitted segment
* If there is an error like that:
	* Sender
		* Treat contents of UDP segment as sequence of 16-bit integers
		* Checksum: addition of segment content
		* Checksum value put into UDP checksum field
	* Receiver
		* Compute checksum of received segment
		* Check if computedd checksum equals checksum field value
			* Not equal - error detected
			* Equal - no error detected, or not?
		  