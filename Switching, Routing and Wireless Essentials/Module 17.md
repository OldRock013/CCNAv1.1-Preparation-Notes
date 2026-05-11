# RSTP (Supplemental v1.1)

### 1. RSTP Port Roles and Port States
    a. STP vs RSTP
       - RSTP (IEEE 802.1w) supersedes the original STP (802.1D) while maintaining backward compatibility.
    b. Differences between STP and RSTP:
       BPDUs Forwarding:
        - STP: Only the root bridge sends BPDUs, relayed by other switches.
        - RSTP: All switches send hello BPDUs every 2 seconds for keepalive.
    c. Port States:
        - STP: Disabled, Blocking, Listening, Learning, Forwarding
        - RSTP: Disabled, Discarding, Forwarding
    d. Port Roles:
        - STP: Root, Designated, Non-Designated (Blocking)
        - RSTP: Root Designated, Alternate (Discarding), Backup (Discarding)
    e. Convergence Time: 
        - STP: Up to 50 seconds
        - RSTP: A few seconds
     f. RSTP Port States
         Disabled: Port is administrativeliy disabled; no frame forwarding.
         Discarding: Prevents loops; listens to BPDUs without forwarding frames.
         Forwarding: Immediately forwards frame, learns MAC addreses, and monitors for topology changes.
     g. RSTP Ports Roles
         Root Port: Forwards traffic to the root bridge with the lowest path cost.
         Designated Port: Forwards traffic from a segment to the root bridge, determined by root path cost, determined by root path cost.
         Alternate Port: Backup path to the root bridge, in discarding state, ensures rapid convergence in link failure events.
         Backup Port: Backup to designated port; typically connected to hubs
     h. RSTP Link Types and Edge Ports
         Link types:
           - Point-to-Point (P2P) for full duplex
           - Shared for half duplex
         Edge Ports:
           - Immediate forwarding when enabled.
           - Loses edge status upon receiving BPDU.
### 2. Potential STP Problems and Solutions
      a. Rogue Switch: 
         Problem: Unauthorized switch may become root bridge due to lower Bridge ID
         Solution: BPDU Guard: Prevents unauthorized switches by disabling the port.
                   Root Guard: Enforces root bridge plaement by blocking superior BPDUs.
      b. Unnecessary BPDU Traffic:
         Problem: BPDUs propagate unncessarily on access ports, causing delays and processing overhead.
         Solution: BPDU Filter: Prevents BPDU forwarding on access ports.
      c. Unidirectional BPDU Traffic:
         Problem: Broken fiber-optic link causes unidirectional communication, risking network loops.
         Solution: Loop Guard: Detecs and mitigates Layer 2 loops by blocking affected ports.
### 3. STP Enhancements Mechanisms
      a. PortFast: Enable access ports to transition directly to forwarding states.
      b. BPDU Guard: Disable ports that receive BPDUs to prevent loops.
         BPDU Guard Configuration:
         S3(config)# interface Fa0/23
         S3(config-if)# switchport mode access
         S3(config-if)# spanning-tree portfast
         S3(config-if)# spanning-tree bpduguard enable
      c. BPDU Filter: Prevents BPDU forwarding and reception on specific ports.
         Note: Do not configure BPDU Guard and BPDU Filter on the same port.
         BPDU Filter Configuration:
         S4(config)# interface Fa0/23
         S4(config-if)# switchport mode trunk
         S4(config-if)# spanning-tree bpdufilter enable
         S4(config-if)# no shut
         S4(config)# end
      d. Root Guard: Enforces root bridge placement by blocking superior BPDUs
          Root Guard Configuration:
          S1(config)# int range F0/1 - 3
          S1(config-if-range)# spanning-tree guard root
          S1(config)# do show spanning-tree root
      e. Loop Guard: Detect and mitigates loops caused by unidirectional link failures by placing ports in loop-inconsistent state.
         Loop Guard Configuration:
         S4(config)# interface Fa0/23
         S4(config-if)# switchport mode trunk
         S4(config-if)# spanning-tree guard loop
         S4(config-if)# exit
         S4# show spanning-tree vlan 1 interface fa0/23 detail
      f. UDLD (Unidirectional Link Detection): Detects and prevents unidirctional link issues.
      g. Bridge Assurance: Ensures STP topology health by exchanging BPDUs between designated ports.
# Summary

### RSTP Port Roles and Port States:

RSTP and Rapid PVST+ provide enhanced network reliability with faster convergence compared to traditional STP.

Ensure loop-free topologies by quickly transitioning ports to forwarding states.

Simplified port states (Disabled, Discarding, Forwarding) and new port roles (Root, Designated, Alternate, Backup) optimize data traffic and topology adjustments

### STP Enhancement Mechanisms:

Enhanced network stability, security, and efficiency through features like PortFast, BPDU Guard, BPDU Filter, Root Guard, Loop Guard, and UDLD.

These features prevent loops, unauthorized root bridge elections, and unidirectional link failures, thereby ensuring robust network performance

### Configuration and Monitoring

Essential commands help configure and verify RSTP and STP enhancements.

show spanning-tree command aids in monitoring correct RSTP port roles and network stability.
