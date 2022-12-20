# Notekeeping

If you wanna be successful in your career, and you wanna be successful in this course, you really need to take good notes.

Here are some of the best applications I've tried and can recommend:

- [Notion](https://www.notion.so/)
- [Obsidian](https://obsidian.md/)
- [Logseq](https://logseq.com/)
- [OneNote](https://www.onenote.com/download)
- [CherryTree]([https://www.giuspen.com/cherrytree/](https://www.giuspen.com/cherrytree))

# Networking Refresher

## IP Addresses

An IP address (Internet Protocol address) is a unique identifier that devices use to communicate with each other on a computer network.

#### IP Version 4
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

#### IP Version 6 
IPv6 is the sixth version of the Internet Protocol and is designed to replace IPv4, which is quickly running out of available addresses due to the growth of the internet. 

In IPv6, the address size was increased from 32 bits in IPv4 to 128 bits, thus providing up to 2<sup>128</sup> (340,282,366,920,938,463,463,374,607,431,768,211,456) addresses. 
It is written in hexadecimal format.

> For example: **2001:0db8:85a3:0042:1000:8a2e:0370:7334**

#### IPv4 to IPv6
The transition from IPv4 to IPv6 has been underway for a number of years, and is expected to continue for some time. IPv4 is the fourth version of the Internet Protocol, which is the primary communication protocol used on the internet. It is based on a 32-bit address space, which allows for a total of about 4.3 billion unique addresses.

However, with the explosive growth of the internet and the proliferation of devices that use it, the pool of available IPv4 addresses has been depleted. This has led to the development of IPv6, which is based on a 128-bit address space and allows for a virtually limitless number of unique addresses.

IPv6 has been available since the late 1990s, and many internet service providers (ISPs) and other organizations have begun the process of transitioning to it. However, the transition has been slow due to the significant costs and technical challenges involved. Additionally, IPv4 is still widely used and supported, and there is a large installed base of devices and infrastructure that rely on it.

It is difficult to predict exactly when the transition from IPv4 to IPv6 will be complete, as it will depend on a number of factors, including the rate of adoption of IPv6 by ISPs and other organizations, and the lifetime of existing IPv4 infrastructure. However, it is likely that the transition will continue for many years to come.

#### Network Address Translation (NAT)
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


## MAC Addresses

A MAC address (or "Media Access Control" address) is a hardware identification number that uniquely identifies each device on a network. Every network interface card (NIC) in any device has its own unique MAC address that is used to identify the device on the network. The MAC address consists of six groups of two hexadecimal digits, separated by colons or hyphens. 

> For example, 00:12:34:56:78:9A

## Subnetting
Subnetting is the process of breaking a large network into smaller subnetworks, or subnets. A subnet is a segmented portion of a larger network, which can be used to help divide the network into smaller and more efficient parts. By doing this, it allows for easier management of the overall network, as well as improved performance and better security of the individual parts. Subnetting is also used to reduce the size of broadcast domains by splitting them up into smaller logical groups. This can help prevent congestion on the network by limiting broadcast traffic and providing better control over who has access to certain parts of a network.

netmask 255.255.255.0

*Example of a /24 or wack24 network*

If all of the ones are switched on, we've got a 255.
If none of the ones are switched on, we've got a 0.

They have to be switched in order (from left to right)


![[Screenshot 2022-12-17 104419.png]]

## The OSI Model

The OSI Model, or Open Systems Interconnection model, is a reference model for how applications communicate over a network. It is composed of 7 layers, each layer responsible for a different function in the communication process. 

1. **Physical** Layer (Data, Cables, Cat6)
Responsible for transmitting raw bits over a physical medium. It includes the physical characteristics of the network such as cables, connectors, and network interface cards (NICs).

2. **Data Link** Layer (Switching, MAC Addresses)
It provides reliable transmission of data across a physical link by using error-correction techniques. It also controls the flow of data by using protocols such as Ethernet and token ring.

3. **Network** Layer (IP Addresses, Routing)
It is responsible for routing packets from source to destination networks by using the best possible path. It also provides packet switching, flow control, and congestion control services.

4. **Transport** Layer (TCP/UDP)
It is responsible for providing end-to-end reliable delivery of data between two applications on different hosts by using connection-oriented protocols such as TCP and UDP. 

5. **Session** Layer (Session Management)
It establishes, manages and terminates communication sessions between two applications on different hosts. 

6. **Presentation** Layer (WMV, JPEG, MOV)
It is responsible for formatting the data in a particular way before it is sent over the network to ensure compatibility between different systems on the network. 

7. **Application** Layer (HTTP, SMTP)
This layer provides services to user applications such as file transfer protocol (FTP), telnet, email, etc., that enable users to access information or resources available on other systems on the network.

> An easy way to remember all the seven layers is to take the first letter of each layer (PDNTSPA) and remember this phrase: 'Please, do not throw sausage pizza away'

## TCP/UDP
#### TCP
Transmission Control Protocol (TCP) is a transport layer protocol that is used to transmit data across a network. It is a connection-oriented protocol, which means that it establishes a dedicated end-to-end connection between the sender and the receiver before transmitting data. This connection is maintained until the transmission is complete or the connection is terminated.

TCP is designed to provide reliable data transmission by ensuring that all data packets are acknowledged by the receiver and retransmitted if necessary. It uses a number of mechanisms to ensure the integrity of the transmission, including sequence numbers, checksums, and flow control.

TCP is used by a wide range of applications that require a reliable end-to-end connection, such as web browsing, email, file transfer, and remote login. It is also used as a transport layer protocol in many other protocols, including HTTP, FTP, and SMTP.

One of the main advantages of TCP is its reliability. Because it establishes a connection and performs error checking, it is able to recover from packet loss and ensure that all data is transmitted correctly. This makes it ideal for applications that require a high level of reliability, such as email and file transfer.

However, the overhead associated with establishing and maintaining a connection and performing error checking can also be a disadvantage of TCP. It requires more resources and has higher overhead than other transport layer protocols such as User Datagram Protocol (UDP), which can lead to slower performance in certain situations.

#### UDP
User Datagram Protocol (UDP) is a transport layer protocol that is used to transmit data across a network. It is a connectionless protocol, which means that it does not establish a dedicated end-to-end connection between the sender and the receiver before transmitting data. Instead, it sends packets of data called datagrams directly to the destination without establishing a connection or checking to see if the packets were received.

UDP is often used for real-time applications that require low latency and high speed, such as online gaming, video conferencing, and voice over IP (VoIP). It is also used for applications that do not require a reliable end-to-end connection, such as Domain Name System (DNS) queries and Simple Network Management Protocol (SNMP) notifications.

One of the main advantages of UDP is its simplicity. Because it does not establish a connection or perform error checking, it requires fewer resources and has lower overhead than other transport layer protocols such as Transmission Control Protocol (TCP). This makes it ideal for applications that require high performance and low latency.

However, the lack of error checking and reliability can also be a disadvantage of UDP. If a packet is lost or corrupted, there is no mechanism to recover it or request a retransmission. This can lead to data loss and may make it less suitable for applications that require a high level of reliability.

### Common Ports and Protocols

##### TCP (Transmission Control Protocol) common ports:

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

##### UDP (User Datagram Protocol) common ports:

-   53 - DNS (Domain Name System)
-   67 and 68: DHCP (Dynamic Host Configuration Protocol)
-   69: TFTP (Trivial File Transfer Protocol)
-   123 - NTP (Network Time Protocol)
-   161 - SNMP (Simple Network Management Protocol)

In general, TCP is more reliable but slower, while UDP is faster but less reliable. The choice of which protocol to use depends on the specific needs of the application transmitting the data.

## Three-Way Handshake
A three-way handshake, also known as a TCP handshake, is a process used by the Transmission Control Protocol (TCP) to establish a connection between two devices before transmitting data. It involves the exchange of three messages between the devices, which are used to synchronize their sequence numbers and initiate the connection.

The three-way handshake consists of the following steps:

1.  The client (Computer A) sends a SYN (Synchronize) message to the server (Computer B), requesting the establishment of a connection. The SYN message includes a random initial sequence number (ISN) chosen by the client.

2.  The server responds with a SYN-ACK (Synchronize-Acknowledge) message, acknowledging the receipt of the SYN message and requesting the establishment of a connection. The SYN-ACK message includes its own ISN, which is chosen by the server, as well as the client's ISN plus one.

3.  The client responds with an ACK (Acknowledge) message, acknowledging the receipt of the SYN-ACK message and completing the three-way handshake. The ACK message includes the server's ISN plus one.

After the three-way handshake is complete, the devices can begin transmitting data over the connection. The three-way handshake is used to establish a connection between devices in both directions, so the process is repeated in reverse if data needs to be transmitted from the server to the client.

The three-way handshake is used by TCP to establish a connection because it ensures that both devices are ready to communicate and have synchronized their sequence numbers. It also allows each device to verify that the other device is alive and reachable.



# Introduction to Linux
## Sudo Overview
## Navigating the File System
## Users and Privileges

## Common Network Commands

- `ifconfig` / `ip a`
- `iwconfig`
- `arp -a` / `ip n`
- `ip r`
- `route`
- `ping`
*see icmp traffic
- `netstat`
*see dhcp and ups*

## Starting and Stopping Services
`sudo service service_name start/stop`

There's also a faster and more efficient way of doing this with python:
`python3 -m http.server 80`
It runs the module http.server on port 80 and hosts all the content of the folder where I ran the script

`sudo systemctl enable/disable service_name`
This enables or disables startups programs

## Installing and Updating Tools

`sudo apt update && sudo apt upgrade`
Scans all the packages installed on the computer, looks if they have any updates available and upgrades them.
*Upgrading packages can sometimes break things, you should **always** have a copy/backup of your system.*

`sudo apt autoremove`
Removes broken or not necessary packages from the system.

`sudo apt install package_name`
Installs individual packages

## Scripting with Bash

### Ping Sweeper

#### Explanation

##### `ping 10.0.2.15 -c 1 > ip.txt`


```
PING 10.0.2.15 (10.0.2.15) 56(84) bytes of data.
64 bytes from 10.0.2.15: icmp_seq=1 ttl=64 time=2.40 ms

--- 10.0.2.15 ping statistics ---
1 packets transmitted, 1 received, 0% packet loss, time 0ms
rtt min/avg/max/mdev = 2.395/2.395/2.395/0.000 ms
```

- `ping` IP address to see if it's alive
- `-c 1` to do the ping only 1 time

##### `cat ip.txt | grep "64 bytes" | cut -d " " -f 4 | tr -d ":"`

- `cat` to show the content of the file 
- `grep` to grab the line of code contained within the ""
- `cut` for cutting out the sections and writing the result to standard output
	- Using the delimeter (-d) argument to cut the 4th field (-f) using spaces (" ")
	- Using translate to get rid of the double colons (:)
   - grab the four field separated with spaces, being the IP one the fourth without the : at the end of the IP


#### IP Sweeper Script

```
#!/bin/bash
if [ "$1" = "" ]
then
echo "You forgot an IP address!"
echo "Syntax: ./ipsweep.sh 192.168.1"

else
for ip in `seq 1 254`; do
ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
done
fi
```

Bash has “positional arguments” that correspond to the arguments used to invoke a bash script.
We are going to use $1 to set the first argument to the IP we wanna sweep or ping.

#### IP Scanner Script

```
#!/bin/bash

for ip in $(cat ips.txt); do nmap $ip & done
```

We are going to use the nmap tool to scan for all the actives port within the ips.txt document we created using the IP Sweeper Script.



# Introduction to Python

[View the Full Documentation of Python](https://www.w3schools.com/python)

### Indentation
Python relies on indentation (whitespace at the beginning of a line) to define scope in the code. 
Other programming languages often use curly-brackets for this purpose.

> **Making use of a correct indentation will not only make your program not resort to errors, but it is one of the good practices of a programmer.**

### Comments

Comments can be used to explain the code, make the it more readable or to prevent execution when testing.
Comments starts with a `#`, and Python will ignore them:

```
# This is a commentary
# Everything here will be ignored by python
# This is usefull to explain what your script is doing
```

Python actually does not support multiline comments, but you can use multiline strings (not quite as intended)
Since Python will ignore string literals that are not assigned to a variable, you can add a multiline string (triple quotes) in your code, and place your comment inside it. *(see **Strings**)*

### Variables
- Python has no command for declaring a variable.
- A variable is created the moment you first assign a value to it.
- Variables do not need to be declared with any particular _type_, and can even change type after they have been set.
- String variables can be declared either by using single or double quotes
- Variable names are case-sensitive.

#### Variable Names
A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume). Rules for Python variables:

-   A variable name must start with a letter or the underscore character
-   A variable name cannot start with a number
-   A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
-   Variable names are case-sensitive (age, Age and AGE are three different variables)

**Example of legal variable names:**

> myvar = "John"  
> my_var = "John"  
> _my_var = "John"  
> myVar = "John"  
> MYVAR = "John"  
> myvar2 = "John"

**Example of illegal variable names:**

> 2myvar = "John"  
> my-var = "John"  
> my var = "John"

##### Many Values to Multiple Variables
`x, y, z = "Orange", "Banana", "Cherry"`

##### One Value to Multiple Variables
`x = y = z = "Orange"`

#### Global Variables
Variables that are created outside of a function are known as global variables.

Global variables can be used by everyone, both inside of functions and outside.

If you create a global variable and a variable inside a function with the same name, the global variable with the same name will remain as it was, global and with the original value.

```
x = "awesome"  
  
def myfunc():  
  x = "fantastic"  
  print("Python is " + x)  
  
myfunc()  
  
print("Python is " + x)
```

This will print:

```
Python is fantastic
Python is awesome
```

### Data Types

| Type     | Value                        |
| -------- | ---------------------------- |
| Text     | str                          |
| Numeric  | int, float, complex          |
| Sequence | list, tuple, range           |
| Mapping  | dict                         |
| Set      | set, frozenset               |
| Boolean  | bool                         |
| Binary   | bytes, bytearray, memoryview |
| None     | NoneType                     |

- The data type is automatically set when you assign a value to a variable
- If you want to specify the data type, you can use the constructor functions:
   - *Example: `x = str("Hello World")`*
- To verify the type of any object in Python, use the `type()` function

### Numbers
There are 3 types of numbers in python:

#### Int
Int, or integer, is a whole number, positive or negative, without decimals, of unlimited length.

```
x = 1.10  
y = 1.0  
z = -35.59
```

#### Float
Float, or "floating point number" is a number, positive or negative, containing one or more decimals.
Float can also be scientific numbers with an "e" to indicate the power of 10.

```
x = 35e3  
y = 12E4  
z = -87.7e100
```

#### Complex
Complex numbers are written with a "j" as the imaginary part

```
x = 3+5j  
y = 5j  
z = -5j
```

> - You can convert from one type to another with the `int()`, `float()`, and `complex()` methods.
> - You cannot convert complex numbers into another number type.

### Math

| Type      | Symbol | Details                   |
| --------- | ------ | ---------------------- |
| Add       | +      |                        |
| Substract | -      |                        |
| Multiply  | *      |                        |
| Exponent  | **     |                        |
| Divide    | /      | with remainder (float) |
| Divide    | //     | no remainder           |
| Modulo    | %      | take what is left over |

### Strings

Strings in python are surrounded by either single quotation marks, or double quotation marks.
`'hello'` is the same as `"hello"`

You can assign a multiline string to a variable by using three quotes (either single or double):

```
"""Lorem ipsum dolor sit amet,  
consectetur adipiscing elit,  
sed do eiusmod tempor incididunt  
ut labore et dolore magna aliqua."""
```

### String Slicing
- You can return a range of characters by using the slice syntax.
   - Specify the start index and the end index, separated by a colon, to return a part of the string.

```
b = "Hello, World!"  
print(b[2:5])
```

> The first character has index 0.

#### Slice from the start
Get the characters from the start to position 5 (not included):

```
b = "Hello, World!"  
print(b[:5])
```

By leaving out the start index, the range will start at the first character.

#### Slice to the end
Get the characters from position 2, and all the way to the end:

```
b = "Hello, World!"  
print(b[2:])
```

By leaving out the _end_ index, the range will go to the end

#### Negative Indexing
Get the characters: From: "o" in "World!" (position -5), to, but not included: "d" in "World!" (position -2):

```
b = "Hello, World!"  
print(b[-5:-2])
```

Use negative indexes to start the slice from the end of the string

### String Concatenation
- To concatenate, or combine, two strings you can use the + operator.
- To add a space between them, add a `" "`.

### String Formatting
In Python, we cannot combine strings and numbers. 
But we can combine strings and numbers by using the `format()` method!

The `format()` method takes the passed arguments, formats them, and places them in the string where the placeholders `{}` are:

```
age = 36  
txt = "My name is John, and I am {}"  
print(txt.format(age))
```

The format() method takes unlimited number of arguments, and are placed into the respective placeholders:

```
quantity = 3  
itemno = 567  
price = 49.95  
myorder = "I want {} pieces of item {} for {} dollars."  
print(myorder.format(quantity, itemno, price))
```

You can use index numbers `{0}` to be sure the arguments are placed in the correct placeholders:

```
quantity = 3  
itemno = 567  
price = 49.95  
myorder = "I want to pay {2} dollars for {0} pieces of item {1}."  
print(myorder.format(quantity, itemno, price))
```

### String Methods

| Method                                                                         | Description                                                                                  |
| ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| [capitalize()](https://www.w3schools.com/python/ref_string_capitalize.asp)     | Converts the first character to upper case                                                   |
| [casefold()](https://www.w3schools.com/python/ref_string_casefold.asp)         | Converts string into lower case                                                              |
| [center()](https://www.w3schools.com/python/ref_string_center.asp)             | Returns a centered string                                                                    |
| [count()](https://www.w3schools.com/python/ref_string_count.asp)               | Returns the number of times a specified value occurs in a string                             |
| [encode()](https://www.w3schools.com/python/ref_string_encode.asp)             | Returns an encoded version of the string                                                     |
| [endswith()](https://www.w3schools.com/python/ref_string_endswith.asp)         | Returns true if the string ends with the specified value                                     |
| [expandtabs()](https://www.w3schools.com/python/ref_string_expandtabs.asp)     | Sets the tab size of the string                                                              |
| [find()](https://www.w3schools.com/python/ref_string_find.asp)                 | Searches the string for a specified value and returns the position of where it was found     |
| [format()](https://www.w3schools.com/python/ref_string_format.asp)             | Formats specified values in a string                                                         |
| format_map()                                                                   | Formats specified values in a string                                                         |
| [index()](https://www.w3schools.com/python/ref_string_index.asp)               | Searches the string for a specified value and returns the position of where it was found     |
| [isalnum()](https://www.w3schools.com/python/ref_string_isalnum.asp)           | Returns True if all characters in the string are alphanumeric                                |
| [isalpha()](https://www.w3schools.com/python/ref_string_isalpha.asp)           | Returns True if all characters in the string are in the alphabet                             |
| [isdecimal()](https://www.w3schools.com/python/ref_string_isdecimal.asp)       | Returns True if all characters in the string are decimals                                    |
| [isdigit()](https://www.w3schools.com/python/ref_string_isdigit.asp)           | Returns True if all characters in the string are digits                                      |
| [isidentifier()](https://www.w3schools.com/python/ref_string_isidentifier.asp) | Returns True if the string is an identifier                                                  |
| [islower()](https://www.w3schools.com/python/ref_string_islower.asp)                                                                      | Returns True if all characters in the string are lower case                                  |
| [isnumeric()](https://www.w3schools.com/python/ref_string_isnumeric.asp)                                                                      | Returns True if all characters in the string are numeric                                     |
| [isprintable()](https://www.w3schools.com/python/ref_string_isprintable.asp)                                                                    | Returns True if all characters in the string are printable                                   |
| [isspace()](https://www.w3schools.com/python/ref_string_isspace.asp)                                                                      | Returns True if all characters in the string are whitespaces                                 |
| [istitle()](https://www.w3schools.com/python/ref_string_istitle.asp)                                                                       | Returns True if the string follows the rules of a title                                      |
| [isupper()](https://www.w3schools.com/python/ref_string_isupper.asp)                                                                       | Returns True if all characters in the string are upper case                                  |
| [join()](https://www.w3schools.com/python/ref_string_join.asp)                                                                           | Joins the elements of an iterable to the end of the string                                   |
| [ljust()](https://www.w3schools.com/python/ref_string_ljust.asp)                                                                          | Returns a left justified version of the string                                               |
| [lower()](https://www.w3schools.com/python/ref_string_lower.asp)                                                                          | Convers a string into lower case                                                             |
| [lstrip()](https://www.w3schools.com/python/ref_string_lstrip.asp)                                                                          | Returns a left trim version of the string                                                    |
| [maketrans()](https://www.w3schools.com/python/ref_string_maketrans.asp)                                                                     | Returns a translation table ot the used in translation                                       |
| [partition()](https://www.w3schools.com/python/ref_string_partition.asp)                                                                     | Returns a tuple where the string is parted into three parts                                  |
| [replace()](https://www.w3schools.com/python/ref_string_replace.asp)                                                                        | Returns a string where a specified value is replaced with a specified value                  |
| [rfind()](https://www.w3schools.com/python/ref_string_rfind.asp)                                                                          | Searches the string for a specified value and returns the las position of where it was found |
| [rindex()](https://www.w3schools.com/python/ref_string_rindex.asp)                                                                         | Searches the string for a specified value and returns the las position of where it was found |
| [rjust()](https://www.w3schools.com/python/ref_string_rjust.asp)                                                                         | Returns a right justified version of the string                                              |
| [rpartition()](https://www.w3schools.com/python/ref_string_rpartition.asp)                                                                     | Returns a tuple where the sitrng is parted into three parts                                  |
| [rsplit()](https://www.w3schools.com/python/ref_string_rsplit.asp)                                                                         | Splits the string at the specified separator, and returns a list                             |
| [rstrip()](https://www.w3schools.com/python/ref_string_rstrip.asp)                                                                        | Returns a trim version of the string                                                         |
| [split()](https://www.w3schools.com/python/ref_string_split.asp)                                                                         | Splits the string at the specified separator, and returns a list                             |
| [splitlines()](https://www.w3schools.com/python/ref_string_splitlines.asp)                                                                     | Splits the string at line breaks and returns a list                                          |
| [startswith()](https://www.w3schools.com/python/ref_string_startswith.asp)                                                                    | Returns True if the string starts with the specified vale                                    |
| [strip()](https://www.w3schools.com/python/ref_string_strip.asp)                                                                          | Returns a trimmed version of the string                                                      |
| [swapcase()](https://www.w3schools.com/python/ref_string_swapcase.asp)                                                                      | Swaps cases, lowercase becomes upper case and vice versa                                     |
| [title()](https://www.w3schools.com/python/ref_string_title.asp)                                                                       | Convers the first character of each word to theupper case                                    |
| [translate()](https://www.w3schools.com/python/ref_string_translate.asp)                                                                    | Returns a translated string                                                                  |
| [upper()](https://www.w3schools.com/python/ref_string_upper.asp)                                                                          | Convers a string into upper case                                                             |
| [zfill()](https://www.w3schools.com/python/ref_string_zfill.asp)                                                                          | Fills the string with a specified number of 0 values at the beginning                                                                                             |


### Escape Characters
To insert characters that are illegal in a string, use an escape character.
An escape character is a backslash `\` followed by the character you want to insert.

An example of an illegal character is a double quote inside a string that is surrounded by double quotes.

You will get an error if you use double quotes inside a string that is surrounded by double quotes:

```
txt = "We are the so-called "Vikings" from the north."
```

To fix this problem, use the escape character `\"`:

```
txt = "We are the so-called \"Vikings\" from the north."
```

#### List of all Escape Characters

| Code   | Result          |
| ------ | --------------- |
| `\'`   | Single Quote    |
| `\\`   | Backlash        |
| `\n`    | New Line        |
| `\r`    | Carriage Return |
| `\t`    | Tab             |
| `\b`    | Backspace       |
| `\f`    | Form Feed       |
| `\ooo`       | Octal value     |
| `\xhh` | Hex value       |

### Casting
There may be times when you want to specify a type on to a variable. This can be done with casting. Python is an object-orientated language, and as such it uses classes to define data types, including its primitive types.

Casting in python is therefore done using constructor functions:

- `int()` - constructs an integer number from an integer literal, a float literal (by removing all decimals), or a string literal (providing the string represents a whole number)

```
x = int(1)   # x will be 1  
y = int(2.8) # y will be 2  
z = int("3") # z will be 3
```

- `float()` - constructs a float number from an integer literal, a float literal or a string literal (providing the string represents a float or an integer)

```
x = float(1)     # x will be 1.0  
y = float(2.8)   # y will be 2.8  
z = float("3")   # z will be 3.0  
w = float("4.2") # w will be 4.2
```

- `str()` - constructs a string from a wide variety of data types, including strings, integer literals and float literals

```
x = str("s1") # x will be 's1'  
y = str(2)    # y will be '2'  
z = str(3.0)  # z will be '3.0'
```


### Functions
- A a function is defined using the `def` keyword
- To call a function, use the function name followed by parenthesis

```
def my_function():  
  print("Hello from a function")  
  
my_function()
```

#### Arguments *(or Paramenters)*
- Information can be passed into functions as arguments.
- Arguments are specified after the function name, inside the parentheses. You can add as many arguments as you want, just separate them with a comma.
- A function must be called with the correct number of arguments. Meaning that if your function expects 2 arguments, you have to call the function with 2 arguments, not more, and not less.
- 
##### The terms _parameter_ and _argument_ can be used for the same thing: information that are passed into a function.

> Arguments are often shortened to _args_ in Python documentations.

#### Keyword Arguments
You can also send arguments with the _key_ = _value_ syntax. This way the order of the arguments does not matter.

```
def my_function(child3, child2, child1):  
  print("The youngest child is " + child3)  
  
my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```

#### Arbitrary Arguments
If you do not know how many arguments that will be passed into your function, add a `*` before the parameter name in the function definition.

This way the function will receive a _tuple_ of arguments, and can access the items accordingly:

```
def my_function(*kids):  
  print("The youngest child is " + kids[2])  
  
my_function("Emil", "Tobias", "Linus")
```

### Logical Conditions
Python supports the usual logical conditions from mathematics:

-   Equals: `a == b`
-   Not Equals: `a != b`
-   Less than: `a < b`
-   Less than or equal to: `a <= b`
-   Greater than: `a > b`
-   Greater than or equal to: `a >= b`

### Booleans
In programming you often need to know if an expression is `True` or `False`.
   - You can evaluate any expression in Python, and get one any of these two answers.
When you compare two values, the expression is evaluated and Python returns the Boolean answer.
   - These are done by using the logical conditions explained above.

```
print(10 > 9)  
print(10 == 9)  
print(10 < 9)
```

##### Most Values are True
Almost any value is evaluated to `True` if it has some sort of content.
- Any string is `True`, except empty strings.
- Any number is `True`, except `0`.
- Any list, tuple, set, and dictionary are `True`, except empty ones.

##### Some Values are False
In fact, there are not many values that evaluate to `False`, except:
- Empty values, such as `()`, `[]`, `{}`, `""`, 
- The number `0`
- The value `None`
- And of course the value `False` evaluates to `False`.

#### Truth Table of Python 

| When                                     | Return Value |
| ---------------------------------------- | ------------ |
| All truthy values                        | True         |
| All falsy values                         | False        |
| One truthy values (all others are falsy) | True         |
| One falsy value (all others are truth)   | True         |
| Empty iterable                           | False        |

-----
##### NOT
| NOT       | Return Value |
| --------- | ------------ |
| not False | True         |
| not True  | False        |

##### AND

| AND             | Return Value |
| --------------- | ------------ |
| True and False  | False        |
| True and True   | True         |
| False and True  | False        |
| False and False | False        |

##### NOT AND

| NOT AND               | Return Value |
| --------------------- | ------------ |
| not (True and False)  | True         |
| not (True and True)   | False        |
| not (False and True)  | True         |
| ot (False and False) | True             |

##### OR

| OR             | Return Value |
| -------------- | ------------ |
| True or False  | True         |
| True or True   | True         |
| False or True  | True         |
| False or False | False        |

##### NOT OR

| NOT OR               | Return Value |
| -------------------- | ------------ |
| not (True or False)  | False        |
| not (True or True)   | False        |
| not (False or True)  | False        |
| not (False or False) | True         |

##### !=

| !=     | Return Value |
| ------ | ------------ |
| 1 != 0 | True         |
| 1 != 1 | False        |
| 0 != 1 | True         |
| 0 != 0 | False        |

##### ==

| ==     | Return Value |
| ------ | ------------ |
| 1 == 0 | False        |
| 1 == 1 | True         |
| 0 == 1 | False        |
| 0 == 0 | True             |


-----

### Conditional Statements *(If...Else)*
##### If
If the condition is true, do something.

```
a = 33  
b = 200  
if b > a:  
  print("b is greater than a")
```

##### Elif
The elif keyword is pythons way of saying "if the previous conditions were not true, then try this condition".

```
a = 33  
b = 33  
if b > a:  
  print("b is greater than a")  
elif a == b:  
  print("a and b are equal")

```

##### Else
The else keyword catches anything which isn't caught by the preceding conditions.

```
a = 200  
b = 33  
if b > a:  
  print("b is greater than a")  
elif a == b:  
  print("a and b are equal")  
else:  
  print("a is greater than b")
```

##### Nested if
You can have `if` statements inside `if` statements, this is called _nested_ `if` statements.

```
x = 41  
  
if x > 10:  
  print("Above ten,")  
  if x > 20:  
    print("and also above 20!")  
  else:  
    print("but not above 20.")
```

##### And
The and keyword is a logical operator, and is used to combine conditional statements:

```
a = 200  
b = 33  
c = 500  
if a > b and c > a:  
  print("Both conditions are True")
```

##### Or
The `or` keyword is a logical operator, and is used to combine conditional statements:

```
a = 200  
b = 33  
c = 500  
if a > b or a > c:  
  print("At least one of the conditions is True")
```

##### Pass
`if` statements cannot be empty, but if you for some reason have an `if` statement with no content, put in the `pass` statement to avoid getting an error.

```
a = 33  
b = 200  
  
if b > a:  
  pass
```

#### **Ternary Operators** or **Conditional Expressions**.
##### Short Hand If
If you have only one statement to execute, you can put it on the same line as the if statement.

```
if a > b: print("a is greater than b")
```

##### Short Hand If...Else
If you have only one statement to execute, one for if, and one for else, you can put it all on the same line:

```
a = 2  
b = 330  
print("A") if a > b else print("B")
```

You can also have multiple else statements on the same line:

*One line if else statement, with 3 conditions:*

```
a = 330  
b = 330  
print("A") if a > b else print("=") if a == b else print("B")
```

### Data Collection *(Lists, Tuple, Set, Dictionary)*
Python has 4 built-in data types to store collections of Data, all with different qualities and usage.

#### Lists
Lists are created using square brackets:

```
thislist = ["apple", "banana", "cherry"]  
print(thislist)
```

List items are **ordered**, **changeable**, and **allow duplicate values**.
List items are **indexed**, the first item has index `[0]`, the second item has index `[1]` etc.

##### Ordered
When we say that lists are ordered, it means that the items have a defined order, and that order will not change.
If you add new items to a list, the new items will be placed at the end of the list.

> There are some [list methods](https://www.w3schools.com/python/python_lists_methods.asp) that will change the order, but in general: the order of the items will not change.

##### Changeable
The list is changeable, meaning that we can change, add, and remove items in a list after it has been created.

##### Allow Duplicates
Since lists are indexed, lists can have items with the same value:

```
thislist = ["apple", "banana", "cherry", "apple", "cherry"]  
print(thislist)
```

#### Tuples
Tuples are written with round brackets:

```
thistuple = ("apple", "banana", "cherry")  
print(thistuple)
```

Tuple items are **ordered**, **unchangeable**, and **allow duplicate values**.
Tuple items are **indexed**, the first item has index `[0]`, the second item has index `[1]` etc.

##### Ordered
When we say that tuples are ordered, it means that the items have a defined order, and that order will not change.

##### Unchangeable
Tuples are unchangeable, meaning that we cannot change, add or remove items after the tuple has been created.

##### Allow Duplicates
Since tuples are indexed, they can have items with the same value:

#### Sets
Sets are written with curly brackets:

```
thisset = {"apple", "banana", "cherry"}  
print(thisset)
```

A set is a collection which is **unordered**, **unchangeable**, and **do not allow duplicates**.
Sets are **unindexed**.

- Set  _items_ are unchangeable, but you can remove items and add new items.
- Sets are unordered, so you cannot be sure in which order the items will appear.

##### Unordered

Unordered means that the items in a set do not have a defined order.
Set items can appear in a different order every time you use them, and cannot be referred to by index or key.

##### Unchangeable

Set items are unchangeable, meaning that we cannot change the items after the set has been created.
Once a set is created, you cannot change its items, but you can remove items and add new items.

##### Duplicates Not Allowed

Sets cannot have two items with the same value.


```
thisset = {"apple", "banana", "cherry", "apple"}  
  
print(thisset)
```

The output of the example above will be:

```
{'banana', 'cherry', 'apple'}
```

#### Dictionaries
Dictionaries are written with curly brackets, and have keys and values:

```
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
print(thisdict)
```

Dictionaries are used to store data values in key:value pairs.
A dictionary is a collection which is **ordered**, **changeable** and **do not allow duplicates**.

> As of Python version 3.7, dictionaries are _ordered_. In Python 3.6 and earlier, dictionaries are _unordered_.

##### Ordered or Unordered?
When we say that dictionaries are ordered, it means that the items have a defined order, and that order will not change.

Unordered means that the items does not have a defined order, you cannot refer to an item by using an index.

##### Changeable

Dictionaries are changeable, meaning that we can change, add or remove items after the dictionary has been created.

##### Duplicates Not Allowed

Dictionaries cannot have two items with the same key, if it does, the first value will be overwritten:

```
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964,  
  "year": 2020  
}  
print(thisdict)
```


zx