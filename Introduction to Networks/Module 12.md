# IPv6 ADDRESSING

### 1. IPv4 Issues

        Need for IPv6, IPv4 address exhaustion due to increasing internet population and growth of the Internet of Things (IoT).
        IPv6 provides: A 128-bit address space a solution for IPv4 limitations.
### 2. IPv4 and IPv6 Coexistence
        Migration from IPv4 to IPv6 will take years.
        Techniques for Coexistence with IPv4:
         * Dual Stack: Devices run both IPv4 and IPv6 protocols.
         * Tunneling: IPv6 packets are encapsulated within IPv4 packets.
         * Translation: NAT64 enables communication between IPv4 and IPV6 devices.
         Goal - Acheive native IPv6 communication
### 3. IPv6 Representation
    a. IPv6 Addressing Formats
      IPv6 addresses are:
      128 bits long
      Written in Hexadecimal
      Case-insensitive
    b. Preferred format: x:x:x:x:x:x:x:x, where each "x" consists of four hexadecimal values.
    Example: 2001:0db8:0000:1111:0000:0000:0000:0200
    Hextet: Informal term for a 16-bit segment (4 hexadecimal digits)
    Rule 1: Remove Leading Zeros
    Example: 01ab → 1ab
    Rule 2: use "::" to represent once contiguous segment of zeros.
    Example: 2001:0db8:0000:1111:0000:0000:0000:0200 → 2001:db8:0:1111::200
### 4.IPv6 address types

    IPv6 Prefix Length - Identifies the network portion of the address
                       - Represented in slash notation 
                       - Recommended prefix length: /64 suitable for most networks.
    Types of IPv6 Unicast Addresses 
    Global Unicast Address (GUA): Globally routable on the IPv6 internet.
                       - Assigned from the range 2000::/3
    Link-Local Address (LLA) - Required for all IPv6-enabled devices.
                       - Used for communication on the same link.
                       - Range fe80::/10
    Unique Local Address (ULA) - Range: fc00::/7
                       - Similar to IPv4 provate addresses but nit routable.
                       - Used for Local communication within a site.
                       - Devices that do not access other networks.
    IPv6 GUA structure 
    Global Routing Prefix - Assigned by ISPs
                       - Identifies the network
    Subnet ID - Used to create subnets within the network.
    Interface ID - Host portion of the address.
                       - Recommended size: 64 bits  
                       
                      
                       
