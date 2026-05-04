# IPv4 ADDRESSING

### 1. IPv4 Address Structure

a. Network and Host Portions

    IPv4 is 32-bit hierarchical address divided in to 
    Network Portion: Identifies the network 
    Host Portion: Idetifies the host within the network.
    Determined by a Subnet Mask
b. Subnet Mask

    Determines network and host portions by comparing each bit of the IPv4 address.
    Logical ANDing operation is used to extract the network address.

c. Prefix Length

    Simplifies the subnet mask notation. Prefix length represents the number of bits allocated to the network
    Example:
    /8 → 255.0.0.0
    /16 → 255.255.0.0
    /24 → 255.255.255.0

d. Network, Host, Broadcast Addresses

    Network Address: First address in the range (e.g., 192.168.10.0).
    Host Addresses: Range of usable IPs (e.g., 192.168.10.1 to 192.168.10.254).
    Broadcast Address: Last address in the range (e.g., 192.168.10.255).
### 2. IPv4 Unicast, Broadcast, and Multicast

    Sends data to a single destination (e.g., PC to printer).
    Unicast: Sends data to a single destination
    Broadcast: Sends data to all devices on a network
    Multicast: Sends data to a group of devices with a multicast group address.

### 3. Types of IPv4 Addresses

    a. Public ad private 
       Public IPs: Globally routable
       Private IPs: Non-routable, used internally
       10.0.0.0/8
       172.16.0.0/12
       192.168.0.0/16
    b. Loopback: 127.0.0.1 for testing TCP/IP
       Link-Local: 169.254.0.0/16 for self configuration.
    c. Legacy Classful Addressing
       Class A: 0.0.0.0/8
       Class B: 128.0.0.0/16
       Class C: 192.0.0.0/24
       Class D: 224.0.0.0/4 (Multicast)
       Class E: 240.0.0.0/4 (Experimental)
### 4. Network Segmentation
    a. Broadcast Domains - Routers limit broadcasts to specific domains.
                         - Switches propagate broadcasts to all interfaces except the source.
    b.Problems with large broadcast doamains - Execssinge traffic affects performance.
                         - Solution: Divide networks using subnetting.
    c. Reasons for Subnetting - Reduces traffic.
                         - Implements Security policies.
                         - Limits the impact of broadcast traffic.
### 5. Subnetting an IPv4 Network
    a. Subnetting on Octet Boundaries - /8, /16, /24 for simpler subnetting.
    Example: Subnetting 10.0.0.0/8 into /16 or /24
    b. Subnetting within Octets - Smaller Subnets for specific needs.
    Example: /25 2 subnets, 126 hosts
    /30 64 subnets, 2 hosts.
### 6. Variable Length Subnet Masking (VLSM)

  Optimizes address usage by dividing subnets further based on needs.
  Example:
  Optimizes address usage by dividing subnets further based on needs.
  Example: Use /30 for point-to-point links and /27 for LANs.

  For Full Tutorial of [Subnetting](URL"https://youtube.com/playlist?list=PLartSvhZE-WCJzk8yU2_KGJb8J97xVjPP&si=GPd6ZIaQ31U-Gxfo")
  
    
      
