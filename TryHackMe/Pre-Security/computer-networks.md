# Computer Networks

## MAC Address

- A MAC address is a **12-character** hexadecimal number (hexadecimal is a base-16 numbering system used in computing), split into pairs separated by colons.
- For example: `a4:c3:f0:85:ac:2d`
- The first six characters identify the company that made the network interface, and the last six are a unique number.

- Some routers and services use the MAC address to identify and authenticate a user.
- This is handy if you want to bill each device separately, but the problem is that anyone who spoofs (fakes) the MAC address of a paying user can use the service too.
- So using MAC addresses for identification is a very insecure method.

## Ping

- Ping is one of the most basic network tools.
- Ping uses **ICMP** (**I**nternet **C**ontrol **M**essage **P**rotocol) packets to check the connection between devices: whether a connection exists and whether it's reliable.
- Ping measures the time it takes for ICMP packets to travel between the devices.
- It does this by sending an ICMP **echo request** and waiting for an ICMP **echo reply** from the target device.
