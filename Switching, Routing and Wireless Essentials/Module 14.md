# Routing Concepts

### 1. Path Determination
    a. Router Functions
       - Determine the best path using the routing table.
       - Forward packets to their destinations.
    b. Longest Match Rule
       - Route with the greatest number of matching bits in the prefix is chosen.
       Example: IPv4 and IPv6 logest match calculations.
    c. Types of Routes
       Directly Connected: Added when an interface is configured with an IP addess
       Static Routes: Manually configured by the administrator.
       Default Route: Used when no specific match exists in the routing table.
### 2. Packet Forwarding
    a. Decision Process
       1. Examine destination IP address
       2. Find the longest match in the routing table.
       3. Forward packet to next-hop or directly connected network.
       4. Drop packet if no match exists.
    b. Forwarding Mechanisms
       - Process Switching: Oldest, CPU-intensive method.
       - Fast Switching: Uses a cache for repeated flows.
       - Cisco Express Forwarding (CEF): Default and mose efficient method.
 ### 3. Baic Router Configuration
     a. Configuration Steps
       1. Set hostname, enable secret, and configure interfaces with IP addresses.
       2. Enable routing protocols (e.g., IPv6 unicast routing)
       3. Save configuration with "copy running-config startup-config"
     b. Verification Commands:
        show ip interface brief
        show running-config
        show ip route
 ### 4. IP Routing Table
     a. Route Sources
        Directly Connected: Indicated by "C" in the routing table.
        Static Routes: Indicated by "S"
        Dynamic Routes: Learned through protocols like OSPF (indicated by "O")
     b. Routing Table Structure
        - Contains route, source, destination network, next-hop, and metric.
        - IPv4 routing table retains classful structure for compatibility.
        - IPv6 routing table is straightforward with consistent formatting.
     c. Static and Dynamic Routing
        Static Routing:
        - Manually configured and suitable for small or secure networks.
        - Common use cases: Stub networks, default routes.
        Dynamic Routing:
        - Automatically adapts to network topology changes
        - Protocols include RIP, OSPF, and EIGRP.
        - Enables equal-cost load balancing for multiple paths.
        
