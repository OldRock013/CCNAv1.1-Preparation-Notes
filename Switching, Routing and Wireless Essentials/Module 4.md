# Inter-VLAN Routing 

### 1. Inter-VLAN Routing Operation
    Definition: Forwardong network traffic from one VLAN to another VLAN.
    Options:
    a. Legacy Inter-VLAN Routing
       - Uses a router with multiple Ethernet interfaces.
       - Not scalable due to limited physical interfaces.
    b. Router-on-a-Strick
       - Uses a single physical interface with subinterfaces.
       - Configured as 802.1Q trunk
       - Scales up to 50 VLANs
    c. Layer 3 Switch with SVIs
       - Uses switched virtual interfaces (SVIs)
       - Most scalable and efficient for medium to large organizations.
### 2. Router-on-a-stick Inter-VLAN Routing
    a. Advantages
       - Overcomes limitation of legacy routing.
       - Requires only one physical interface.
    b. Configuration
       - Configure subinterface for each VLAN.
       - Assign IP address and VLAN IDs to subinterfaces.
       - Enable trunking on the switch
    c. Veirfication
       - Use ping to test connectivity
       - Commands: show ip route, show ip interface brief, show interfaces.
### 3. Inter-VLAN Routing using Layer 3 Switches
    a. Advantages:
       - Faster than ROAS
       - No need for external links to a router.
       - Supports Etherchannels for increased bandwidth
       - Lower Latency
    b. Configuration:
       - Create VLANs
       - Configure SVI VLAN interfaces with IP addresses.
       - Assign access ports to VLANs
       - Enable IP routing
    c. Veirfication
       - Use ping to test connectivity
       - Commands: show ip route, show ip interface brief, show interfaces. 
### 4. Troubleshooting Inter-VLAN Routing
    a. Missing VLANs: Create VLANs or recreate and verify with "show vlan brief".
    b. Switch Trunk Port Issues: Ensure trunk ports are configured correctly and verify with "show interface trunk".
    c. Switch Access Port Issues: Assign correct VLAN to access ports and verify with "show interfaces switchport"
    d. Router Configuration Issues: Check subinterface configurations. and verify with "show ip interface brief"


### Key takeaways:

Inter-VLAN routing enables communication between VLANs.

Three methods: Legacy, Router-on-a-Stick, and Layer 3 Switch with SVIs.

Layer 3 switches are preferred for scalability and performance.

Proper configuration and troubleshooting are essential for successful implementation.
