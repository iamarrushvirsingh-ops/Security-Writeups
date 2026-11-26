# Intro to LAN

- There are many network designs. These designs are called **topologies**:
    1. Star topology
    2. Bus topology
    3. Ring topology

## Star Topology

- Each device is individually connected to a central networking device, like a switch or hub.
- It's costly because of all the extra cabling.
- But it's easily scalable.

## Bus Topology

- This type of connection relies on a single shared cable, known as the **backbone cable**.
- It's prone to bottlenecks, and multiple requests at once can be a problem.
- If the backbone cable is damaged, the whole network fails.

## Ring Topology

- Devices are connected to each other in a circle.
- For any request, the packets travel around the circle until they reach the intended device.
- Its cons: packets only travel in one direction, and if the cable is damaged at any point, the whole network stops.

## Subnetting (Intro)

- Subnetting means splitting a network into smaller networks within itself.
- This is done by splitting up how many hosts (devices) can fit in the network, using a number called a **subnet mask**.
- An IP address is made up of four sections called **octets**.
- A subnet mask is written the same way: 4 bytes (32 bits), with each section ranging from 0 to 255.
- Subnets use IP addresses in three different ways:
    - **Network address**: identifies that the network exists.
    - **Host address**: an IP address used to identify a device on the subnet.
    - **Default gateway**: a special address given to a device on the network (usually the router) that can send information to another network.

## ARP

- **ARP** (**A**ddress **R**esolution **P**rotocol) is the technology that lets devices identify themselves on a network.
- Simply put, ARP lets a device link a MAC address to an IP address on the network.
- Each device keeps a record of the MAC addresses of other devices. This record is called a **cache**, and for ARP it's called the **ARP cache**.
- When a device wants to communicate, it can send a broadcast asking for the MAC address of the device with a specific IP.
- Once it gets the answer, it saves the MAC and IP pair in its ARP cache, so it doesn't have to broadcast every time.

To map these two identifiers together (IP address and MAC address), ARP sends two types of messages:

1. **ARP Request**: asks, "Which device has this IP? Send me your MAC address."
2. **ARP Reply**: the device with that IP responds with its MAC address.

- The requesting device then remembers this mapping in its ARP cache for future use.

## DHCP

When a device joins a network, it gets an IP address automatically through DHCP in 4 steps:

1. **DHCP Discover**: the device sends a request to see if there are any DHCP servers on the network.
2. **DHCP Offer**: the server offers an IP address for the device to use.
3. **DHCP Request**: the device confirms it would like to use the offered IP.
4. **DHCP ACK**: the server acknowledges that it's all done, and the device can now use the IP.
