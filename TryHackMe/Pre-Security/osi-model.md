# OSI Model

**O**pen **S**ystems **I**nterconnection Model

- It provides a framework that decides how all network devices send, receive and interpret data.
- It lets devices made for different functions communicate with each other.

- The layers of the OSI model are:
    1. Physical
    2. Data Link
    3. Network
    4. Transport
    5. Session
    6. Presentation
    7. Application

- The process of adding information to data (packets) is called **encapsulation**.
- This happens at each layer of the OSI model, as needed.

## Layer 1: Physical

- Devices use electrical signals to transfer data between each other in binary (1s and 0s).
- Example: Ethernet cables connecting devices.

## Layer 2: Data Link

- This layer handles the physical addressing of the transmission.
- It takes a packet from the network layer (which includes the IP address of the remote computer) and adds the physical **MAC** (Media Access Control) address of the device receiving it.
- Every network-enabled computer has a **N**etwork **I**nterface **C**ard (**NIC**) with a unique MAC address to identify it.

## Layer 3: Network

- Routing decides the best path for chunks of data to be sent along.
- Some protocols at this layer work out the best path for data to reach a device.
- These protocols include **OSPF** (**O**pen **S**hortest **P**ath **F**irst) and **RIP** (**R**outing **I**nformation **P**rotocol).
- They consider:
    1. The shortest path
    2. The most reliable path
    3. The fastest physical connection
- At this layer, everything is dealt with using IP addresses.
- Devices that can deliver packets using IP addresses (like routers) are known as **Layer 3 devices**.

## Layer 4: Transport

- This layer uses protocols like TCP and UDP.
- **TCP** (Transmission Control Protocol): error checking, slower, keeps a constant connection.
- **UDP** (User Datagram Protocol): no error checking, faster, no guarantee that data arrives.
- UDP is used for things like video streaming or gaming, where losing a few packets (a few pixels) isn't a big problem.
- TCP is used for tasks that need accuracy and assurance, like sending emails and transferring files.

## Layer 5: Session

- This layer creates and maintains a connection (session) with the other computer the data is meant for.
- It's also responsible for closing the session when the task is done, or when the session hasn't been used for a while.
- The session stays open as long as the connection is established.
- Data can't travel across 2 different sessions. If the same file has to be sent to 2 different endpoints, 2 separate sessions are made and the data is sent through each independently.

## Layer 6: Presentation

- This layer translates data into a standard format so it can be sent over the network and understood on the other side.
- Security features like HTTPS encryption also happen at this layer.
- This layer deals with everything related to how data is presented.

## Layer 7: Application

- This layer contains the protocols and rules that decide how users interact with the application.
- It's the layer users interact with directly, for example through an app's GUI (graphical user interface).
