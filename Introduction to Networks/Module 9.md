# ADDRESS RESOLUTION

### 1. MAC and IP

       Destination on Same Network
       Two primary addresses on an Ethernet LAN:
       -Layer 2 address delivers frames between NICs on the same network
       - If destination IP is in the same network, desination MAC is the of the desitnation device.

       Destination on Remote Network
       - If destination IP is on a remote network, destination MAC address is the default gateway.
       Address resolution:
       - IPv4 uses ARP to map IP to MAC
       - IPv6 uses ICMP for similar funtionality.
#### 2. ARP (Address Resolution Protocol)

  ARP Resolves IPv4 addresses to MAC address and Maintains a table of IPv4-to-MAC mappings.

      a. Funtions:
      Steps for sending frame:
      1. Device searches ARP table for destination IPv4 and MAC
      2. Local Network: Searches for destination IP's MAC.
      3. Remote Network: Searches for default gateway's MAC.
      4. If no entry, send an ARP request.
      5. ARP reply adds the resolved MAC address to the table.
      b. ARP Table Maintenance 
        - Entries removed when ARP cache time expires.
        - Duration varies by operating system.
        - Entries can be manually removed by administrators.
      c. Tools
        - Cisco routers: "show ip arp" displays the ARP Table.
        - Windows 10: arp -a shows arp table.
      d. Issues
        - Excessive ARP broadcasts can redure performance.
        - ARP spoofing (poisoning) attacks:
          -Threat actors spoof replies to alter ARP tables.
          -Mitigation: Enterprise level-switches with built-in protections.

  IPv6 Neighbor Discovery

  ND resolved MAC addresses, discovers routers, and redirects traffic.
  ICMPv6 messages used:

      Neighbor Solicitation (NS) and Neighbor Adverstisement (NA): Address Resolution
      Router Solicitation (RS) and Router Advertisement (RA): Router discovery
      Redirect messages: Better next-hop selection.

  IPv6 address resolution - IPv6 devices resolve MAC address of known IPv6 addresses
  Neighbor Solicitation Messages: Sent using special multicast Ethernet and IPv6 addresses.
  
          
    
