# Extending Your Network

## Port Forwarding

- Routers are used to configure port forwarding.
- Without port forwarding, devices like web servers are only available to other devices on the same local network.
- With port forwarding, devices on other networks can reach them. They send a request to your network's public IP on the chosen port, and if the port is set up, the request is passed on and the response is sent back.
- In simple words, port forwarding sends incoming network traffic on a specific port to a specific device on your network.
- The router keeps a table that you configure, matching ports to private IP addresses. Any packet that arrives with destination port X is routed to the private IP linked to that port in the table.

## Firewalls

- A firewall is a device on the network that decides which traffic is allowed to enter or exit.
- A firewall permits or denies traffic based on:
    1. Where is it coming from?
    2. Where is it going?
    3. What port is it for?
    4. What protocol is it using?
- Firewalls perform packet inspection to answer these questions.
- Firewalls come in many shapes and sizes, from dedicated hardware to software on your computer.
- They can be divided into 2 main categories:
    1. Stateful
    2. Stateless

### Stateful

- This firewall monitors the entire connection, rather than inspecting individual packets.
- It decides how to treat a device based on its whole connection.
- It uses more resources than a stateless firewall, because its decision-making is dynamic.
- If a connection from a host is bad, it will block the entire device.

### Stateless

- This type of firewall uses a fixed set of rules to decide whether each individual packet is acceptable or not.
- It uses far fewer resources, but it's less smart.
- However, these firewalls are useful when receiving a large amount of traffic from a set of hosts (like a DDoS attack).

## VPNs

- VPN stands for Virtual Private Network.
- With a VPN, 2 devices on different networks can communicate over a dedicated, private path across the internet (a **tunnel**).
- VPNs are not just proxy server connections with a tunnel.
- VPNs run at the operating system level, while proxy servers run at the application level. A proxy only tunnels traffic for one application, but a VPN tunnels traffic for the whole system.
- It lets networks in different physical and geographical locations be connected.
- It also helps with privacy, as data sent through a VPN is encrypted.
- It hides what you're doing from your ISP. They can see you're using a VPN, but not the content.

### VPN Technologies

#### PPP
- Point-to-Point Protocol. This technology is used by PPTP.
- It's used for authentication and encryption of data.
- VPNs work by using a private key and a public certificate.
- PPP is non-routable: it can't leave the network on its own.

#### PPTP
- Point-to-Point Tunneling Protocol.
- This is the technology that allows the data from PPP to travel and leave a network.
- PPTP is easy to set up and supported by most devices.
- But its encryption is weak compared to the alternatives.

#### IPSec
- Internet Protocol Security encrypts data using the existing IP framework.
- IPSec is harder to set up than the alternatives.
- However, once set up, it offers very strong encryption and is supported by many devices.

## LAN Networks

- A router is a device used to connect networks and pass data between them.
- Routing happens at layer 3 (the network layer) of the OSI model.
