# IP Static Routing

### 1. Static Routes
    a. Types of Static Routes:
       Standard Static Route - Connecting to a specific internal subnet or a partner's office network.
       Default Static Route - Directing all internet-bound traffic to an ISP
       Floating Static Route - Having a slow, secondary link take over if the high-speed primary fiber link goes down.
       Summary Static route - Representing ten different subnets (e.g., 192.168.1.0/24 through 192.168.10.0/24) with one summarized entry like 192.168.0.0/16.
    b. Next-Hop Options
       - Next-Hop route: Uses only the next-hop IP address.
       - Directly connected Static route: Uses the exit interface.
       - Fully pecified static route: Uses both next-hop IP and exit interface.
### 2. Configure Static Routes
    a. IPv4 Static Route Commmand:
       Command syntax: ip route network-address subnet-mask {ip-address | exit-intf [ip-address]} [distance]
    b. IPv6 Static Route Command:
       Command syntax: ipv6 route ipv6-prefix/prefix-length {ipv6-address | exit-intf [ipv6-address]} [distance]
    c. Verification Commands:
       show ip route static
       show ipv6 route static
       ping
       traceroute
### 3. Configure IP Default Static Routes
