# WAN Concepts

### 1. Purpose of WANs
    a. LANs vs. WANs
       LAN: Small geographic area, high bandwidth, managed internally.
       WAN: Large geographic area, external ISP infrastructure, variable bandwidth
    b. Private vs. Public WANs
       - Private: Dedicated to a signle organization. Security guaranteed badnwidth, reliability.
       - Public: Shared infrastructure (e.g., internet). Lower cost but varying bandwidth and less secure.
    c. WAN Topologies 
       Point-to-Point
         - Direct connection between two sites.
         - Transparent Layer 2 communication.
         - Expensive for scaling.
       Hub-and-Spoke
         - Central hub connects multiple sites (spokes).
         - Limitations: Single point of failure at the hub.
       Dual-homed
         - Redundancy with multiple connections.
         - Requires additional hardware and complex configurations.
       Fully Meshed
         - All sites connected directly to each other.
         - High fault tolerance but costly.
       Partially Meshed 
         - Selective connections between sites to balance cost and redundancy.
### 2. WAN Operations
    a. Standards: Defined by: TIA/EIA, ISO, IEEE
    b. OSI Layer Model:
       Layer 1 (Physical): SDH, SONET, DWDM.
       Layer 2 (Data Link): MPLS, Ethernet WAN, PPP. 
    c. Key Terminology: DTE, DCE, CPE, POP, Local Loop, Demarcation Point.
    d. WAN Devices: DSL/Cable Modems, CSU/DSU, Optical Converters, Wireless Routers.
    e. Communication Types: Circuit-switched (e.g., PSTN, ISDN). Packet-switched (e.g., MPLS, Frame Relay).
### 3. Modern WAN Connectivity
    a. Ethernet WAN: Metro Ehternet, EoMPLS, VPLS. Replacing legacy connections.
    b. MPLS: High Performance routing. Features: PoS, Redundancy, VPNs
    c. Internet-Based: Wired: DSL, Cable, optical fiber. Wireless: Cellular (3G/4G/5G), Satellite, Wi-Fi.
### 4. VPN Connectivity
    a. Site-to-Site VPNs: Transparent encryption for users.
       Remote Access VPNs: User-initiated secure connections.
    b. advantages: Cost Savings, scalability, compatibility with broadband technologies.
### 5. ISP Connectivity Options
    a. Single-homed: One link to ISP; no redundancy.
    b. Dual-homed: Two links to the same ISP; redundancy with shared risk
    c. Multihomed: Connections to two different ISPs for resilince
    d. Dual-Multihomed: Redundant connections to multiple ISPs; Highest reliability.
