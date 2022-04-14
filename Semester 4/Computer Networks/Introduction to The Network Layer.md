---
Zettelkasten: 230322 130637 +0700
---
# Introduction
## Network-layer Services and pProtocols
* Transport segment from sending to receiving host
	* Sender: encapsulates segments into datagrams, passes to link layer
	* Receiver: delivers segments to transport layer protocol
* Network layer protocols in every Internet device: osts , routers
* Routers
	* Examines header field in all IP datagrams passing throughit
	* Moves datagrams from input ports to output ports to transfer datagrams along end-end path
* Incubation notes: This is similar to to the introduction in Chapter 1

## Two Key Network-layer functions
* Analogy: taking a trip
	* Forwarding is a process of getting through single interchange
	* Routing is a process of planning trip from source to destination

## Data Plane and Control Plane
### Data plane:
* Local, per-router function
* Determines how datagram arriving on routerinput port is forwarded to router output port
### Control Plane
* Network-wide logic
* Determines how datagram is routed among routers along end-end path from source host to destination host
* Two control-plane approaches:
	* Traditional routing algorithms that is implemented in routers
	* Software-defined networking (SDN) that is implemented in (remote) servers

## Network Service Model
* Example services for individual datagrams
	* Guaranteed delivery
	* Guaranteed delivery with less than 40 ms delay
* Example services for a flow of datagrams
	* In-order datagram delivery
	* Guaranteed minimum bandwidth to flow
	* Restrictions on changes in inter-packet spacing
* ![[Network-layer Service Model.png]]

* Reflections
	* Simplicity of mechanism has allowed internet to be widely deployed and adopted
	* Sufficient provisioning of bandwidth
	* Replicated, application-layer distributed services
	* Congestion control of "elastic" services helps

This was taken in the class within the same date.