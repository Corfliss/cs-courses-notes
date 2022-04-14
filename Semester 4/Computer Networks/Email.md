---
Zettelkasten: 250222 151502 +0700
---
# Infrastructure
## Components
* User agents
	* AKA "Mail reader"
	* Composing, editing, reading mail messages
	* e.g.: Gmail, Outlook
	* Outgoing, incoming messages stored on server
* Mail servers
	* Mailbox, contains incoming messages for user
	* Message queue of outgoing to be sent
* Simple Mail Transfer Protocol (SMTP)
	* Client: sending mail server
	* "server": receiving mail server

## Scenario
1. A uses UA to compose email message "to" B email
2. A UA sends message to her mail server using SMTP, message placed in message queue
3. Client side of SMTP at mail server opens TCP connection with B
4. SMTP client sends A's message over the TCP connection
5. B's mail server places the message in B's mailbox
6. B invokes his user agent to read messages

# SMTP
## SMTP Request for Comments (RFC)
* Uses TCP
* Reliably transfer email message
* From client (mail server initiating connection to server, port 25)
	* Direct transfer
		* Sending server (acting like client) to receiving server
* Three phases of transfer
	* SMTP handshaking (greeting)
	* SMTP transfer of messages
	* SMTP closure
* Command/response interaction (like HTTP)
	* Commands: ASCII text
	* Response:: status code and phrase

## SMTP Observations
* Comparison with HTTP
	* HTTP: client pull
	* SMTP: client push
	* Both have ASCII command/response interaction, status codes
	* HTTP: each object encapsulated in its own response message
	* SMTP: multiple objects sent in multipart message
	* SMTP uses persistent connections
	* SMTP requires message (header & body) to be in 7-bit ASCII
	* SMTP serer uses CRLF.CRLF to determine end of message

* Mail Message Format
	* SMTP
		* RFC 5321: protocol for exchanging email messages
		* RFC 2822: syntax for email message

* Retrieving Email
	* SMTP: delivery/storage of email messages to receier's server
	* Mail access protocol: retrieval from server
		* IMAP (Internet Mail Access Protocol) [RFC 3501]
			* Messages store on server
			* IMAP provides retrieval, deletion, folders of store messages on server