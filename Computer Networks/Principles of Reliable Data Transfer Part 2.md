---
Zettelkasten: 210322 005036 +0700
---

# rdt3.0: Channels with Errors and Loss
## How it Works
* New channel assumption: underlying channel can also lose packet (data or ACKs)
	* Checksum, squence of numbers, ACKs, retransmission will be of help
	* but not quite enough
	* Approach: sender waits "reasonable" amount of time for ACK
		* Retransmits if no ACK received in this time
		* if pkt (or ACK) just delayed (not lost):
			* Retransmission will be duplicate, but seq numbers already handles this. 
			* Receiver must specify sequence number of packet being ACKed
		* Use countdown timer to interrupt after "reasonable" amount of time
## rdt3.0 in Action
* If there is loss, there is a timeout time to resend from the sender
* Premature timeout existiting if the ACK message is too late with the timeout. Then the duplicate of the sender will be ignore

## rdt3.0 Performance (Stop and Wait)
* Sender: utilization - fraction of time sender busy sending
* E.g.: Example 1 Gbps link, 15 ms prop. delay, 8000 bit packet
	* Time to transmit packet into channel:
		* Dtrans = L/R = 8000/10^9 bits/sec = 8 ms
* rdt 3.0 protocol perforamance stinks

## rdt3.0: Pipelined Protocols Operation
* Pipelining, sender allowws multiple, "in-flight", yet to be acknowledged packets
	* Range of sequence numbers must be increased
	* Buffering at sender and/or receiver
* Increased utilization

# Go-Back-N: Sender
## How It Works
* Sender: "window" of up to N, consecutive transmitted but unACKed pkts
* Cumulative ACK: ACK(n): ACKs all packets up to, including seq # n
	* On receiving ACK(n): move window forward to begin at n+1
* Timer for oldest in-flight packet
* Timeout(n): restransmit packet n and all higher seq # packets in window

# How It Acts
* Suppose 4 sender is sends 4 pkt but 1 is lost
* The rest will be sent, but the lost pkt will be using timeout
* Then send like the rest

## Selective Repeat
### How It Works
* Receiver individually acknowledges all correctly received packets
	* Buffer packets, as needed, for eventual in-order delivery to upper layer
* Sender times-out/retransmits individually for unACKed packets
	* Sender maintains timer for each unACKed pkt

### Sender and Receiver
* Sender
	* data from above:
		* if next available seq # in window, send packet
	* Timeout(n)
		* Resend packet n, restart timer
	* ACK(n) in [sendbase, sendbase+N]:
		* Mark packet n as received
		* If n smallest unACKe packet, advance window base to next unACKe seq #
* Receiver
	* Packet n in [rcvbase, rcvbase+N-1]
		* Send ACK(n)
		* Out-of-order: buffer
		* In-order: deliver (also deliver buffered, in-order packet)
		* Avance window to next not-yet-received packet
	* Packet n in [rcvbase=N, rcvbase-1]
		* ACK(n)
	* Otherwise
		* Ignore


