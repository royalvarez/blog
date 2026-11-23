+++
title = 'Computer Science Principles Unit 2 Review E'
date = 2026-11-23T14:20:17-06:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, we will go up a layer to see how packets use an additional protocol to ensure proper transmission on the internet.
The first transport protocol that we will begin to understand is the User datagram Protocol, what it is used for, and its structur.
Another transport protocol used by IP is the Transmission Control Protocol. We will learn its structure, and its way of handling common errors with packets.

### Transport Protocol
So far, we have understood that the Internet Protocol describes the structure of data (called an IP Packet), and how the packet should be transferred from one computer to another on the internet. But there is more aspects to packets than just the Internet Protocol.

Packets also rely on another protocol that is layered atop of the Internet Protocol. This protocol known as a transport protocol, acts as a verifier so that both computers, 
the sender, and the reciever, can reassemble the packets in its initial data format.

Lets explore some common errors that can happen when sending packets to another computer:
* Packets can arrive out of order.
* The packet becomes corrupted, meaning the recieved data does not match the sent data.
* Packets can get lost, which might mean that the other computer cannot reconstruct the data 100%.
* Packet duplication, as a result of of the same packet being sent over to the reciever.

There are higher level protocols that solve these errors, and we will learn about 2 kinds of transport protocols:
* User Datagram Protocol

The User Datagram Protocol solves less errors but is faster.

* Transmission Control Protocol

The Transmission Control Protocol solves packet ordering, retransmission (duplication), and data integrity. It is the most commonly used transport protocol.

The great thing about the transport protocol is that internet applications can choose the one that fits best with there needs.

### User Datagram Protocol
The User Datagram Protocol (UDP for short) is a simple and fast transport protocol layered atop of the Internet Protocol. The reason for the speed increase is a result of not establishing a strong connection before data transfer occurs.

UDP solves packet corruption, but not other common errors like packet loss and packets that are out of order. For this reason, the UDP is sometimes called the unreliable transport protocol.

Cases for When UDP is used as the transport protocol:
* when the file is too large for other common transport protocols.
* time sensitive applications like livestreaming.

#### UDP Packet Structure
The UDP takes the already structured IP packet, the header and payload, and modifies the payload field. This change is called a UDP segment.

##### UDP Segment
A UDP ssegment contains a header field and payload.

The characteristics of each UDP segment field are:
* Header

8 bytes wide header.

* Payload

A variable length amount.

##### UDP Header Field
The UDP Header can be thought of  as three main sections:
* Port numbers.
* Segment length.
* Checksum.

###### Port Numbers
The first 4 bytes of the header indicate both the source device and the destination device port numbers.

[A networked device](https://dev.to/ritam369/understanding-network-devices-4go7) is a device responsible for moving the packets along to the target destination.

They have virtual ports which allow for the device to be able to recieve and handle multiple packets at once.

The various ports on a networked device help differentiate the types of network traffic, such as [real time and non-real time data](https://www.fortinet.com/resources/cyberglossary/network-traffic).

###### Segment Length
The 2 bytes in the header following after the port numbers contain the segment length. The length is measured in bytes.

We can calculate the maximum length of a segment by the following process:
1. 2 bytes is 16 bits.
2. 2 raised to the 16th minus 1 is 65535.
3. 65535 bytes, because the type of the segment unit is measured in bytes.

###### Checksum
The final 2 bytes in the header check for data corruption and is used by both the sender and reciever. This third section or field is called a checksum.

The Checksum process can be generalized by the following (note that these are not all the steps):
1. The sender computes the checksum value based on the segment and payload.
2. Stores the checksum in the final 2 bytes in the UDP header.
3. Transfer UDP packet over the internet.
4. The reciever acquires the UDP packet.
5. The reciever computes the checksum.
6. The reciever then compares the two values, and if the checksums are not equal, the reciever deems the UDP packet as corrupted.

A corrupted packet often makes it impossible to reconstruct the original data, so the computer discards the packet all together.

### Transmission Control Protocol
Transmission Control Protocol (TCP for short), is the most commonly used transport protocol used atop of the Internet Protocol layer. It transfors packets reliably.

TCP solves many of the errors that IP packets can have:
* Duplication of packets.
* Loss packets.
* Out of ordered packets.
* Packet Ccorruption.

A common term you might hear is the Internet Protocol staack followed by TCP/IP, because of how common IP uses TCP for transferring data.

#### TCP Packet Structure
A TCP packet modifies an IP packet's payload field. This modification is the TCP segment.

##### TCP Segment
The TCP segment contains both a header and payload.

The TCP segment Header is more extensive than the UDP segment header. It has more fields and can store 20 to 60 bytes - the exact bytes is determined by the options field in the header.

However, the TCP segment shares some commonality with UDP segments too.
* Both contain a source port numbers field and destination port numbers field in the header.
* Both contain a checksum field in the header.
* Both payloads are of variable length.

#### Transffering with TCP
Lets look how we send packets using TCP as our transfer protocol, or TCP/IP.

The high level abstraction is:
1. Establish a connection.
2. Send over pacckets.
3. Close the connections.

##### Establishing a Connection
The first step before any data transfering is ensuring a connection between both computers. This process is called a three way handshake.

Inside the TCP ssegment header, there are bits belonging to flags. Flags provide specific instructions for how something should be handled. You can [learn more here](https://backup.education/showthread.php?tid=1769).

There are 2 main flags that begin the three way handshake connection:
* SYN (synchronize).
* ACK (acknowledge).

Now lets see how packets use these flags to establish a connection.
1. The first computer (sender) sets a packet's SYN bit to 1, and sends it to the other computer (reciever).
2. The reciever sends a different packet with ACK set to 1 and SYN set to 1 to the sender.
3. The sender sends another different packet with the ACK set to 1 to the reciever.

Usually, the packets that are being sent and establishing the three way handshake contain no payload.

After all three packets have forgone and successfully established a connection, the data can now be transferred.

##### Sending Packets of Data
IN TCP, when a packet of data gets recieved, an acknowledgement is required. Lets see what this means in practice.

1. The first computer (sender) sends a packet with data and a sequence number.
2. The recieving computer (reciever) acknowledges the packet by setting the ACK to 1 and increases the acknowledgment number by the length of the payload.

Both the sequence numbers and acknowledgement numbers are part of the TCP segment header.

They also help in tracking information like:
* what daata has been successfully recieved.
* What data was lost.
* What data has been sent more than once.

##### Closing the Connection
Both ccomputers have the option to close the connection, when either computer wants to no longer send or recieve pacckets.

The process again follows a three way handshake.

1. Either the sender or reciever begins by sending a packet with the FIN (finish flag) set to 1 to the other computer.
2. The other computer responds by sending a different packet with the ACK set to 1 and the FIN set to 1.
3. The computer that began the closing process sends one more packet with ACK set to 1 to the other computer, and then the connection closes.

#### Strategy for Detecting Loss Packets
TCP connections uses a timeout system to detect packet loss.

1. The sender starts a timer once the packet is sent off.
2. The packet gets set in a retransmission queue.
3. If the timer finishes and no ACK was sent by the reciever, the packet is sent again.

Packets might not always be lost, and instead be slow to arrive. In these cases, the transmission will still send the packet, resulting in a duplicate of packets. The reciever can identify the duplicates and discard them to only have one packet of that data.

#### Strategy for Handling Out of Order Packets.
The TCP connection can identify when a packet was sent out of order based on the sequence numbers and acknowledgement numbers in the TCP segment header.

The reciever checks the sequence number, and if it is a number higher than what it has accknowledge so far, the reciever knows that there is a disordering.

As a result, the reciever then sends a packet with the acknowledgement number set to the expected   sequence number to the sender.

A packet can be deemed lost by:
* The packet is slow to arrive.
* The packet is actually lost.

Whatever is the reason on why a packet is considered lost, the result is that the reciever is then dealing with out of order packets. And the reciever can handle this error by using the sequence numbers to properly order the pacckets.

## Summary
A transport protocol is layered atop of the IP, and it solves errors that can occur with packets.  There are 2 primary transport protocols: UDP and TCP.
The UDP is fast but solves fewer errors that are common with IP Packets. The structure of an IP Packet using UDP contains a UDP segment. Inside the UDP segment, there is a checksum which is used to check for corrupted data.
Finally, TCP is the most common transport protocol used atop of the IP. Thanks to its three way handshake strategy, connections are reliable in transferring data. The fact that the TCP segment header is more extensive, it is able to do more things, like solving packet loss and out of order packets.