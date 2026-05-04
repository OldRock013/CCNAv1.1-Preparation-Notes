# ICMP

### 1. ICMP Messages
  
  a. ICMPv4 and ICMPv6 Messages
       
    - Purpose: provide feedback about issues related to IP packet processing.
    - Common messages: Host Reachability, Destination or service unavailable, Time Exceeded
  b. Host Reachability 0 used to test if a host is reachable

  c. Destination or service unreachable - notifies the source that a destination or service is unreachable.

  d. Time Exceeded - Indicates thet the Time to Live (TTL) field of a packer has expired.

  e. ICMPv6 Messages:

      Part of Neighbor Discovery
      Router Solicitation (RS)
      Router Advertisement (RA)
      Neighbor Solicitation (NS)
      Neighbor Advertisement
      Dynamic Address Allocation: 
      RA messages sent every 200 seconds to provide addressing information.
      SLAAC enabled hosts use the link-local address of the router as the default gateway
  f. Duplicate Address Detection

      Purpose: Ensures the uniqueness of ah IPv6 address
      Process: 
      Device sends NS message to check if an address is in use
      If the address is taken, another deivce responds with an NA message.
  g. MAC address Resolution

    Process:
    Device sends an NS message to the solicited node multicast address
    Target device responds with an NA message containing its MAC address

### 2. Ping and Traceroute Tests

    a. Ping-Test Connectivity
       Funtionality
       Uses ICMP Echo Request and Reply nessages.
       Test connectivity between hosts
       Provide statistics (success rate, round-triptime)
    b. Timeouts: First ping may timeout due to ARP or ND resolution.
    c. Traceroute-Test the path
       Functionality:
       Determines the path betwen two hosts,
       Provides a list of successfully reached hops.
       Indicates round-trip time for each hops
       Process:
       Initial message sent with TTL=1
       TTL incremented progressively to trace the path.
       
      
      
