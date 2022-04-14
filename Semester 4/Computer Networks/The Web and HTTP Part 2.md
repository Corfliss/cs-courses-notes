# Web Caches
## How it Works
Caches is a process to satisfy client request without involving origin server.
* User configures browser to point to a (local) web cache.
* Browser sends all HTTP requests to cache
	* If object in cache: cache returns objject to client
	* Else cache request object from origin server, caches received object, then returns obect to client

## Web Caches (AKA Proxy Servers)
* Web cache acts as both client and server
	* Server for original requesting client
	* Client to origin server
* Server tells cache about object's allowable cachig in response header:
### Why Web Caching?
* Reduce response time for client request
	* Cache is closer to client
* Reduce traffic on an institution's access link
* Internet is dense with caches
	* enables "poor" content providers to more effectively deliver content
# Conditional HTTP GET
## Goal
* Don't send object if cache has up-to-date cached version
* No object transmission delay (or use of network resources)

## Behavior
* Client: specify date of cached copy in HTTP request
* Server: response contains no object if cached copy is up-to-date

# HTTP/2 and HTTP/3
## HTTP/2
### Goal
* Decreased delay in multi-object HTTP requests
* Increase flexibility at server in sending object to client:
	* Method, status codes, most header fields, unchanged from HTTP 1.1
	* Transmission order of requested objects based on cliene-specified object priority
	* Push unrequested objects to client
	* Divide objects into frames, schedule frames to mitigate HOL blocking.

## HTTP/3
### Goal
* Adding security, per object error- and congestion- control (more pipelining) over UDP
* More on HTTP/3 in transport layer.