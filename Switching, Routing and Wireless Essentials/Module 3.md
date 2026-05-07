# VLANs

### 1. Overview of VLANs
        - Logical Connections with similar devices
    a. Characteristics:
       1. Provides segmentation of devices
       2. Organizes or manageability
       3. Isolates broadcast, multicasts, and unicasts.
       4. Unique IP range for each VLAN.
       5. Smaller broadcast domains.
    b. Benefits:
       1. Smaller broadcast domains.
       2. Improved Security (communication limited to same VLAN)
       3. Improved IT efficiency (grouping similar devices)
       4. Reduced cost (one switch supports multiple VLANs)
       5. Better performmance (reduce traffic)
       6. Simpler management (similar groups need similar resources)
    c. Types of VLAN
       1. Default VLAN: VLAN1; Default, native, and management VLAN. It cannot be deleted or renamed.
       2. Data VLAN: Dedicated to user-generated traffic (e.g. email, web). VLAN 1 is the default data VLAN.
       3. Native VLAN: Used for trunk links only. Frames on native VLAN are untagged.
       4. Management VLAN: Used for SSH/ Telnet VTY traffic. Should not carry end-user traffic.
       5. Voice VLAN - Separate VLAN for voice traffic. Requires assured bandwidth, high QoS, and low delay.
### 2. VLANs in a Multi-Switched Environment
    a. VLAN Trunks: Point-to-Point link between network devices.
       Functions:
       1. Allows more than one VLAN
       2. Extends VLAN accross the network.
       3. Supports all VLANs by default.
       4. Uses 802.1Q trunking
    b. Networks Without VLANs: All devices receives all unicast, multicast, and broadcast traffic.
    c. Network with VLANs: Traffic confined to VLAN. Device in different VLANs cannot communicate with out a Layer 3 device.
    d. VLAN Identification
       802.1Q header (4 bytes)

<img width="1354" height="130" alt="image" src="https://github.com/user-attachments/assets/706d21f3-c195-4666-a19f-e1685c426218" />

<img width="742" height="262" alt="image" src="https://github.com/user-attachments/assets/86246cc4-5699-4eae-afb5-4a0cf1915d8b" />
     
     Fields:
     Type (Tag Protocol ID).
     User Priority (3-bit value).
     Canonical Format Identifier (1-bit value).
     VLAN ID (12-bit identifier, supports up to 4096 VLANs).
    e. Native VLANs and 802.1Q Tagging
       - Tagging done on all VLANs except native VLAN.
       - Both ends of a trunk link must have the same native VLAN
    f. Voice VLAN Tagging:
       - VoIP phones tag their ownt traffic
       - Voice VLAN tagged with Layer 2 CoS priority vlaue.
### 3. VLAN Configuration
    a. VLAN Ranges:
       Normal Range: VLAN 1 - 1005
       Extended Range: VLAN 1006 - 4095
       Reserved VLAN: 1002 - 1005
    b. VLAN Creation:
       Commands:
       vlan vlan-id (creates VLAN)
       name vlan-name (assign name)
    c. VLAN Port Assignment:
       Commands:
       switchport mode access (set port to access mode).
       switchport access vlan vlan-id (assign VLAN to port).
    d. Data and Voice VLANs: Access port can belong to one data VLAN and one voice VLAN.
    e. Verification
       Commands:
       show vlan (view VLAN details).
       show vlan brief (summary of VLANs).
    f. Deleting VLANs
       Commands:
       no vlan vlan-id (delete specific VLAN).
       delete vlan.dat (delete all VLANs)
### 4. VLAN Trunks
    a. Trunk Configuration:
       Commands:
       switchport mode trunk (set port to trunk mode).
       switchport trunk native vlan vlan-id (set native VLAN).
       switchport trunk allowed vlan vlan-list (allow specific VLANs).
    b. Trunk Verification: Commands: show interfaces switchport (view trunk settings).
    c. Resetting Trunks:
       Commands:
       no switchport mode trunk (reset trunk to default).
       switchport mode access (set trunk to access mode).
    d. Dynamic Trunking Protocol
       1. Introductions:
          Cisco proprietary protocol.
          On by default on Catalyst switches.
          Can be turned off with nonegotiate command.
       2. Interface modes:
          Access: Permanent access mode.
          Dynamic Auto: Becomes trunk if neighbor is trunk or desirable.
          Dynamic Desirable: Actively seeks to become a trunk.
          Trunk: Permanent trunk mode. 
       3. Verification: Command: show dtp interface (view DTP mode)
### Key learnings

VLANs are logical, not physical connections.

VLANs segment networks based on function, team, or application.

Trunks carry traffic for multiple VLANs.

802.1Q tagging includes type, user priority, CFI, and VID.

Separate voice VLAN is required for VoIP.

DTP manages trunk negotiations.       
