### TCP
Transmission Control Protocol (TCP) is a transport layer protocol that is used to transmit data across a network. It is a connection-oriented protocol, which means that it establishes a dedicated end-to-end connection between the sender and the receiver before transmitting data. This connection is maintained until the transmission is complete or the connection is terminated.

TCP is designed to provide reliable data transmission by ensuring that all data packets are acknowledged by the receiver and retransmitted if necessary. It uses a number of mechanisms to ensure the integrity of the transmission, including sequence numbers, checksums, and flow control.

TCP is used by a wide range of applications that require a reliable end-to-end connection, such as web browsing, email, file transfer, and remote login. It is also used as a transport layer protocol in many other protocols, including HTTP, FTP, and SMTP.

One of the main advantages of TCP is its reliability. Because it establishes a connection and performs error checking, it is able to recover from packet loss and ensure that all data is transmitted correctly. This makes it ideal for applications that require a high level of reliability, such as email and file transfer.

However, the overhead associated with establishing and maintaining a connection and performing error checking can also be a disadvantage of TCP. It requires more resources and has higher overhead than other transport layer protocols such as User Datagram Protocol (UDP), which can lead to slower performance in certain situations.

### UDP
User Datagram Protocol (UDP) is a transport layer protocol that is used to transmit data across a network. It is a connectionless protocol, which means that it does not establish a dedicated end-to-end connection between the sender and the receiver before transmitting data. Instead, it sends packets of data called datagrams directly to the destination without establishing a connection or checking to see if the packets were received.

UDP is often used for real-time applications that require low latency and high speed, such as online gaming, video conferencing, and voice over IP (VoIP). It is also used for applications that do not require a reliable end-to-end connection, such as Domain Name System (DNS) queries and Simple Network Management Protocol (SNMP) notifications.

One of the main advantages of UDP is its simplicity. Because it does not establish a connection or perform error checking, it requires fewer resources and has lower overhead than other transport layer protocols such as Transmission Control Protocol (TCP). This makes it ideal for applications that require high performance and low latency.

However, the lack of error checking and reliability can also be a disadvantage of UDP. If a packet is lost or corrupted, there is no mechanism to recover it or request a retransmission. This can lead to data loss and may make it less suitable for applications that require a high level of reliability.

### Common Ports and Protocols

#### TCP (Transmission Control Protocol) common ports:

-   20 and 21 - FTP (File Transfer Protocol)
-   22 - SSH (Secure Shell)
-   23 - Telnet
-   25 - SMTP (Simple Mail Transfer Protocol)
-   53 - DNS (Domain Name System)
-   80 - HTTP (Hypertext Transfer Protocol)
-   110 - POP3 (Post Office Protocol 3)
-   143 - IMAP (Internet Mail Access Protocol)
-   443 - HTTPS (HTTP Secure)
-   465 - SMTPS (SMTP Secure)
-   993 - IMAPS (IMAP Secure)
-   3389 - Remote Desktop Protocol (RDP)

#### UDP (User Datagram Protocol) common ports:

-   53 - DNS (Domain Name System)
-   67 and 68: DHCP (Dynamic Host Configuration Protocol)
-   69: TFTP (Trivial File Transfer Protocol)
-   123 - NTP (Network Time Protocol)
-   161 - SNMP (Simple Network Management Protocol)

In general, TCP is more reliable but slower, while UDP is faster but less reliable. The choice of which protocol to use depends on the specific needs of the application transmitting the data.

### Three-Way Handshake
A three-way handshake, also known as a TCP handshake, is a process used by the Transmission Control Protocol (TCP) to establish a connection between two devices before transmitting data. It involves the exchange of three messages between the devices, which are used to synchronize their sequence numbers and initiate the connection.

The three-way handshake consists of the following steps:

1.  The client (Computer A) sends a SYN (Synchronize) message to the server (Computer B), requesting the establishment of a connection. The SYN message includes a random initial sequence number (ISN) chosen by the client.

2.  The server responds with a SYN-ACK (Synchronize-Acknowledge) message, acknowledging the receipt of the SYN message and requesting the establishment of a connection. The SYN-ACK message includes its own ISN, which is chosen by the server, as well as the client's ISN plus one.

3.  The client responds with an ACK (Acknowledge) message, acknowledging the receipt of the SYN-ACK message and completing the three-way handshake. The ACK message includes the server's ISN plus one.

After the three-way handshake is complete, the devices can begin transmitting data over the connection. The three-way handshake is used to establish a connection between devices in both directions, so the process is repeated in reverse if data needs to be transmitted from the server to the client.

The three-way handshake is used by TCP to establish a connection because it ensures that both devices are ready to communicate and have synchronized their sequence numbers. It also allows each device to verify that the other device is alive and reachable.