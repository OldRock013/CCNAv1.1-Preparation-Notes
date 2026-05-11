# Troubleshoot Static and Default Routes

### 1. Packet Processing with Static Routes
    a. Static Routes and Packet Forwarding
       Static Route: Router forwards the packet using the next hop or exit interface.
       Default static route: Router forwards the packet if no specific route matches.
       No route: Router drops the packet and sends an ICMP error.
    b. Steps in Forwarding
       1. De-encapsulate the packet.
       2. Match a route in the routing table.
       3. Foward the packet to the next hop or out of the identified interface.
### 2. Troubleshoot IPv4 Static and Default Route Configuration
    a. Common Causes of Network Failures
       - Interface Failure
       - Service provider connection issues
       - Misconfigurations by administrators.
    b. Troubleshooting Commands:
       ping: Verify Layer 3 connectivity.
       traceroute: Trace the path to the destination.
       show ip route: View routing table entries.
       show ip interface brief: Check interface status.
       show cdp neighbors: Validate Layer 1/2 connectivity.
