# Ethernet Switching

### 1. Ethernet Frame

    a. Ethernet Encapsulation - operates in data link and the physical layer. Defined by IEEE 802.2 and 802.3 standards.
    b. Data Link Sublayers
       LLC Sublayer (802.2) - Communicates betwneen networking software and device hardware.
                            - Identifies network later protocol used in the frame.
       MAC Sublayer (802.3, 802.11 or 802.15) - Responsible for data encapsulation, media access control and addressing.
    c. Frame Size - Minumim ise 64 bytes, Maximum 1518 bytes (excluding preamble)

### 2. Ethernet MAC Address
    
    a. MAC address in Ethernet VLAN - each device on an ethernet LAN has unique 48bit MAC Address | 24-bit for OUI; 24-bit for vendor assigned.
    b. Frame Processing - Ethernet header include source and destination MAC address.
                        - NIC checks if the destination MAC mathces; if not, discards frame unless it's a broadcast or multicast.
    c. Types of MAC addresses:
        Unicast MAC address - used for one-to-one communication.
                            - ARP for IPv4, ND for IPv6 resolve IP to MAC.
        Broadcast MAC Address - ff-ff-ff-ff-ff-ff, processed by all devices on LAN, not forwarded by routers.
        Multicast MAC address - 01-00-5E for IPv4 multicast, 33-33 for IPv6 multicast.
                            - other reserved multicast addresses for non-IP protocols.
                            - Flooded unless switch configured for multicast snooping.

### 3. Switch Speeds and Forwarding Methods
    
    a. Frame Forwarding Methods on Cisco Switches
       Store and Forwarding Switching - Receives entire frame, checks CRC, then forwards if valid.
                            - Supports QoS analysis for traffic prioritization. (e.g, VoIP)
       Cut-through switching - Forwards before receiving entire frame, only checks destination MAC
                            - Fast-forward switching - Immediate forwarding after destination address, no error checking.
                            - Fragment-free switching - checks first 64 bytes for collision fragments before forwarding.
    b. Memory Buffering on Switches:
       Port-Based Memory Buffering - frams queued per port, transmitted in order, can cause dialysis.
       Shared Memory Buffering - All frames in common buffer, dynamically allocated per port, reduces dropped frames.
    c. Duplex and Speed Settings: 
       Full Duplex - allows simultaneously send/receive.
       Half Duplex - Only one direction at a time.
       Autonegetaion for speed nad duplex compatibility.
       Gigabit Ethernet ports operate full-duplex only.
       Duplex Mismatch - Occures when link partners operate at different duplex settings, common performance issue.
    d. Auto-MDIX - Automatically detecs and configures for straight-through or crossover cables.
                 - Enabled by default in Cisco IOS Release 12.2(18)SE or later, can be disabled and re-enabled. 
       
      
                            
        
