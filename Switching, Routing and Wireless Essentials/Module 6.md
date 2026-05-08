# EtherChannel

### 1. EtherChannel Operation
    a. Link Aggregation
        - Increases bandwidth and redundancy between devices.
        - Prevents switching loops by grouping Multiple physical Ethernet links into one logical link.
        - Provides fault-tolerance, load sharing, increased bandwidth, and redundancy.
    b. EtherChannel Technology
        - Developed by Cisco for LAN switch-to-switch communication.
        - Groups Fast Ethernet or Gigabit Ethernet ports into one logical channel.
        - Virtual Interface created is called a port channel.
    c. Advantages
        - Configuration consistency across links.
        - No need for expensive upgrades for higher bandwidth.
        - Load balancing across links.
        - Redundancy: Loss of one physical link does not affect the logical connection.
    d. Implementation Restrictions
        - Interfaces types cannot be mixed (e.g. Fast Ethernet and Gigabit Ethenet)
        - Up to 8 Ethernet ports per EtherChannel
        - Consistent configuration required on both devices.
        - All ports must be Layer 2 ports and configured as trunks or access ports.
    e. Auto-Negotiation Protocols
        - Port Aggregation Protocol (PAgP) - Cisco proprietary
        - Link Aggregation Control Protocol (LACP) - IEEE Standard
### 2. PAgP Operation
    a. Modes:
       On: Forces interfaces to channel without negotiation
       Desireable: Actively negotiates EtherChannel.
       Auto: Passively waits for negotiation
    b. Features:
        - Sends PAgP packets every 30 seconds.
        - Ensures configuration consistency.
        - Requires same speed, duplex and VLAN settings accross ports.
### 3. LACP Operation
    a. Modes:
       On: Forces interface to channel without negotiation.
       Active: Actively negotiates Etherchannel
       Passive: Passively waits for negotiation.
    b. Features:
        - IEEE standard for multivendor environments.
        - Ensures compatibility and configuration consistency.
### 4. Configure EtherChannel
     a. Configuration Guidelines
      - All interfaces must support EtherChannel.
      - Interfaces must operate at the same speed and duplex mode.
      - All interfaces must belong to the same VLAN or be configured as trunks.
      - Allowed VLAN range must match across all interfaces.
     b. Steps for LACP Configuration
       1. Specify interfaces using interface range command.
       2. Create port channel interface with channel-group command.
       3. Configure Layer 2 settings on the port channel interface
### 5. Verify and Troubleshoot EtherChannel
     a. Verification Commands:
       show interfaces port-channel
       show etherchannel summary
       show etherchannel port-channel
       show interfaces etherchannel
     b. Common Issues
       - Ports not in the same VLAN or not configured as trunks.
       - Different native VLANs on ports.
       - Inconsistent trunking configuration.
       - Mismatched dynamic negotiation options for PAgP or LACP
     c. Troubleshooting Steps:
       1. View EtherChannel summary information.
       2. Check port channel configuration.
       3. Correct misconfigurations (e.g., PAgP mode).
       4. Verify EtherChannel is operational

# Key Takeaways

EtherChannel increases bandwidth and redundancy without being blocked by STP.

Groups multiple physical Ethernet links into one logical link.

Supports PAgP (Cisco proprietary) and LACP (IEEE standard) for negotiation.

Requires consistent configuration across all interfaces in the EtherChannel.

Verification and troubleshooting are essential for successful implementation.
