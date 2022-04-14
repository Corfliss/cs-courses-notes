---
Zettelkasten: 200322 105924 +0700
---
# Reliable Data Transfer (RDT) Protocol Interfaces
* rdt_send(): called from above liek by app. Passed ata to deliver to receiver upper layer
* udt_send(): called by rdt to transfer packet over unreliable channel to receiver
* rdt_rcv(): called when packet arrives on receiver side of channel
* deliver_data(): called by rdt to deliver data to upper layer

# rdt1.0: Reliable Transfer over A Reliable Chanel
* Underlying channel perfectly reliable
	* No bit errors
	* No loss of packets
* Separate FSM for sender, receiver:
	* Sender sends data into underlying channel
	* Receiver reads data from underlying channel

# rdt2.0: Channnel with Bit Errors
## General
* Underlying channel may flip bits in packet
	* Checksum to detect bit errors
* The question: how to recover  from errors?
	* Acknowledgements (ACKs): receiver explicitly tells sender that pkt received OK
	* Negative acknowledgments (NAKs): receiver explicitly tells sender that pkt had errors
	* Sender retransmits pkt on receipt of NAK

## FSM Specification 
* Two FSM.
	* Wait for call from above (1)
	* Wait for ACK or NAK (2)
	* From (1) to (2)
		* if (rdt_send(data))
			* snkpkt = make_pkt(data, checksum)
			* udt_send(sndpkt)
	* From (2) to (1)
		* rdt_rcv(rcvpkt) && isACK(rcvpkt)
			* Transitioning
	* From (2) to (2)
		* if (rdt_rcv(rcvpkt) && isNAK(rcvpkt))
			* udt_send(sndpkt)
* FSM of receiver
* if (rdt_rcv(rcvpkt) && corrupt(rcvpkt))
	* udt_send(NAK)
* if (rdt_rcv(rcvpkt) && notcorrupt(rcvpkt))
	* extract(rcvpkt, data)
	* deliver_data(data)
	* udt_send(ACK)

## Fatal Flaw
* ACK/NAK can be corrupted
	* Sender cannnot know what happened at receiver
	* Can't just retransmit; possbile duplicate
* Handling duplicates
	* Sender retransmits current pkt if ACK/NAK corrupted
	* Sender adds sequence number to each pkt
	* Receiver discards (doesn't deliver up) duplicate pkt

# rdt2.1: Sender, Handling Garbled ACK/NAKs
## FSM Specification
* Wait for call 0 from above (1)
* Wait for ACK or NAK 0 (2)
* Wait for ACK of NAK 1 (3)
* Wait for call 1 from above (4)

## FSM Connection
### From (1) to (2)
* if (rdt_send(data))
	* sndpkt = make_pkt(0, data, checksum)
	* udt_send(sndpkt)

### From (2) to (4)
* if (rdt_rcv(rcvpkt) && not corrupt(rcvpkt) && isACK(rcvpkt)
	* Transitioning

### From (4) to (3)
* rdt_send(data)
	* sndpkt = make_pkt(1, data, checksum)
	* udt_send(sndpkt)

### From (3) to (1)
* if (rdt_rcv(rcvpkt) && notcorrupt(rcvpkt) && isACK(rcvpkt))
	* Transitioning

### From (2) to (2)
* rdt_rcv(rcvpkt) && (corrupt(rcvpkt) || isNAK(rcvpkt))
	* udt_send(sndpkt)

## Another FSM Configuration
* Wait for 0 from below (1)
* Wait for 1 from below (2)

## FSM Connection
### From (1) to (2)
* if (rdt_rcv(rcvpkt) && notcorrupt(rcvpkt) && has_seq0(rcvpkt))
	* extract(rcvpkt, data)
	* deliver_data(data)
	* sndpkt = make_pkt(ACK, chksum)
	* ut_send(sndpkt)
### From (2) to (1)
* if (rdt_rcv(rcvpkt) && notcorrupt(rcvpkt) && has_seq1(rcvpkt))
	* extract(rcvpkt, data)
	* deliver_data(data)
	* sndpkt = make_pkt(ACK, chksum)
	* ut_send(sndpkt)

## From (2) to (2)
* if (rdt_rcv(rcvpkt) && corrupt(rcvpkt))
	* sndpkt = make_pkt(NAK, chksum)
	* udt_send(sndpkt)
* if (rdt_rcv(rcvpkt) && notcorrupt(rcvpkt) && has_seq0(rcvpkt))
	* sndpkt = make_pkt(ACK, chksum)
	* udt_send(sndpkt)

## From (1) to (1)
 * if (rdt_rcv(rcvpkt) && corrupt(rcvpkt))
	* sndpkt = make_pkt(NAK, chksum)
	* udt_send(sndpkt)
* if (rdt_rcv(rcvpkt) && notcorrupt(rcvpkt) && has_seq1(rcvpkt))
	* sndpkt = make_pkt(ACK, chksum)
	* udt_send(sndpkt)
