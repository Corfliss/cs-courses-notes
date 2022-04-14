---
Zettelkasten: 170222 085410 +0700
---
# Web, HTTP Overview
## Overview
* HTTP stands for Hypertext Transfer Protocol
* Web's application layer protocol
* Client-Server model
	* Client (like a browser)
		* Request
		* Receives (with HTTP protocol)
		* "Displays" Web objects
	* Server
		* Sends (with HTTP protocol) objects
		* Respond to requests
* Uses TCP, here's how:
	* Client initiates TCP connection (creates socket) to server, port 80
	* Server accepts TCP connection from client
	* HTTP messages (application-layer protocol messages) exchanged between browser (HTTP client) and Web server (HTTP server)
	* TCP connection closed
* "Stateless"
	* Server maintains no informatino about past client requests
# HTTP Connection Types
## Non-persistent HTTP
### Characteristics
1. TCP connection opened
2. At most one obect sent over TCP connection
3. TCP connection closed
* To download multiiple objects required multiple connections
### How It Works
1. HTTP client
	* Initiates TCP connection
	* Destination:
		* HTTP server (process) 
		* At a website on certain port
2. Simultaneously, HTTP server at host website
	* waiting for TCP connection at a certain port 
	* "Accepts" connection 
	* Notifying client
3. HTTP client (again)
	* Sends HTTP request message
		* Containing URL
	* Destination
		* TCP connection socket
	* Message indication
		* Client wants object
		* Object is at a certain website
4. HTTP server (again)
	* Receives request message
	* Forms response message
	* Contains requested object
	* Send message into its socket
	* Close TCP connection
5. HTTP client (again)
	* Receives response message
		* Containing HTML file
	* Displays HTML
	* Parsing HTML File
	* Find objects to be displayed
6. Repeat for each 10 JPEG objects

### Response time
#### RTT (Round Trip Time) Definition
* Time for a small package travel
*  From client to server and back
#### HTTP Response Time (Per Object)
* One RTT to initiate TCP connection
* One RTT for
	*  HTTP request 
	* first few bytes of HTTP response to return
* Object/file transmission time
* Total time for this: 2(RTT) + File transmission time

## Persistent HTTP
### Characteristics
1. TCP connnection opened to a server
2. Multiple obects can be sent over single TCP connection between client and that server
3. TCP connection closed
* This one can download more objects
### How It Works
1. Server leaes connectionn openn after sending resposne
2. Subsequent HTTP messages between same client/server sennt over open connection
3. Clients sends requests as soon as it encounters a referenced object
4. As little as one RTT for all the referenced objects (cutting respose time in half)

# HTTP Messages
There are to types of HTTP messages: request and response

## Request
* ASCII (human-readable format)
* General format
	* Request Line
		* GET
			* Include user data in URL field of HTTP GET request (like a '?')
		* POST
			* Web page often includes form input
			* User input sent from client to server in entity body of HTTP POST request maessage
		* HEAD
			* Request headers (only) that would be returned if specified URL were requested with an HTTP GET method
		* PUT
			* Uploads new file (object) to server
			* Completely replaces file that exists at specified URL with content in entitiy body of POST HTTP request message
	* Header lines
	* Body

## Response
* Status line (protocol status code status phrase)
	* Example of sample codes
		* 200 OK
		* 301 Moved Permanently
		* 400 Bad Request
		* 404 Not Found
		* 505 HTTP Version Not Supported
* Header lines
* Data

# HTTP Cookies
Web Sites and client browser use cookies to maintain some state between transaction

## Components
1. Cookie header line of HTTP response message
2. Cookie header line in next HTTP request message
3. Cookie file kept on user's host, managed by user's browser
4. Back-end database at Website