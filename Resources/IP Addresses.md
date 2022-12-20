An IP address (Internet Protocol address) is a unique identifier that devices use to communicate with each other on a computer network.

### IP Version 4
IPv4 is the fourth version of the Internet Protocol and is the most commonly used version of IP. 
**When referring to IP, we 99% of the time refer to this one.**

An IPv4 address has a size of 32 bits, which limits the [address space](https://en.wikipedia.org/wiki/Address_space "Address space") to 4.294.967.296 (2<sup>32</sup>) addresses. Of this number, some addresses are reserved for special purposes such as [private networks](https://en.wikipedia.org/wiki/Private_network "Private network") (~18 million addresses) and [multicast addressing](https://en.wikipedia.org/wiki/Multicast_address "Multicast address") (~270 million addresses).

It consists of four octets, with each octet represented in decimal form and ranging from 0 – 255. 
It can also be written in binary form, consisting of 32 bits and ranging from 00000000 – 11111111. 
It serves two main functions: network interface [identification](https://en.wikipedia.org/wiki/Identification_(information) "Identification (information)") and location [addressing](https://en.wikipedia.org/wiki/Network_address "Network address").

These octets can be used to calculate the number of hosts available on the network. 
A host is any device that has an IP address and is used to communicate over the network. 
In order for two hosts to communicate with each other, they must have the same subnet mask.

> For example: **192.168.1.1**

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |   
| --- | --- | --- | --- | --- | --- | --- | --- | 
| 1   | 1   | 1   | 1   | 1   | 1   | 1   | 1   |     

The above table is equal to 255

| 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |   
| --- | --- | --- | --- | --- | --- | --- | --- | 
| 0  | 0   | 0   | 0   | 0   | 1   | 1   | 1   |    

The above table is equal to 7

##### Classes
There are five classes of IPv4 addresses: A, B, C, D, and E.

-   Class A addresses have a range of 1.0.0.0 to 126.0.0.0. The first octet is used to identify the network, and the last three octets are used to identify the host. Class A addresses are used for large networks with a large number of hosts.

-   **Class B** addresses have a range of 128.0.0.0 to 191.0.0.0. The first two octets are used to identify the network, and the last two octets are used to identify the host. Class B addresses are used for medium-sized networks with a moderate number of hosts.

-   **Class C** addresses have a range of 192.0.0.0 to 223.0.0.0. The first three octets are used to identify the network, and the last octet is used to identify the host. Class C addresses are used for small networks with a small number of hosts.

-   **Class D** addresses have a range of 224.0.0.0 to 239.0.0.0 and are reserved for multicast addresses. Multicast addresses are used to send a single packet to multiple destinations simultaneously.

-   **Class E** addresses have a range of 240.0.0.0 to 255.0.0.0 and are reserved for experimental or future use.

In a class D address, the network portion is represented by the first four octets and the host portion is not used. Class D addresses are used for multicast communications and are not used to identify individual hosts. Instead, they are used to identify a group of hosts that are interested in receiving the same multicast traffic.

### IP Version 6 
IPv6 is the sixth version of the Internet Protocol and is designed to replace IPv4, which is quickly running out of available addresses due to the growth of the internet. 

In IPv6, the address size was increased from 32 bits in IPv4 to 128 bits, thus providing up to 2<sup>128</sup> (340,282,366,920,938,463,463,374,607,431,768,211,456) addresses. 
It is written in hexadecimal format.

> For example: **2001:0db8:85a3:0042:1000:8a2e:0370:7334**

### IPv4 to IPv6
The transition from IPv4 to IPv6 has been underway for a number of years, and is expected to continue for some time. IPv4 is the fourth version of the Internet Protocol, which is the primary communication protocol used on the internet. It is based on a 32-bit address space, which allows for a total of about 4.3 billion unique addresses.

However, with the explosive growth of the internet and the proliferation of devices that use it, the pool of available IPv4 addresses has been depleted. This has led to the development of IPv6, which is based on a 128-bit address space and allows for a virtually limitless number of unique addresses.

IPv6 has been available since the late 1990s, and many internet service providers (ISPs) and other organizations have begun the process of transitioning to it. However, the transition has been slow due to the significant costs and technical challenges involved. Additionally, IPv4 is still widely used and supported, and there is a large installed base of devices and infrastructure that rely on it.

It is difficult to predict exactly when the transition from IPv4 to IPv6 will be complete, as it will depend on a number of factors, including the rate of adoption of IPv6 by ISPs and other organizations, and the lifetime of existing IPv4 infrastructure. However, it is likely that the transition will continue for many years to come.

### Network Address Translation (NAT)
Network Address Translation (NAT) is a method used to allow devices on a private network, such as a home network or corporate LAN, to communicate with the internet. NAT allows devices on the private network to use a single, shared IP address to access the internet, while still maintaining their own unique, private IP addresses on the local network.

**NAT was created to address the issue of the depletion of IPv4 addresses.** As the internet grew, the pool of available IPv4 addresses became depleted, and it became necessary to find ways to conserve these addresses. NAT allows organizations and individuals to use a single, public IP address for multiple devices on their private network, rather than having to assign a unique, public IP address to each device. This helps to conserve IPv4 addresses and allows for the efficient use of the remaining pool of addresses.

NAT is typically implemented by a NAT device, such as a router, that sits between the private network and the internet. When a device on the private network sends traffic to the internet, the NAT device translates the private IP address of the device into a public IP address, and vice versa when traffic is received from the internet. This allows devices on the private network to communicate with the internet, while still maintaining their private IP addresses and keeping them hidden from the public internet.

There are 3 types of NAT:

> Each type of NAT has its own set of advantages and disadvantages, and the appropriate type to use depends on the specific needs and requirements of the network.

##### Static NAT

This type of NAT creates a fixed, one-to-one mapping between a private IP address and a public IP address. This means that a device on the private network will always use the same public IP address to access the internet. Static NAT is useful in situations where a device on the private network needs to be reachable from the internet using a consistent, static IP address.

##### Dynamic NAT

This type of NAT creates a mapping between a private IP address and a public IP address from a pool of available addresses. When a device on the private network needs to access the internet, it is assigned a public IP address from the pool. When the device is no longer using the internet, the public IP address is returned to the pool for reuse. Dynamic NAT allows multiple devices on the private network to access the internet using a limited number of public IP addresses.

##### Port Address Translation (PAT) or Network Address Port Translation (NAPT)

This type of NAT creates a one-to-many mapping between a single public IP address and multiple private IP addresses. When a device on the private network sends traffic to the internet, the NAT device assigns a unique port number to the traffic, which allows it to be multiplexed over a single public IP address. This allows multiple devices on the private network to share a single public IP address and access the internet simultaneously. PAT is commonly used to conserve public IP addresses and allow multiple devices to access the internet using a limited number of addresses.

