# NAT for IPv4

### 1. NAT Characteristics
    a. IPv4 Address Space
       - Private IPv4 addresses as per RFC 1918
       - Class A: 10.0.0.0/8
       - Class B: 172.16.0.0/12
       - Class C: 192.168.0.0/16
       - Private IPv4 addresses cannot be routed over the internet.
       - NAT enables translation of private addresses to public addresses for internet access.
    b. What is NAT
       - Primary function: Conserve public IPv4 addresses.
       - Allows internal devices to communicate with external networks by translating private IPs
       - NAT operates on the edge/border router.
    c. How NAT works
       1. Device sends a packet to a destination. (e.g web server)
       2. Border router intercepts the packet examines the source IP.
       3. Router performs a translation (maps local to global address) and logs the mapping in its NAT table.
       4. Destination responds, and the router translates the global address back to the local address for delivery
    d. NAT Terminology
       Inside Local Address: Private IP address assigned to the source device (e.g 192.168.10.10)
       Inside Global Address: Public IP address assigned to represent the internal device externally (e.g., 209.165.200.256)
       Outside Global Address: Public IP of the destination device (e.g. webserver: 209.165.201.1)
       Outside Local Address: IP of the destination as seen internally (usually the same as the global address)
### 2. Types of NAT
    a. Static NAT
       - One-to-one mapping between an internal private IP and public IP
       - Use cases: Web servers accessible externally. Devices requiring consistent external access (e.g., CCTC cameras)
       Limitation: Requires sufficient public IPs for mapping.
    b. Dynamic NAT
       - Utilizes a pool of public IP addresses
       - Dynamically assigns a public IP to internal devices on a first-come, first-served basis.
       - If all public IPs are in use, additional requests are queued or denied.
    c. Port Address Translation (PAT)
       - Maps multiple provate IPs to a single public IP using TC/UDP port numbers for differentiation.
       - PAT process:
         1. A unique port is appended to each translation (e.g., 209.165.200.226:1444)
         2. If a port is unavailable, a new public IP is used (e.g. available)       
### 3. NAT Advantages and Disadvantages
    a. Advantages
       - Conserves public IP addresses.
       - Simplifies network renumbering during ISP changes.
       - Provides security by hiding internal IPs from external networks.
       - Enables multiple devices to share a single public IP.
    b. Disadvantages
       - Increases latency due to translation overhead.
       - breaks end-to-end communication and address traceability.
       - Impacts certain applications, e.g IPsec tunnels, VoIP.
       - Complex configuration for protocols relying on embedded IP addresses.
### 4. Configuration Examples
    a. Static NAT
       Command: ipnat inside source static <inside-local> <inside-global>
       Interfaces:
       Inside: ip nat inside
       Outside: ipnat outside
       Example:
       ip nat inside source static 192.168.10.10 209.165.201.5
    b. Define the address pool:
       ip nat pool NAT-POOL1 209.165.200.226 209.165.200.240 netmask 255.255.255.224
       Bind the pool to ACL:
       access-list 1 permit 192.168.0.0 0.0.255.255
       ip nat inside source list 1 pool NAT-POOL1
    c. Enable overloading
       ip nat inside source list 1 interface serial 0/1/1 overload
### 5. NAT64
       - Enables IPv6 only devices to communicate with IPv4 only devices.
       - Use case: IPv4 to IPv6 migration strategy.
       - Converts IPv6 addresses into IPv4 mapped equivalents.
