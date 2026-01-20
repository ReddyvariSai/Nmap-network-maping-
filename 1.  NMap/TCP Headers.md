# TCP Headers

In the context of networking and tools like Nmap, `TCP headers` (often referred to as flags) are control bits used to manage the state of a connection and direct the flow of data.

Understanding these headers is essential for performing and analyzing network scans.

According to the sources, the primary TCP flags used during scanning and communication include:

## Primary TCP Flags
###### • SYN (Synchronize):
This flag is used to initiate a connection. It acts as a request to establish a communication channel between two machines.
###### • ACK (Acknowledgment): 
This flag indicates that data has been received successfully. It is a signal sent back to the sender to confirm receipt of a packet.
###### • RST (Reset): 
This flag is used to abort or stop a connection, usually in response to an error. For example, if Nmap sends a SYN packet to a closed port, the target machine typically responds with an RST flag.
###### • FIN (Finish): 
This flag is used to close an established connection gracefully once data transfer is complete.
###### • PSH (Push): 
This flag instructs the receiving system to transmit data to the application layer immediately rather than waiting for buffers to fill up.
###### • URG (Urgent): 
This flag signifies that the data within the packet is urgent and must be processed immediately by the application layer.

## Usage in Nmap Scanning

The sources explain that different scanning techniques manipulate these headers to identify open ports or bypass security:

###### • Vanilla Scan (TCP Connect):
This follows the complete three-way handshake using SYN, SYN/ACK, and ACK flags.
###### • Stealth Scan (SYN Scan):
This is a "half-open" scan where Nmap sends a SYN flag but responds with an RST instead of a final ACK after receiving a SYN/ACK from the target. This prevents the connection from being fully established and logged.
###### • Xmas Scan: 
This technique turns on the FIN, PSH, and URG flags simultaneously. When viewed in a protocol analyzer like Wireshark, the packet appears to be "blinking like a Christmas tree".
###### • Null Scan: 
This involves sending a packet with no flags set at all (none of the TCP headers are active) to see how the target responds.

Analogy: Think of TCP headers as a control panel of light switches on a shipping container.

> * SYN is the "Arrival Notice" switch you flip to tell the warehouse you're coming.
> * ACK is the "Received" switch you flip when the box lands in your hands.
> * RST is the "Emergency Stop" switch you hit if the warehouse is on fire or the door is locked.
> * PSH is the "Priority" switch used for packages that need to be opened the second they arrive.
> * FIN is the "Final Shipment" switch you flip when you are done sending boxes for the day.

# A TCP three-way handshake

A TCP three-way handshake is the standard process used to establish a reliable socket connection between a client and a server, such as a web browser and a web server.

This process ensures that both devices are ready to transmit data and that the communication channel is clear.

The handshake consists of the following three steps:

## • Step 1: SYN (Synchronize) – 

The process begins when the client sends a TCP SYN packet to the server.

This packet acts as a request to establish a connection and contains a random sequence number used to initiate communication.

The objective is to ask the server if it is open for a new connection.

## • Step 2: SYN-ACK (Synchronize-Acknowledgment) – 

If the server’s port is open and able to accept the connection, it receives the SYN packet and responds with a SYN-ACK packet.

This packet serves as a confirmation receipt, acknowledging the client's sequence number and sending the server's own sequence number back to the client.

## • Step 3: ACK (Acknowledgment) – 

Once the client receives the SYN-ACK, it sends a final ACK packet back to the server. This signal indicates that the server's response was received successfully.

Once these three steps are complete, the TCP connection is established, and the devices can begin the reliable exchange of data.

If the server sends an RST (Reset) packet instead of a SYN-ACK, it indicates that the targeted port is closed and no connection can be made.




