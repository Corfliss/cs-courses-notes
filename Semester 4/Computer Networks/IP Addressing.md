---
Zettelkasten: 230322 135013 +0700
---
# IP addressing Structure
* Describe the dotted decimal structure of a binary OP address and label its parts
* Describe the general role of 8-bit binary in network addressing and convert 8-bit binary to deci
* An IP address consists of 32 bits, grouped into four octets
* Convert 8-bit binary to decimal
* Convert decimal to 8-bit binary

# Classify an Define IPv4 Addresses
* Name the three types of addresses in the network and describe the purpose of each type
* Identify the address ranges reserved for these special purposes in the IPv4 protocol
* Identify the historic method for assigning addresses and the issues associated with the method

# Subnetting
* Used to partition the given address space into smaller, manageable sizes
* IP networks can be divided into smaller networks called subnetworks (or subnets)
* Subnetting provides the netwrok administrator with several benefits
	* Extra flexibility
	* More efficient use of netwrok addresses
	* The capability to contain broadcast traffic (a broadcast will not cross a router)
* Subnet enables to chunk networks for easier management
## Type
### Static Subnetting
* A portion of host address bits are used as subnetwork address bits
* The "dividing line" between network address and host address parts is shifted variably to the right
* Example
	* ![[Before and After Subnetting.png]]
#### Subnet Mask
* A subnet is defined by applying the subnet mask to the IP address
* If a bit is "on" (set to 1) in the subnet mask, then that equivalent bit in the address is interpreted as a network bit
* If a bit is "off" (set to 0) in the subnet mask, then that equivalent bit in the address is interpreted as a host bit
* Standard subnet masks for the 3 classes of addresses
	* Class A address - 255.0.0.0
	* Class B address - 255.255.0.0
	* Class C address - 255.255.255.0

#### How to Determine Network Portion
* 
### Variable Length Subnet Mask (VLSM)
* Variable length is the more flexible of the two
* ![[Without VLSM by Example.png]]
* ![[Answer of Without VLSM Example.png]]

	