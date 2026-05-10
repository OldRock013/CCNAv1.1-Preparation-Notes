# SLAAC and DHCPv6

### 1. IPv6 GLobal Unicast Address Assignment
    a. IPv6 Host Configuration
        - Configure an IPv6 GUA using IPv6 GUA using "ipv6 address ipv6-address/prefix-length" command.
        - Windows hosts can dynamically acquire IPv6 GUA or be manually configured.
        - Manual configuration can be error-prone; automatic methods are preferred.
    b. IPv6 Host Link-Local Address
        - Host use ICMPv6 Router Advertisement (RA) messages for automatic configuration.
        - Link-local addresses are created automatically when the Ethernet interface is active.
        - No IPv6 GUA is created no router provides configuration instructions.
        - The Zone ID (e.g. % and a number) associstes the link-local address with specific interface.
    c. Three RA Message Flags
        A flag: Use StateLess Address Autoconfiguration (SLAAC) to create IPv6 GUA.
        O flag: Additional configuration available from stateless DHCPv6 server
        M flag: Use a stateful DHCPv6 server to obtain IPv6 GUA.
### 2. SLAAC
    a. Enabling SLAAC
        - Routers send RA messages containing configuration information.
        RA includes:
        Link-local IPv6 address
        IPv6 GUA prefix and subnet mask
        Multicast group addresses
        Example: R1 joins multicast group and sends RA messages.
    b. SLAAC Only Method
        RA Messages:
        - A = 1 Create GUA using prefix in RA and generate Interface ID.
        - O = 0 and M = 0: Use RA exclusively for configuration information.
        Example: PC1 creates IPv6 GUA using RA and sets the default gateway to the router's LLA
      
    c. Host Process to Generate Interface ID
        - Ramdon generation (Default for Privacy)
        - EUI-64 method: Converts 48-bit MAC address and inserts FFFE
        - Some OSes prefer random IDs to protect privacy.
    d. Duplicate Address Detection (DAD)
        Ensures uniqueness od IPv6 GUA:
        - Host sends ICMPv6 Neighbot Solicitation (NS) to multicast address.
        - If no Neighbor Advertisement (NA) is received, the address is unique.
        DAD reduces chances of duplicate addresses but still recommended by IETF.
### 3. DHCPv6
    a. Operation Steps - Stateful DHCPv6 does not require SLAAC, while stateless does.
       1. Host sends RS message
       2. Router sends RA message
       3. Host sends DHCPv6 SOLICIT message.
       4. DHCPv6 server responds with ADVERTISE message.
       5. Host sends REQUEST message.
       6. Server sends REPLY message.
    b. Stateless DHCPv6 - Provide additional configuration parameters (e.g. DNS) without maintaining address bindings.
       Example:
       RA: A = 1, O = 1, M = 0
       Host creates GUA using SLAAC and sends SOLICIT to DHCPv6 serverfor additional details.
    c. Stateful DHCPv6 - DHCPv6 server maintains address bindings and provides full configuration details.
       Example:
       RA: A = :0, O = 0, M = 1.
       host contacts DHCPv6 server for all addressing and configuration.
### 4. Configure DHCPv6 Server
    a. DHCPv6 Router Roles: A Cisco ISO router can act as:
        DHCPv6 Server (Stateless or stateful)
        DHCPv6 Client
        DHCPv6 Relay Agent
    b. Configure a Stateless DHCPv6 Server
        1. Enable IPv6 routing: ipv6 unicast-routing
        2. Define DHCPv6 pool: ipv6 dhcp pool POOL-NAME
        3. Configure pool options (e.g. DNS server, domain name).
        4. Bind interface to the pool: ipv6 dhcp server POOL-NAME
        5. Set O flag: ipv6 nd other-config-flag.
    c. Configure a Statful DHCPv6 Server
        1. Enable IPv6 routing: ipv6 unicast-routing.
        2. Define DHCPv6 pool: ipv6 dhcp pool POOL-NAME.
        3. Configure pool options (e.g., address prefix, domain name).
        4. Bind interface to the pool: ipv6 dhcp server POOL-NAME.
        5. Set M flag: ipv6 nd managed-config-flag.
        6. Disable SLAAC: ipv6 nd prefix default no-autoconfig
    d. Configure DHCPv6 Relay Agent:
        Used when DHCPv6 server is on a different network.
        Configure relay destination: ipv6 dhcp relay destination ipv6-address
        
    
  
