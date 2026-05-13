# Network Design

### 1. Hierarchical Networks
    a. Three-Tier Model
       Layers:
         Access: End-user connectivity
         Distribution: Routing, security, QoS aggregation.
         Core: High-speed backbone
    b. Two-Tier Model
       Layers:
         Collapsed core combines core and distribution layers.
         Used in smaller networks or single-building campuses.
    c. Converged Networks
       Support data, voice, and video.
       Features: Scalable and Flexible.
               : Includes wireless and IP telephony.
### 2. Scalable Networks
    a. Design Principles: Redundancy: Avoid single points of failure with failover serces and duplicate paths.
      Reduces failure domains: Use smaller Layer 2 broadcast domains.
                             : Deploy switch blocksfor isolation   
    b. Bandwidth: Link aggregation (e.g, EtherCahnnel) for combining multiple links into one logical connection.
                 Benefits: Load balancing | simplifies configuration. 
    c. Routing Protocols: Use scalable protocols like OSPF with hierarchical design (areas)
### 3. Switch Hardware
    a. Platforms
       Fixed: Limited feature set, single box.
       Modular: Expandable chassis with replaceable line cards.
       Stackable: Switches operate as one logical unit.
    b. Features
       Port Density: Number of ports per switch (12, 24, 48, or more).
       Power over Ethernet (PoE):
         Provides power to devices like IP phones and cameras.
         Cost considerations for PoE-enabled switches.
    c. Performance
        Forwarding rates determine throughput.
        Multilayer switching supports routing and packet forwarding close to Layer 2 speeds.
### 4. Router Hardware
    a. Functions
       Route IP packets.
       Contain broadcast traffic.
       Provide logical segmentation and security via ACLs.
    b. Router Types
       Branch: Small office use.
       Edge: Connecting LANs to WANs.
       Service Provider: Scaling for high traffic.
       Industrial: Rugged environments.
    c. Form Factors
       Compact: Cisco 900 series for SMBs.
       Aggregation: ASR 9000 for large networks.
       Converged: NCS 5500 for service providers.
