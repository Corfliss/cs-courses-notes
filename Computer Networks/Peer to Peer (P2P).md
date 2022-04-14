---
Zettelkasten: 2022.04.04 21:32:03 +0700
---
# P2P Architecture
## What Is P2P?
* No always on server
* Arbitrary end systems directly communicate
* Peer request service from other peers, provide service in return to other peers
* Peers are intermittenly connected and change IP address
* Example:
	* P2P file sharing (BitTorrent)
	* Streaming (KanKan)
	* VoIP (Skype)

# Client Server vs P2P
Suppose there is a file sized F needs to be transfered into N devices, in this case. It's called peers. The upload speed from the server is Us and the minimal download speed is Dmin. While the peer download speed is Di and the upload speed is Ui
## Client Server Method
* Server transmission
	* Must sequentially upload files to the peers
	* To send to one peer: F/Us
	* To send to N peers: NF/Us
* Client download
	* At worst, it can be downloaded in Dmin speed.
	* To download from peer source: F/Dmin
* Time to distribute F to N clients using client-server approach (Dc-s)
	* Dc-s = Max{NF/Us, F/Dmin}
	* Explanation: It's either time send to N peers or download time from peer source.

## P2P Method
* Server transmission
	* To send to one peer: F/Us
	* Basically the same intro with the client-server method
* Client download
	*  To download from peer source: F/Dmin
	* Still the same until now
	* As aggregate must download NF bits
	* Max upload rate (limiting max download rate) = Us + Sum of all Ui (Sigma Ui) //Too lazy to write the LaTeX
	* Time to distribute F file to N peers using P2P approach
		* Dp2p>max{F/Us, F/Dmin, NF/(Us + Sigma Ui)}
		* Explanation: It's either the max of time to send to one peer, to download from peer source, or max upload rate.

# FYI: P2P vs Server-Client Method Speed Comparison
* ![[P2P vs Server-Client Speed Comparison.png]]
# P2P File Distribution
## How to Distribute
* File divided into 256Kb chunks
* Peers in torrent send/receive file chunks
* Two types of P2P devices
	* Torrent: Group of peers exchanging chunks of a file
		* As soon as the peer download a chunk, it can download another chunk from another torrent
	* Tracker: Server that tracks peers participating in a torrent
		* FYI: BitTorrent is using this, so it is not purely P2P, since using tracker server. But it has been improved with distributed tracker server.

## How To Add Another Peer
* New peer appear
* New peer obtain list
* New peer exchanging chunks

## How To Distribute (Continued)
* When new peer is connected
	* Has no chunk
	* Will accumulate the data over time
	* Register trackers to get list of peers
	* Connect to the subset of adjacent peers (AKA "neighbor")\
* While downloading, new peer upload chunks to other peers
* Peer may change peers with whom it exchange chunks
* Churn: peers may come and go
* Churn either leave (selfishly) or store (altruistically) 

# P2P Requesting and Sending File Chunks
## Requesting Chunks
* At any given time, there will be peers who has some chunks
* New peers can ask for list of chunks other peers may have
* The request starts from the rarest

## Sending Chunks
* The chosen four peers that new peer send chunks to will send the new peer the chunks needed at the highest rate
	* Other peers are choked by the new peer (do not receive chunk from it)
	* Reevaluate the top 4 every 10 seconds.
* Every 30 seconds, randomly selects another peer, start sending chunks
	* "Optimistically unchoke" this chunk
	* Newly chosen peer may join

## P2P Tit-for-Tat
* New peer request with "optimistically unchoke" to other peer
* New peer becomes one of the top 4 provider for the other peer.
* Vice versa happens too
* Increased transfer rate as the result

