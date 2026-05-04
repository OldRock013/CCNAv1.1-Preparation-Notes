# NETWORK LAYER

### 1. Network Later Characteristics

  a. IP Protocols (IPv4 and IPv6) are primary communication protocols.

  b. Provides services for end devices to exchange data:

        Addressingend devices
        Encapsulation of transport layer segments into IP packets
        Routing packets through the network
        De-encapsulation at receiving end
 
 c. IP Encapsulation

       Encapsulates transport layer segments into IP packets.
       IP packets remain unchanged from source to destination unless altered by NAT.
  
  d. Characteristics of IP 

      Connectionless - No conection setup before transmission, no control information like acknowledgements.
      Best Effort - Does not guarantee delivery, no resend mechanism, no acknowledgement expected.
      Media Independent - Operates over any merdia type with out concern for frames types or media specifics.
                        - Establishes MTU based in data link layer's control information.
                        - IPv4 supports packet fragmentation, IPv6 does not.
                        - Fragmentation in IPv4 icreases latency, IPv6 avoids this by bot fragmenting.

### 2. IPv4 Packet Header

  It Ensures correct routing of the packet. Contains information for network layer processing: Routing direction and network layer information fields.

  a. Header Fileds
<img width="1061" height="362" alt="image" src="https://github.com/user-attachments/assets/881b1124-6ed0-44a5-83c3-18246a8d3388" />

    Version (4 bits)- Identifies IP Version
    DS (Differentiated Services) (4 bits) - Used for Quality of Service (QoS), inculde DSCP or ToS.
    Header Checksum (16 bits) - Detects corruption in the header.
    Time to Live (TTL) - Hop count limit, decremented by each router, packet discarded if Zero.
    Protocol (8 bits) - Identifies encapsulated protocol (eg., ICMP, TCP, USDP).
    Source IPv4 Address (32 bits) - IP address of the packet's origin.
    Destination IPv4 Address (32 bits) - IP address where the packet is destined.

### 3. IPv6 Packets

  Limitations of IPv4: Address depletion, lack of end-to-end connectivity due to NAT, increased network complexity.

  IPv6 Overview: Developed by IETF to overcome IPv4 limotations:

  IPv6 Packet Header - Fixed 40 bytes, fewer fields for performance.
  <img width="1060" height="397" alt="image" src="https://github.com/user-attachments/assets/f8285587-75b9-4909-b0ff-8d9ed36a5f1e" />

    Sinificant Fields:
    Version (4 bits) - Identifies IP version (6 in this case)
    Traffic Class (8 bits) - Similar to DiffServ in IPv4 for QoS.
    Flow Label (20 bits) Identifies packets belonging to the same flow for consistent handling.
    Payload length (16 bits) Length of the data portion.
    Next Header (8 bits) - Identifies next protocol in the packet.
    Hop Limit (8 bits) - Replaces TTL in IPv4, decremented by each router.
    Source IPv6 address (128 bits)
    Destination IPv6 address (128 bits)

### 4. How a Host Routes

Packets are created at the source with each host having its routing table.

    Destinations can be:
    Itself - Loopback address
    Local Hosts - same LAN
    Remote Host - Outside LAN or Different network.
Determination of Local vs Remote

    For IPv4: uses IP address, subnet mask, and destination IP to determine.
    For IPv6: uses network address and prefix from the local router.

Local Traffic is sent out the host's interface to be handled by network devices.

Remote traffic is sent to default gateway

Default Gateway 

    Must have an IP address on the same LAN, capable of forwarding traffic off the LAN
    Critical for devices to communicate outside their LAN
Host Routes to the Default Gateway

    Known through static configuration or DHCP (IPv4)
    IPv6 uses Router Solicitation or manual configuration
    Static route on host's routingt table as the last resort.
    
    
