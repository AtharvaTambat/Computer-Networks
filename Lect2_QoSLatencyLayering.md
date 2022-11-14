# Quality of Service
## Best Effort 
An application will make do with whatever quality of service the nework gicves - no QoS garuntees from the network - it will transfer data as best as it can 

1. The current internet is designed as a **Best Effort network**
2. Difficult to change the protocols that have already been set
3. Each of the links in a router has a certain bit rate (BANDWIDTH) (Link capacity - wired links) - maximum data rate of transmissionon a wired link
4. The incoming packets have to be sent out in a common output
5. If they exceed the maximum datarate of the output - the extra pakets have to be stored in a Queue
6. In the current internet you cannot reserve bandwidth - it also depends on how many other people are using the network

## Latency 
1. Data is coming at a rate of c1 bits per second 
2. Typically, Routers will not send the bit as soon as it comes into the router - will need a few bits to see the destination IP address - wait till the full packet comes in  - because the packet could be corrupt
3. **STORE AND FORWARD** - wait till the full packet is received - forward to the output queue

Another type of switching - **CUT THROUGH SWITCHING**
1. Forward to the output as soon as you can - as soon as you know what the output IP address is
2. $t_0$ - the time at which the firs bit comes at the router, $t_1$ - last bit is received at input. (Say the Queue already had some data - $Q_{t_1}$)

$t_1 = t_0 + \frac{P}{C_1}$

Let $t_2$ be the time when the first bit is sent at the output link
Say the Queue is being emptied at $C_2$ bits per second

$t_2 = t_1 + \frac{Q_{t_1}}{C_2}$

Let $t_3$ be the time when the last bit is sent at the output link

$t_3 = t_2 + \frac{P}{C_2} = t_0 + \frac{P}{C_1} + \frac{Q_{t_1}}{C_2} + \frac{P}{C_2}$

> $\frac{P}{C_2}$ - Transmission Delay $\\$
> $\frac{Q_{t_1}}{C_2}$ - Queueing Delay

Even when the queues are empty, the latency is not zero

## Cross traffic
The traffic other than one's own packets

Telephone network was designed for voice call - bandwidth is ensured - not like wireless

## Congestion control
If the Queues build up at any router 

If the queue is full, the packet is dropped - the quality of service will plummet - congestion control is handled by TCP (transport layer) - also may be handled by lower layers

- Application layer - protocols like FTP, HTTP, SMTP, VOIP...
- Transport layer - TCP, UDP - (VOIP could choose to use UDP - in case you want the packet to be sent immediately in the network)
- Network - IP 
- IEEE 802.11 - standards - handles DLL, Physical protocols

We end up with an hourglass figure - IP being the narrow part

- Congestion control - done by transport and some in DLL and physical layer and ethernet protocol

Designed such that every layer has to communicate to the immediate higher or lower layer















