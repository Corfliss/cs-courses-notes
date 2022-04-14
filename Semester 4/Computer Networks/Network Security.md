---
Zettelkasten: 260322 211631 +0700
---
# Bad Actors
## Packet "Sniffer"
* Using "sniffing" software, like Wireshark
* "Sniff" the package sent by recording all packages through the network
* Usually at broadcast media (Ethernet or wireless)

## Fake Identity
* Pretend to be the "good" person
* AKA Spoofing in internet security
* Injecting packet with false address
* Usually like phising emails that pretends to be a "good" person

## Denial of Service
* Overwhelming the server with overwhelming traffic congestion
* Making the server available because of that
* Breaks into hosts around targets (like botnet) to DDoS the target.

# Designs and Deployed Defenses
## For Spoofing: Authentication
* Using any available confirmation data to authenticate
* To prove the real user is

## For sniffing: 
* Encryption
	* To ensure confidentiality
	* Checksum256 is an example for that
* Integrity check
	* Using digital signature
	* Prevent tampering
* Password protection
	* Restrict access to certain "area"
	* Often like VPN

## For DoS: Firewalls
* Detecting DDoS attack
* "Middleman" of access and core networks.

# Reference
* [Jim Kurose's viddeo about Network Security](https://www.youtube.com/watch?v=yukwBqSwAkg)