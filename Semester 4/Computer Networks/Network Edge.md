---
Zettelkasten: 090222 211223 +0700
---
# What is Network Edge?
Network edge is basically the endpoint of the internet in which it is interfacing with. This includes, PC, smartphone, and IoT objects like smart cars, and smart fridge. (Probably you can play Skyrim on your smart fridge). It is connected to the access network in which will be conected to the internet.

# How Network Edge Connected?
* Residentail access nets
* Institutional access nets (like schools or company)
* Mobile access network (Wifi, 4G/5G)

## Cable Based Access
It uses Frequency Division Multiplexing (FDM). To better understand it, it is similar with the usage of FM radio, where the edge connected to certain frequency in order to get the data needed. To summarize, it is reading channel which is transmitted in different frequency bands.

Usually, it uses Hybrid Fiber Coaxial (HFC), where it transmit the data asymmetrically. Notably from 40 Mbps to 1.2 Gbps for download and 30 Mbps to 100 Mbps for dowload. This might makes us more of a consumer of data rather than maker of data.

## Digital Subscriber Line (DSL)
It is an access network that uses existing telephone line to central office with DSL access multiplexer (DSLAM) at a place, called the central office. Data from the DSL phone line is goes to the internet, while voice over DSL phone line goes to telephone net.

Usually it is about 24-52 Mbps download and 3.5-16 Mbps upload, but the further you acess the internet using DSL from the central office, the slower it is to have the bandwith of the internet.

## Home Networks
For starter, there is a cable that is conected to the central office in both direction, and then it is connected to cable of DSL modulator demodulator (DSL modem). And then modem will be connnected to the router and finally to the WiFi wireless access. 

If the computer directly connected to the router, it is a wired ethernet (1Gbps). If it is connected to the WiFi wireless access, it is basically what we called as wifi connection (54 to 450 Mbps).

## Wireless Access Networks (In a Big Picture)
There are two types of wireless acess networks, one is about Wireless Local Area Networks (WLAN) and Wide-area cellular access networks.

### WLAN
Operate in the range of ~30m (100ft) (Idk about American measurement s Metric, so cmiiw). Optimally, it may vary depending how much you pay (e.g.:11, 54, 450 Mbps)
Example:
* Wifi

### Wide-area Cellular Access Networks.
Provide by mobile celullar operator. Operate in 10km 
Optimally, 10 Mbps
Example:
* 4G/5G

## Enterprise Networks
* Basically on home networks on steroids.
* Combines home networks, and mix of switches and routers.
* Speed variation
	* Ethernet: 100 Mbps to 10 Gbps
	* Wifi: 11 to 450 Mbps

# Packets of Data
How the packets is send.
* Takes the data to send
* Breaks to chunks called packet.  Usually in a certain amount of bits (L)
* Transmit packet into access network at a certain transmission rate (R)
	* Also known as Bandwith
* Packet transmission delay = time needed to go insert chunks to link =  L/R

# Physical Media of Networks
To transfer bits into a physical links, there are two ways. One is with guided media, and the other one is unguided media

## Guided Media
This includes: 
* Copper wire
* Fiber optics
* Coaxial cable

## Unguided Media
This includes wireless radio such as:
* Wifi
* 4G/5G
* Bluetooth
* Terrestrial microwae
* Satellite

Reference:
[Jim Kurose's Video: The Network Edge](https://www.youtube.com/watch?v=k8NmM-hImBU)