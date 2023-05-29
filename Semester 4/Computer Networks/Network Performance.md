---
Zettelkasten: 140222 130434 +0700
---
# Components of Network Delay
## Nodal Processing
* Check bit errors
* Determine output link
* Typically < microsecs

## Queuing Delay
* Time waiting at output link for transmission
* Depends on congestion level of router
* a = average packet arrival rate
* L = packet length (bits)
* R = link bandwidth (bit transmission rate)
* L x a / R = arrival rate of bits/service rate of bits
* Above is equal to "traffic intensity"
	* ~ 0 = average queuing delay small
	* 1 = average queuing delay large
	* > 1 = average delay infinite

## Transmission Delay
* L = packet length (bits)
* R = link transmission rate (bps)
* L/R = transmission delay

## Propagation Delay
* d = length of physical link
* s = propagation speed (~2 x 10^8 m/s)
* d/s = propagation delay

# Traceroute: Looking at Network Delays
## Definition
* provides delay measurement from source to router along end-end Internet path towards destination.

## How
* For all i:
	* Sends three packets that will reach outer i on path towards destination
	* Router i will return packets to sender
	*  Sender measures time interval between transmission and reply

# Packet Loss
* Queue (AKA Buffer) preceding link in buffer has finite capacity
* Packet arriving to full queue dropped (AKA lost)
* Lost packet may be transmitted by
	* previous node
	* source
	* not at all

# Throughput
* Rates (bits/time unit) at which bits are being sent from sender to receiver
	* Instantaneous: rate at given point in time
	* Average: Rate over longer period of time
	* With multiple throughput passed, the maximum rate is the least throughput flow.
	* Above is called bottleneck link.

# Reference
