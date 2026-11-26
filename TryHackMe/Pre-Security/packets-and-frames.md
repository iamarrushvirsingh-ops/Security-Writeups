# Packets and Frames

## Packet

- A piece of data at layer 3 (the network layer) of the OSI model.
- Contains the payload (the actual data) and IP address information.

## Frame

- A packet wrapped (encapsulated) with MAC address information.
- Works at layer 2 (the data link layer) of the OSI model.

- **Encapsulation** is the process of wrapping extra information around data.
- Sending data in small packets reduces the chance of bottlenecks on the network.

## Protocols

- Packets have different structures depending on what type of packet they are.
- Networks follow standards and protocols. Without proper standardisation, the internet would break.
- These standards and protocols decide how packets are handled over a network.

### IP

- A packet that uses the Internet Protocol (IP) has a header with extra information, which is sent along with the packet across the network.

#### Some Notable IP Headers

1. **Time to Live (TTL)**: Sets when the packet expires. This gets rid of lost packets so they don't clog up the network.
2. **Checksum**: Checks integrity. If any data is changed on the way, this value won't match what was expected, so the packet is known to be corrupt.
3. **Source Address**: The IP address of the device the packet is sent from, so the reply knows where to return to.
4. **Destination Address**: The IP address of the device the packet is going to, so it knows where to go.

# TCP/IP Model

- The TCP/IP model has 4 layers:
    1. Application
    2. Transport
    3. Internet
    4. Network Interface
- Information is added at each layer as the data travels through it. As mentioned above, this is called **encapsulation**, and the reverse is called **decapsulation**.

# TCP (Transmission Control Protocol)

- TCP is connection-based: it must set up a connection between the client and the server before any data is sent. This setup is called the **three-way handshake**.
- TCP guarantees that data sent will be received, because the receiver sends back an acknowledgement (ACK) for the data it gets, and anything missing is sent again.

## TCP Headers

A lot of information is added to the packet's header during encapsulation. Some of the headers are:

1. Source port
2. Destination port
3. Source IP
4. Destination IP
5. Sequence number (set when a connection is established)
6. Acknowledgement number
7. Checksum (used to check the integrity of the data)
8. Data
9. Flag (tells how the packet should be dealt with)

## TCP Packet Types (Flags)

1. SYN
2. SYN/ACK
3. ACK
4. DATA
5. FIN
6. RST

- **SYN** is sent by the client to start a connection and synchronise the 2 devices.
- **SYN/ACK** is sent by the receiving device to confirm it received the SYN packet.
- **ACK** can be sent by either the client or the server to confirm that data was received successfully.
- **DATA** is the actual information being transferred, sent after the connection is established.
- **FIN** is used to cleanly and properly close the connection once it's done.
- **RST** abruptly ends a connection. It's a last resort, used when there was a problem during the process.

## Three-Way Handshake

The connection is set up in 3 steps:

1. **SYN**: the client asks to start a connection.
2. **SYN/ACK**: the server agrees and acknowledges.
3. **ACK**: the client confirms, and data can now be sent.

### Sequence Numbers

- Data sent over TCP is numbered starting from a random number, and the receiving device puts it back in order using these numbers, adding 1 each time.
- Both computers must agree on the starting numbers so the data arrives in the correct order.
- This is agreed during the handshake:
    1. **SYN (client)**: "Here's my Initial Sequence Number (ISN) to synchronise with: 0"
    2. **SYN/ACK (server)**: "Here's my ISN: 5,000, and I acknowledge your ISN of 0"
    3. **ACK (client)**: "I acknowledge your ISN of 5,000. Here's some data, starting at my ISN + 1 (0 + 1)"
- Because TCP reserves system resources for each connection, it's best practice to close a connection once the job is done.
    - Example of a TCP session closing:
      `FIN (client to server) -> FIN/ACK (server to client) -> ACK (client to server)`

# UDP (User Datagram Protocol)

- Unlike TCP, UDP is a stateless protocol. It doesn't need a constant connection between 2 devices to send data.
- There is no three-way handshake and no synchronisation.
- UDP is faster because it does fewer checks.
- The sender doesn't check whether the packet was received.
- Applications control the sending rate and any reliability themselves.
- Good for real-time apps, where "working" matters more than perfect packet delivery.
- Use UDP when low delay (latency) matters and some data loss is acceptable.

## Some UDP Packet Headers

1. TTL (time to live)
2. Source address
3. Destination address
4. Source port
5. Destination port
6. Data

- **TTL (time to live)** is the expiry time of the packet. If the packet gets lost on the way, it expires instead of clogging the network.
- Note: TTL and the source/destination addresses actually come from the IP header that wraps the UDP data. UDP itself adds the ports.

# Ports

- A computer has ports numbered 0 to 65,535.
- Ports 0-1023 are called the **well-known ports** (the common port range).
- To prevent confusion, the ports for major services have been standardised.
- For example:
    1. FTP - 21
    2. SSH - 22
    3. HTTP - 80
    4. HTTPS - 443
    5. SMB - 445 (Server Message Block)
    6. RDP - 3389
