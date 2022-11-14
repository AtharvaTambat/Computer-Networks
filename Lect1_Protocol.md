# Protocol
Rules for transmission and formatting of data

# Internet
## Physical layer of protocols
two neighbours in a network and you have to communicate - say, denoising is a part of protocols at the physical layer

## 5 people joined through a bus
1. Bus - a common wire joining all the systems - information about sender and receiver is needed
2. Possiblitly for interference on the bus - medium access - when different users access same medium - make sure the information do not interefere with each other
3. **Medium access** and **framing** - comes under a set of protocols - **Data link layer** 

## Beyond 5 people - thousand people on a bus
1. Medium access problems become huge 
2. Length of problem beomes huge
3. Amplification may be a problem
4. **SWITCHES** - isolator - added in the middle and selectively formward messages to the other side based on which user is on the other end - protocols for the switch are considered under data link layer

## 1 million people
Term used for a small network is a LAN (Local Area Network)

1. Resources might be geographically far apart - cannot use bus (single wire) to connect all
2. IP protocols are used to connect all the LANS - each router has an IP address

### IP Address
IP Packet - the message to be sent is caled the IP packet - consists of sender, receiver and information

### Message being sent between two people 
1. Signal - to let the user know that information is being sent - **Physical Layer**
2. Framing bits - Data link layer header
3. IP Header - sender and receiver
4. Transport layer
5. Information to be sent

At each layer there are different challenges to be solved - which have ifferentr protocols associated with them

### Five layer model of Protocal Stack
1. **Physical Layer**
2. **DLL**
3. **Network (IP)**
4. **Transport Layer**
5. **Application layer**

### Network 
Routers - Layer 3 "Switches" - because operating at layer 3 of five layer internet protocol stack 

1. Routers job is to see the IP header of the packet and to see where to forward it to 
What protocols to use for this? 
1. BGP
2. ISIS/ OSPF 
Layer 3 protocols which solve the problem of "routing" where to send (route) a packet so that it reaches the destination - if poorly implemented, the packet might go round and round in a loop

## Zoom into a router
Say a lot of packets are coming at different links - incoming rates at all links are same - and if all the packets are sent ot the same output link - output link canoot handle this high rate of data.

1. One solution is discard some of the packet - message wont reach the destination
2. Another solution - Queues - buffer the packets in the queues

3. It might happen that the queue gets filled up and you might have **packet loss** - we do have some packet loss 

### Retransmission of lost packets
Loss of packets - layer 3 problem - might happen due to medium loss or queue filling up
1. one solution is  - **retransmissions**
2. Say A sends a packety which gets lost at some router - solution is that A retransmits the packet till B receives it 
3. Might not be the most effecient solution - retransmittion by the router immediately before might be more effecient 
4. A (sender) must detect the loss and retransmits - B (receiver) has to send packets back as acknowledgments - which happens at the **TRANSPORT LAYER**
5. Protocols for this are TCP (in the original internet it ws UDP)

## Protocol Layering
Each layer will have a set of protocols to hadle problems t that layer

1. OSI-7 
2. Application layer handles app (eg. whatsapp)
3. Transport and Network layer - implemented on the OS - TCP/ IP 
4. DLL and Physical layer - implemented on NIC - network interface card

Eg. Whatsapp 
1. Packet starts at application layer - the information to be sent
2. Transport layer - adds information (header) for identificaton of the packet - passes it on to the network layer
3. Network layer adds its own header (IP) 
4. Passed on to the DLL - yet another header is added - takes care of medium acces and fading
5. Passed on to the physical layer - which converts this into a signal
6. signal is sent into the wire for transmission
7. Going to go to the **base station** - tower - might not have all the protocols implemented in it (will not have the **application layer**, the transport are implemented by end users only - so it does not have that also) - only has **lower 3 layers** (Network, DLL, physical). there might be some devices at the base station - **Repeater** - Which only have the physical layer - also there are **Layer 2 switches** (DLL and Physical layers implemented) (only cares about the bottom 2 layers)
8. Base station will strip off the Physical layer, DLL and hand the packet over to the network layer - which will see the IP header of the packet and decide where to send the message to next
9. The packet has to be sent down the stack again - which adds the DLL and Physical header again (new) (higher information layer is not tampered with) and sends it to the other node in the network
10. At the end server - it is going to go all the way up to the application layer - the message will be sent again to your friend's mobile 

# Advantages and Disadvantages of Protocol Layering
## Advantages
1. Decompose the entire problem set is divided into smaller problems
2. Modular design - all the layers are built as a seperate module - makes the process of making new softwares like whatsapp a lot easier (we don't have to worry about retransitting lost packets and all lower level prblems) - we can focus on our high level application
3. Flexibility - we can use different protocols at each layer - we can change different layers independently - if we want to use a different physical layer, we can do so

## Disadvantages
1. Lot of information which is hidden from one layer which could be useful 
Eg. Transport protocol - deals with retransmission of packets - it may help TCP to know where that extra packet was lost and why - since it can only interface **with the lower network layer** but no other outer source


# Performance 
The following are the parameters we look for to characterize the performance of the network/ protocols:
## Throughput
Average data rate sent from one end to the other (sender to the receiver). Roughly 64 KBPS (regular talking) is enough data rate to be able to transmit information (Throughut checks the data rate - how much information you can push through)

## Latency 
Delay of a message across the network
1. A good one-way latency is 100 ms
2. RTT - round trip time - in a good voice call should be 100's of milliseconds
3. ALl the performances are grouped together are called **Quality of Service**

Eg.
1. VIDEO STREAMING:
Nothing interactive
1. throughput - higher than usual - several Mbps
2. Latency - doesn't matter that much - no two way communication - even a few seconds is fine

Eg:
1. File Transfer:
1. Throughput - reasonable - few Megabytes
2. Latency - doesn't matter that much again

We have a lot of scope of change in the application layer - very specific datarates cannot be garunteed - the internet is as it is cannot be changed that much





















