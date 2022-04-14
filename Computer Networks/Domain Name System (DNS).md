# Introduction
To map between IP address and the name of the website and vice versa, it needs Domain Name System (DNS), it is a distributed database implemented in hierarchy of many name servers that communicates with each other. This is also an application-layer protocol, implemented at the network's "edge"

# DNS Structure and Function
## DNS Service
* Hostname-to-IP-address translation
* Host aliasing
	* Canonical, alias names
* Mail server aliasing
* Load distribution
	* Replicated web servers: many IP address correspond to one name
* Not centralized because
	* Single point of failure
	* Traffic volume
	* Distant centralized database
	* Maintenance
* DNS doesn't scale.

## How to Think DNS
* Humongous distributed database:
	* Trillion simple records of queries
* Handless many trillions of queris/day
	* Many more reads than writes
	* Performance matters
		* Almost every internet transaction interacts with DNS
		* msecs count!
* Organnizationally, physically decentralized
	* Million of different organizations reponsible for their record
* "Bulletproof" to attacks

## DNS: A Distributed, Hierarchical Database
![[DNS Hierarchy.png]]
### How Client Gets IP Address of A Website Name with thatwebsite.com
* Client queries root server to find .com DNS server
* Client queries .com DNS server to get the DNS server of thatwebsite.com
* Client queries thatwebsite.com DNS server to get IP address for it.

### DNS: Root Name Servers
* Official, contact-of-last-resort by name servers that can not resolve name
* **Incredibly Important** Internet Function
	* Internet couldn't function without it!
	* DNSSEC - provides security (authentication, message integrity)
* Root DNS domain is managed by ICANN (Internet Corporation for Assigned Names and Numbers)

### Top-Level Domain (TLD), and Authoritative Servers
#### TLD Servers
* Responsible for .com, .org, .net, etc. and country domains like .id, .jp, etc.
* Network Solutions: Authoritatve Registry for .com, .net. TLD

#### Authoritatvie DNS Servers
* Organizaton's own DNS server(s), providing authoritative hostname to IP mapping for organization's named hosts
* Can be maintained by organization or service provider

### Local DNS name servers
* When host makes DNS query, it is sent to its local DNS server
	* Local DNS server returns reply, answering:
		* From its local cache of recent name-to-address translation pairs (possibly out of date)
		* Forwarding request into DNS hierarchy for resolution
	* Each ISP has local DNS name server.
# Resolving DNS queries
## Iterated Query
* Contacted server replies with name of server to contact
* "I don't know this name but ask this server"
* Steps for host at a.com to b.com
	1. a.com sends query to local DNS server
	2. Local DN serversends queries to root DNS server
	3. Root DNS server resends sends DNS responsible for .com to local DNS server
	4. Local DNS server sends query to TLD DNS server
	5. TLD DNS server resends DNS responsible for b.com
	6. Local DNS server sends queries to authoritative DNS server for b.com
	7. That authoritative DNS server sends DNS of b.com to Local DNS server
	8. Local DNS server sends DNS of b.com to host at a.com

## Recursive Query
* Puts burden of name resolution on contacted name server
* Heavy load at upper level of hierarchy?

## Caching DNS Information
* Once (any) name server leans mapping, it caches mapping, and immediately returns a cached mapping in response to a query
	* Caching imporves response time
	* Cache entries timeout (disappear) after some time (TTL)
	* TLD servers typically cached in local name serers

# DNS Record Format
* Formatted in resource records (RR) format: (`name`, `value`, `type`, `ttl` (Time to live))
	* Type A
		* `name` is hostname
		* `value` is IP address
	* Type NS
		* `name` is domain
		* `value` is hostname of authoritative name server for this domain
	* Type CNAME
		* In case you want to do a backup
		* `name` is alias for some "canonical" (the real name)
		* `value` is the canonical name
	* Type MX
		* `value` is the name of SMTP mail server associated with `name`

# DNS Protocol Messages
## DNS Formatting
Query and reply message, both have the same format, which consist of:
* Message header
	* Identification: 16 bit numbers of query, reply to query uses same number.
	* Flags: Is it...
		* Query or reply
		* Recursion desire
		* Recursion available
		* Reply is authoritative
	* Variable number of questions which consist of name, typefields of the query
	* Answers with variable number of RRs in response to query
	* Authority with variable number of RR records for authoritative servers
	* Additional info that may be used

## Getting Your Info Into DNS
* Register the website to DNS registrar (Some sort of network solutons provider)
	* Provide this for the authoritave name server
		* Name
		* IP address
	* Registrar inserts NS and A RRs into .com TLD server:
		* NS example: (nyeheheh.com, dns1.nyeheheh.com, NS)
		* A exmaple: (dns1.nyeheheh.com, 123.123.123.111, A)
* Create authoritatve server locally with IP address on the A example (123.123.123.111)
	* Type A record for [www.nyeheheh.com]
	* Type MX record for nyeheheh.com

## Protect DNS at All Cost
* DDoS attacks
	* Bombards root servers with traffics
	* Bombards TLD servers with traffics (more dangerous)
* Spoofing attacks.

# Reference
[Jim Kurose's Video About DNS](https://clips.twitch.tv/HelpfulDullChipmunkPogChamp-woyHb3ozqRaca3FW)
