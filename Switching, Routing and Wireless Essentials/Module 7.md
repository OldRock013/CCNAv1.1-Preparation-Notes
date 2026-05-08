# DHCPv4

### 1. Concepts
    a. DHCP Overview
       - Assigns IPv4 addresses dynamically
       - Useful for network administrators in small to medium-sized networks
       - Can be implemented using a dedicated server or a Cisco router.
       - Leases IPv4 addreeses for a deficed period.
    b. DHCPv4 Operation
       - Works in client/server mode.
       - Clients lease IPv4 addresses until the lease expires
       - Leased addresses are retuned to the pool when no longer needed.
    c. Steps to Obtain a Lease
       1. DHCP Discover (DHCPDISCOVER)
       2. DHCP Offer (DHCPOFFER)
       3. DHCP Request (DHCPREQUEST)
       4. DHCP Acknowledgement (DHCPACK)
    d. Steps to Renew a Lease
       1. DHCP Request (DHCPRESQUEST)
       2. DHCP Acknowdledgedmemt (DHCPACK)
### 2. Configure a Cisco IOS DHCPv4 Server
    a. Steps tp configure
       1. Exclued IPv4 addresses
       2. Define DHCPv4 pool name
       3. Configure the DHCPv4 pool:
           Define address pool.
           Define default router or gateway.
           Define DNS server.
           Define domain name.
           Define lease duration.
           Define NetBIOS WINS server
    b. Verification Commands:
       show running-config | section dhcp
       show ip dhcp binding
       show ip dhcp server statistics
    c. Disable DHCPv4
       - Use no serveice dhcp to disable
       - Use service dhcp to re-enable
### 3. DHCPv4 Relay
       - Relays DHCPv4 messages to servers on different subnets/networks
       Configuration:
       - Use ip helper-address command to relay DHCPv4 broadcasts.
       - Verifies configuration with "show ip interface"
    e. Other Services relayed:
       Port 37: Time
       Port 49: TACACS
       Port 53: DNS
       Port 67: DHCP/BOOTP server
       Port 68: DHCP/BOOTP client
       Port 69: TFTP
       Port 137: NetBIOS name service
       Port 138: NetBIOS datagram service
### 4. Configure a DHCPv4 Client
    a. Cisco Router as a DHCPv4 Client
       - Configured using ip address dhcp command
       - Used in SOHO or branch sites.
    b. Home Router as a DHCPv4 Client
       - Typically pre-configured for automatic DHCP
       - Internet connection type set to "Automatic Configuration - DHCP"

### Summary

DHCPv4 dynamically assigns IPv4 addresses to clients.

Lease process ensures efficient use of IP addresses.

Cisco routers can act as DHCPv4 servers or clients.

DHCPv4 relay enables communication across subnets.

Verification commands ensure proper configuration and operation
