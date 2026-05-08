# SPANNING TREE PROTOCOL (STP) Concepts

### 1. Purpose of STP
    a. Redundancy in Layer 2 Networks
       - Eliminates single points of failure.
       - Prevents disruption of network services.
       - Redundant paths can cause Layer 2 loops.
    b. Spanning Tree Protocol (STP)
       - Prevents loops while allowing redundancy.
       - Blocks physical loops logically.
       - Recalculates paths during failures.
    c. Issues with Redundant Switch Links
       - Causes MAC address table instability
       - Leads to link saturation and high CPU utilization.
       - Results in broadcast storms and network failure.
    d. Layer 2 Loops
       - Frame loop endlessly without STP.
       - Causes MAC database instability and high CPU ussage.
    e. Broadcast Storm
       - Overwhelms the network with excessive broadcasts.
       - can disable the network within seconds.
    f. Spanning Tree Algorithm (STA)
       - Selects a root bridge
       - Blocks redundant paths to create a loop free topology
### 2. STP Operation
    a. Steps to a Loop-Free Topology
       - Elect the root bridge
       - Elect the root ports
       - Elect designated ports
       - Elect alternate (blocked) ports.
    b. Bridge Protocol Data Units (BPDUs)
       - Used to share information and elect roles.
       - Contains Bridge ID (BID) for decision-making.
    c. Root Bridge Election
       - Switch with the Lowest BID becomes the root bridge
       - BID - Priority + MAC address + Extended System ID.
    d. Root Path Cost
       - Determined by the sum of port costs along the path
       - Default port costs depend on link speed
    e. Port Roles
       - Root Port: Closest to the root bridge 
       - Designated Port: Best Path to the root bridge
       - Alternate (Blocked) Port: Prevents loops
    f. STP Timers
       - Hello Timer: Interval between BPDUs (default: 2 seconds)
       - Forward Delay Timer: Time in Listening/Learning states (default: 15 seconds)
       - Max Age Timer: Time before topology change (default: 20 seconds)
    g. Port States
       - Blocking: Receives BPDUs only.
       - Listening: Receives and sends BPDUs.
       - Learning: Updates MAC table.
       - Forwarding: Forwards data frames.
       - Disabled: Non-operational.
### 3. Evolution of STP
    a. Different VErsions of STP
       - STP (802.1D): Original version, single spanning tree for all VLANs.
       - PVST+: Cisco enhancement, separate spanning tree per VLAN.
       - RSTP (802.1w): Faster convergence than STP.
       - Rapid PVST+: Cisco enhancement of RSTP, per-VLAN instance.
       - MSTP: Maps multiple VLANs into a single spanning tree instance.
    b. RSTP Concepts
       - Backward compatible with STP
       - Faster convergence (milliseconds)
       - Alternate and backup ports for redundancy
    c. PortFast and BPDU Guard
       - PortFast: Immediate transition to forwarding state.
       - BPDU Guard: Disables port upon receiving BPDUs
    d. Alternative to STP
       - Layer 3 routing for redundancy without blocking ports.
       - Transition to Layer 3 in distribution and core layers.
### Summary

Redundant paths can cause Layer 2 loops.

STP prevents loops and ensures redundancy.

STA builds a loop-free topology in four steps.

BPDUs are used for role election and topology updates.

RSTP provides faster convergence than STP.

Cisco enhancements include PVST+, Rapid PVST+, and BPDU Guard.

Layer 3 routing is an alternative to STP for redundancy.
