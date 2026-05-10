# FHRP Concepts

### 1. First Hop Redundacy Protocols
    a. Default Gateways Limitations
       - End devices typically relty on a single default gateway
       - Loss of the default gateway interface disrupts LAN connectivity.
    b. Router Redundancy
        - Prevent a singlepoint of failure by implementing a virtual router.
        - Multiple routers share an IP and MAC address to act as a single virtual router.
        - Traffic sent to the virtual MAC address is forwarded by the active router.
    c. Steps for Router Failover
        1. Standby router stops receiving Hello messages from the active router.
        2. Standby router becomes the new active router.
        3. Host devices experience no service disruption due to virtual MAC adn IP addres.
    4. FHRP Options
        HSRP: Cisco-proprietary protocol for IPv4 and IPv6.
        VRRPv2: Non-proprietary protocol for IPv4.
        VRRPv3: Scalable option for both IPv4 and IPv6
        GLBP: Cisco-proprietary protocol supporting load balancing and redundancy.
        IRDP: Legacy Solution defined in RFC 1256.
### 2. HSRP
    a. Overview:
       - Cisco-proprietary protocol for redundancy in IPv4 and IPv6
       - Selects an active router and Standby router for seamless failover.
    b. Priority and Preemption
       - Highest priority determines the active router (default: 100)
       - Preemption must be enabled to allow higher-priority routers to take over.
    c. States and Times:
       - States: Initial, Listen, Speak, Standby and Active.
       - Hello timer: 3 seconds (default)
       - Hold timer: 10 seconds (default)
       
        
        
        
