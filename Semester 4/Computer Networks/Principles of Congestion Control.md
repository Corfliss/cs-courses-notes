# Causes and Costs of Congestion: Three Scenarios
## Cause
* Too many sources sending too much data too fast for network to handle
## Cost
* Long delays (queueing in router buffers)
* Packet loss (buffer overflow at routers)
## Scenarios
### Scenario 1
* One router, infinite buffers
* Input, outuput link capacity: R
* Two flows
* No retransmissions needed

### Scenario 2
* One rotuer, finite buffers
* Sender retransmits lost, timed-out packet
	* Application-layer input = application-layer output (lambda in = lambda out)
	* Transport-layer input includes retransmissions: lambda' in >= lambda in 

### Scenario 3
* Four senders
* Multi-hop paths
* Timeout/retransmit
# Approaches Towards Congestionn Control
## End-end Congestion Control
## Network-assisted Congestion Control

#ongoing 
