# A Giant Web of Computers? How does the Internet really work? (Part 2- Transmission)

## Summary
In the last release of this series, we opened a discussion about the Internet, defining it as a network of interconnected computers exchanging resources(data). We also clarified the difference between the Internet and the world wide web. And finally, we took a detour into the web and looked at some of the essential components that enable it to work seamlessly. 

In this episode, we dive deeply into the technology responsible for transmitting information across the Internet. How exactly does sharing of digital resources happen across the Internet? 
Brace up, we're in for a fun ride. 

## Switching

Switching is the term used in [Computer Networking](https://en.wikipedia.org/wiki/Computer_network) to denote the sharing of information between two communication devices.  Imagine traveling across the country by car, you would definitely need a map to navigate and determine the best route to take. Data does not just travel in random paths, there must be straight pre-defined paths. 

Switching helps to determine the best route for data transmission, especially in complex networks where there are multiple paths. This concept is the backbone of the Internet, the very technology that enables it to work.
Let's consider two types of switching critical to gaining an understanding of the Internet.

## Packet Switching vs Circuit Switching

### Circuit Switching
Circuit Switching is the type of switching in which a pre-specific route is determined when a connection is opened between the sender and receiver. This path is reserved as long as the connection is open and no other device cannot transmit using this dedicated channel.

This type of network switching is used in Analog Telephone networks.


![Circuit-Switching-Diagram.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666266245406/tJWGDKJum.png align="left")
- Photo credits [https://www.gatevidyalay.com](https://www.gatevidyalay.com/circuit-switching-types-of-switching/)

### Packet Switching
An example to illustrate packet switching would be a scenario where a traveler has so much luggage that he decides to divide the load into chunks and sends them ahead to ease his journey. In packet switching, when a message is sent - it is divided into small chunks called packets. These packets are well-labeled for identification, sent over the network, and assembled at their destination.  Smart, right? 

Each packet contains information such as the destination address, sequence number, etc so they can be routed independently across the network. The obvious advantage of packet switching is that it doesn't need end-to-end connection like circuit switching and therefore does not waste bandwidth. Packet switching is the preferred method of data transmission utilized by the Internet.

![packet switching.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666269074614/rSIPDerKz.png align="left")
- Photo Credits [studytonight.com](https://www.studytonight.com/computer-networks/packet-switching-in-computer-networks)

## TCP/IP
TCP/IP stands for `Transmission Control Protocol/Internet Protocol` and is a set of communication protocols used to transmit data across a network. We have previously established that the Internet makes use of Packet Switching to transmit data from a point to its destination. This process is enabled by TCP/IP. 

TCP manages the process of dividing a message into chunks while IP ensures the packets are well-labeled with the necessary routing information for them to reach the desired destination. The TCP/IP Model contains [four layers](https://www.geeksforgeeks.org/tcp-ip-model/) namely: Application Layer, Transport Layer, Network Layer, and Physical Layer. In a future article, we will dive a bit deeper into the Networking Models but for now, we're keeping this concise article.

## Conclusion
In this article, we discussed the transmission process of Information across the Internet and the tools that make it possible. 

 I hope you have gained a more robust understanding of the Internet through this article. Till the next, stay informed. Cheers!