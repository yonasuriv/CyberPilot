
## Sudo Overview
`sudo` is a Unix-based command that stands for "superuser do." It allows a user to execute commands with the privileges of another user, typically the superuser or root user.

In most Unix-based operating systems, the superuser or root user has full access to all system resources and can perform any action on the system, including modifying system files and installing software. This level of access is necessary for certain tasks, but it also carries a significant risk of accidentally damaging the system.

`sudo` allows regular users to perform tasks that require superuser privileges, but it also requires the user to enter their own password before executing the command. This provides an additional level of security and helps prevent accidental or malicious damage to the system.

For example, if a regular user needs to install a new software package, they can use the `sudo` command to execute the `apt-get install` command as the superuser, allowing them to install the package without logging in as the superuser. This allows users to perform necessary tasks while still maintaining some level of security.

Another example would be trying to see the /etc/shadow file, without doing the `sudo` command we will get a **Permission Denied**

## The Hierarchical Structure
In a Linux-based operating system, the file system is organized in a hierarchical structure, with a single root directory at the top of the hierarchy. All other files and directories on the system are contained within the root directory or one of its subdirectories.

Here is an overview of the main directories in a typical Linux file system hierarchy:

-   `/` (root) - The root directory is the top-level directory in the file system hierarchy. It contains all other files and directories on the system.
-   `/bin` - This directory contains essential user command binaries, such as `ls`, `cp`, and `mv`.
-   `/sbin` - This directory contains essential system command binaries, such as `init` and `shutdown`.
-   `/etc` - This directory contains configuration files for the system and installed applications.
-   `/dev` - This directory contains device files that represent devices connected to the system, such as printers and disk drives.
-   `/proc` - This directory is a virtual filesystem that contains information about the system's hardware and running processes.
-   `/var` - This directory contains variable data such as log files, cache files, and temporary files.
-   `/tmp` - This directory is a location for storing temporary files that are deleted when the system reboots.
-   `/usr` - This directory contains user programs and data, such as libraries and documentation.
-   `/home` - This directory contains the home directories for individual users on the system. Each user has their own subdirectory under `/home`, where they can store their personal files.

This is just a high-level overview of the main directories in a Linux file system. There are many other subdirectories within these directories, and the exact structure may vary depending on the specific Linux distribution and system configuration.

## Navigating the File System

To navigate the file system, you can use the `cd` command to change your current working directory. For example, to change to the root directory, you would use the command `cd /`. To change to a subdirectory within your current working directory, you can use a relative path, such as `cd subdirectory`. To change to a directory elsewhere in the file system, you can use an absolute path, such as `cd /home/user/documents`.

You can also use the `ls` command to list the files and directories in your current working directory. The `ls -l` command will provide a more detailed listing, including the permissions, ownership, and size of each file.

To create a new directory, use the `mkdir` command followed by the name of the directory you want to create. For example, `mkdir new_directory`. To remove a directory, use the `rmdir` command followed by the name of the directory you want to delete.

By using these commands and understanding the file system structure, you can easily navigate and manage the files and directories on your Linux system.

To create a new file, simply use the `touch` command. To remove a file, use the `rm` command followed by the name of the file.

## Users and Privileges
When doing `ls -la` command, you will see all the folders and files within the directory, listed, including the hidden ones.

| d         | r    | w     | x       | r    | w     | x       | r    | w     | x       | kali  | kali  | filename |
| --------- | ---- | ----- | ------- | ---- | ----- | ------- | ---- | ----- | ------- | ----- | ----- | ------------ |
| Directory | Read | Write | Execute | - | - | - | - | - | - | Owner | Owner | File/Folder             |

On each line, the first character identifies the type of entry that is being listed. If it is a dash (`-`) it is a file. If it is the letter `d` it is a directory.

The next nine characters represent the settings for the three sets of permissions.

-   The first three characters show the permissions for the user who owns the file (_user permissions_).
-   The middle three characters show the permissions for members of the file’s group (_group permissions_).
-   The last three characters show the permissions for anyone not in the first two categories (_other permissions_).

There are three characters in each set of permissions. The characters are indicators for the presence or absence of one of the permissions. They are either a dash (`-`) or a letter. If the character is a dash, it means that permission is not granted. If the character is an `r`, `w`, or an `x`, that permission has been granted.

The letters represent:

-   _r_: Read permissions. The file can be opened, and its content viewed.
-   _w_: Write permissions. The file can be edited, modified, and deleted.
-   _x_: Execute permissions. If the file is a script or a program, it can be run (executed).

For example:

-    `---` means no permissions have been granted at all.
-    `rwx` means full permissions have been granted. The read, write, and execute indicators are all present.

For example, to give read and write permissions to the owner and read-only permissions to the group and others for a file called `file.txt`, you would use the command `chmod 644 file.txt`.

### Permission Syntax
To use `chmod` to set permissions, we need to tell it:

-   _Who:_ Who we are setting permissions for.
-   _What_: What change are we making? Are we adding or removing the permission?
-   _Which_: Which of the permissions are we setting?

We use indicators to represent these values, and form short “permissions statements” such as `u+x`, where “u” means ” user” (who), “+” means add (what), and “x” means the execute permission (which).

The “who” values we can use are:

-   _u_: User, meaning the owner of the file.
-   _g_: Group, meaning members of the group the file belongs to.
-   _o_: Others, meaning people not governed by the `u` and `g` permissions.
-   _a_: All, meaning all of the above.

If none of these are used, `chmod` behaves as if “`a`” had been used.

The “what” values we can use are:

-   _–_: Minus sign. Removes the permission.
-   _+_: Plus sign. Grants the permission. The permission is added to the existing permissions. If you want to have this permission and only this permission set, use the option, described below.
-   _=_: Equals sign. Set a permission and remove others.

The “which ” values we can use are:

-   _r_:  The read permission.
-   _w_: The write permission.
-   _x_: The execute permission.

#### Setting Permissions for Multiple Files
We can apply permissions to multiple files all at once.
Let’s say we want to remove the read permissions for the “other” users from files that have a “.page” extension. We can do this with the following command:

`chmod o-r *.page`

#### Numerical Shorthand

Another way to use `chmod` is to provide the permissions you wish to give to the owner, group, and others as a three-digit number. The leftmost digit represents the permissions for the owner. The middle digit represents the permissions for the group members. The rightmost digit represents the permissions for the others.

The digits you can use and what they represent are listed here:

-   0: (000) No permission.
-   1: (001) Execute permission.
-   2: (010) Write permission.
-   3: (011) Write and execute permissions.
-   4: (100) Read permission.
-   5: (101) Read and execute permissions.
-   6: (110) Read and write permissions.
-   7: (111) Read, write, and execute permissions.

Each of the three permissions is represented by one of the bits in the binary equivalent of the decimal number. So 5, which is 101 in binary, means read and execute. 2, which is 010 in binary, would mean the write permission.

Using this method, you set the permissions that you wish to have; you do not add these permissions to the existing permissions. So if read and write permissions were already in place you would have to use 7 (111) to add execute permissions. Using 1 (001) would remove the read and write permissions and add the execute permission.

Let’s add the read permission back on the “.page” files for the others category of users. We must set the user and group permissions as well, so we need to set them to what they are already. These users already have read and write permissions, which is 6 (110). We want the “others” to have read and permissions, so they need to be set to 4 (100).

The following command will accomplish this:

`chmod 664 *.page

As we can see, the read permission has been removed from the “.page” files for the “other” category of users. No other files have been affected.

If we had wanted to include files in subdirectories, we could have used the `-R` (recursive) option.

`chmod -R o-r *.page`

## Common Network Commands

#### View and Manage Network Interfaces
The following commands are used on Linux to view and manage network interfaces on a system. It stands for "interface configuration," and it allows you to view the IP addresses, MAC addresses, and other information about the network interfaces on your system, as well as configure the basic settings of these interfaces.

##### `ifconfig`

-   `ifconfig` - displays a summary of all network interfaces on the system.
-   `ifconfig eth0` - displays detailed information about the `eth0` interface.
-   `ifconfig eth0 192.168.1.100 netmask 255.255.255.0` - assigns the IP address `192.168.1.100` with a netmask of `255.255.255.0` to the `eth0` interface.
-   `ifconfig eth0 down` - disables the `eth0` interface.

##### `ip a`

-   `ip a` - displays a summary of all network interfaces on the system.
-   `ip a show eth0` - displays detailed information about the `eth0` interface.
-   `ip a add 192.168.1.100/24 dev eth0` - adds the IP address `192.168.1.100` with a netmask of `/24` to the `eth0` interface.
-   `ip a del 192.168.1.100/24 dev eth0` - removes the IP address `192.168.1.100` with a netmask of `/24` from the `eth0` interface.

By using either `ifconfig` or `ip a`, you can view and manage the network interfaces on your system, which can be useful for troubleshooting network issues or configuring network settings.

##### Key Differences

`ifconfig` and `ip a` are both Linux commands that are used to view and manage network interfaces on a system. However, there are a few key differences between the two commands:

-   `ifconfig` is an older command that has been around for a long time and is available on most Unix-based systems. `ip a`, on the other hand, is a more modern command that was introduced as part of the `iproute2` package and is available on newer Linux systems.
-   `ifconfig` only allows you to view and modify the basic settings of a network interface, such as its IP address, netmask, and MAC address. `ip a`, on the other hand, has a more flexible and powerful syntax that allows you to view and modify a wider range of settings for a network interface, including IPv4 and IPv6 addresses, link-level attributes, and multicast addresses.
-   `ifconfig` is deprecated and is not actively maintained. `ip a` is the recommended command for managing network interfaces on Linux systems.

Overall, `ip a` is the more powerful and flexible of the two commands and is the recommended tool for managing network interfaces on a Linux system. However, `ifconfig` is still widely used and is often available on older or embedded systems.

#### Configure Wireless Network Interfaces

##### `iwconfig`

The `iwconfig` command is a Linux command that is used to configure wireless network interfaces. It stands for "wireless configuration," and it allows you to view and modify the settings of wireless network interfaces on your system.

To use `iwconfig`, you can specify the name of the wireless interface you want to configure, as well as various options and arguments to control the specific settings you want to modify. Here are a few examples of how you can use `iwconfig`:

-   `iwconfig` - displays a summary of all wireless interfaces on the system.
-   `iwconfig wlan0` - displays detailed information about the `wlan0` interface.
-   `iwconfig wlan0 essid MyWiFi` - sets the ESSID (network name) of the `wlan0` interface to `MyWiFi`.
-   `iwconfig wlan0 mode managed` - sets the `wlan0` interface to operate in managed mode.
-   `iwconfig wlan0 key off` - disables encryption on the `wlan0` interface.

The `iwconfig` command is a useful tool for configuring and troubleshooting wireless network interfaces on a Linux system. It can help you modify the settings of your wireless interface to match the needs of your network and ensure that you have a stable and secure connection.

#### View and Modify Address Resolution Protocol

The following commands are Linux and Unix utilities that are used to view and modify the Address Resolution Protocol (ARP) cache on a system. ARP is a protocol that is used to map the IP addresses of devices on a network to their physical (MAC) addresses. The ARP cache is a table that stores the IP-to-MAC mappings for recently resolved addresses, and it is used to speed up the process of resolving IP addresses to MAC addresses.

##### `arp -a` 

-   `arp` - displays the ARP cache for all interfaces on the system.
-   `arp -a` - displays the ARP cache for all interfaces in a more human-readable format.
-   `arp -i eth0` - displays the ARP cache for the `eth0` interface.
-   `arp -s 192.168.1.100 00:11:22:33:44:55` - adds a static entry to the ARP cache for the IP address `192.168.1.100` and the MAC address `00:11:22:33:44:55`.

The `arp` command is a useful tool for troubleshooting and managing the ARP cache on a system. It can help you view the IP-to-MAC mappings for devices on your network, and it can also allow you to add static entries to the ARP cache to improve the performance of your network.

##### `ip n`

-   `ip n` - displays the ARP cache for all interfaces on the system.
-   `ip n show` - displays the ARP cache for all interfaces in a more human-readable format.
-   `ip n add 192.168.1.100 lladdr 00:11:22:33:44:55 dev eth0` - adds a static entry to the ARP cache for the IP address `192.168.1.100` and the MAC address `00:11:22:33:44:55` on the `eth0` interface.
-   `ip n replace 192.168.1.100 lladdr 00:11:22:33:44:55 dev eth0` - replaces an existing entry in the ARP cache for the IP address `192.168.1.100` on the `eth0` interface with a new MAC address of `00:11:22:33:44:55`.

The `ip n` command is a useful tool for troubleshooting and managing the ARP cache on a system. It has a more modern and flexible syntax than the `arp` command, and it allows you to view and modify the ARP cache for all

##### Key Differences

`arp` and `ip n` are both Linux commands that are used to view and manage the Address Resolution Protocol (ARP) cache on a system. The ARP cache is a table that stores the IP-to-MAC mappings for recently resolved addresses, and it is used to speed up the process of resolving IP addresses to MAC addresses.

Here are the main differences between `arp` and `ip n`:

-   Syntax: `arp` and `ip n` have different syntax and options. `arp` has a more traditional syntax with options such as `-a`, `-i`, and `-s`, while `ip n` has a more modern and flexible syntax with options such as `show`, `add`, and `replace`.
-   Compatibility: `arp` is an older command that is available on most Unix-based systems, while `ip n` is a more modern command that is part of the `iproute2` package and is available on newer Linux systems.
-   Functionality: `arp` has more limited functionality compared to `ip n`. It only allows you to view and modify the ARP cache for a specific interface, while `ip n` has a more flexible and powerful syntax that allows you to view and modify the ARP cache for all interfaces, as well as manage other aspects of network address resolution such as IPv6 neighbor discovery.

Overall, `ip n` is the more modern and flexible of the two commands and is the recommended tool for managing the ARP cache on a Linux system. However, `arp` is still widely used and is often available on older or embedded systems.

#### View and Modify the Kernel Routing Table

##### `ip r`
The `ip r` command is a Linux command that is used to view and modify the kernel routing table. The kernel routing table is a data structure that stores the routes that the kernel uses to forward data packets between network interfaces. It consists of a list of destination networks, their associated next hop routers, and the interfaces through which the packets should be sent.

To use the `ip r` command, you can specify various options and arguments to control the type and level of information displayed. Here are a few examples of how you can use `ip r`:

-   `ip r` - displays the kernel routing table.
-   `ip r add default via 192.168.1.1 dev eth0` - adds a default route to the kernel routing table, specifying that all packets that are not destined for a specific network should be forwarded to the router at `192.168.1.1` through the `eth0` interface.
-   `ip r delete default` - deletes the default route from the kernel routing table.
-   `ip r replace 10.0.0.0/8 via 192.168.1.1 dev eth0` - replaces an existing route for the network `10.0.0.0/8` with a new route through the router at `192.168.1.1` on the `eth0` interface.

The `ip r` command is a useful tool for managing the kernel routing table on a Linux system. It allows you to view the routes that the kernel is using to forward data packets, and it also allows you to add, delete, and modify routes to customize the routing behavior of your system.

#### Manipulate the IP Routing Table

##### `route`
The `route` command is a command line utility that is used to display and manipulate the IP routing table in a Unix-like operating system. It is used to show the route that packets take when they are sent to a specified network or host. The `route` command can be used to add, delete, and modify routes in the IP routing table.

For example, to add a route to the routing table on a Linux system, you might use a command like this:

```
route add -net 192.168.0.0 netmask 255.255.255.0 gw 192.168.0.1
```

This command adds a route to the routing table that directs traffic for the network with the address range `192.168.0.0` to `192.168.0.255` to go through the gateway at `192.168.0.1`.

#### Test Connectivity and Latency

##### `ping`
The `ping` command is a Linux and Unix utility that is used to test the connectivity and latency between two devices on a network. It works by sending an Internet Control Message Protocol (ICMP) echo request message to a specified host and waiting for an echo reply.

To use the `ping` command, you specify the hostname or IP address of the device you want to ping, and the command will send a series of echo request messages and display the results.

#### View detailed information about Network Connections

##### `netstat`
The `netstat` command is a Linux and Unix utility that is used to display information about network connections, routing tables, and network interfaces. It stands for "network statistics," and it allows you to view detailed information about the network activity on your system.

To use the `netstat` command, you can specify a variety of options and arguments to control the type and level of information displayed. Here are a few examples of how you can use `netstat`:

-   `netstat -a` - displays a list of all active network connections, including the local and remote addresses, the protocol in use, and the state of the connection.
-   `netstat -t` - displays a list of all active TCP connections, including the local and remote addresses and the state of the connection.
-   `netstat -r` - displays the kernel routing table, including the destination, gateway, and interface for each route.
-   `netstat -i` - displays a list of all network interfaces, including the name, MTU, and statistics for each interface.

The `netstat` command is a useful tool for troubleshooting network issues and monitoring network activity on a system. It can help you identify active connections and routing issues, and it can also provide insight into the performance and utilization of your network interfaces.


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
- `-c 1` to ping only one time


##### `cat ip.txt | grep "64 bytes" | cut -d " " -f 4 | tr -d ":"`

- `cat` to show the content of the file 
- `grep` to grab the line of code contained within the ""
- `cut` for cutting out the sections and writing the result to standard output
	- Using the delimeter (`-d`) argument to cut or grab the IP using spaces (`" "`) on the 4th field (`-f`)
	- Using translate (`tr`) to get rid of the double colons (`":"`)



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



