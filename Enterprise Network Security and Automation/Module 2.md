# Single-Area OSPFv2 Configuration

### 1. OSPF Router ID
    a. OSPF Reference Topology
       - Topology includes router R1, R2, R3 within OSPF backbone area.
       - ISP router acts as the gateway to the Internet.
    b. Router Configuration Mode for OSPF
       - OSPFv2 enabled using "router ospf <process-id>"
       Example configuration:
       R1(config)# router ospf 10
       R1(config-router)#
    c. Router IDs
        - Definition: A 32-bit value used to uniquely identify an OSPF router.
        Functions:
        - Synchronizes OSPF databases during Exchange State.
        - Participantes in DR/DBR elections in multiaccess LANs
        Order of Precedence:
        Example:
        R1(config)# router ospf 10
        R1(config-router)# router-id 1.1.1.1        
    d. Modify Router ID
       Change requires either router reload or clearing the OSPF process:
       R1# clear ip ospf process
### 2. Point-to-Point OSPF Networks
    a. Network Command Syntax
       - Enable OSPF on specific interfaces:
       Router(config-router)# network <network-address> <wildcard-mask> area <area-id>
       Wildcard mask is typically the inverse of the subnet mask.
    b. Configuring OSPF
       Use the network command to specify interfaces:
       R1(config-router)# network 10.10.1.0 0.0.0.255 area 0
       Alternatively, configure OSPF directly on interfaces:
       R1(config-if)# ip ospf 10 area 0
    c. Passive Interfaces
       Suppress routing updates on interfaces with passive-interface:
       Router(config-router)# passive-interface <interface>
       Verify using "show ip protocols"
    d. DR/BDR Election in Point-to-Point Networks
       - Default DR/BDR election process applies to Ethernet interfaces.
       Disable DR/BDR election using ip ospf network point-to-point:
       R1(config-if)# ip ospf network point-to-point
    e. Loopbacks and Point-to-Point Networks
       - Advertise loopback interfaces as point-to-point networks:
       R1(config-if)# ip ospf network point-to-point
### 3. Multiaccess OSPF Networks
    a. DR/BDR Election
         Roles:
         DR: Collects/distributes LSAs.
         BDR: Backup for DR.
         Election Criteria:
         1. Highest priority (0-255. default 1)
         2. Highest router ID if priorities area equal.
    b. Configuring OSPF Priority
       Set priority to influence DR/BDR election:
       R1(config-if)# ip ospf priority 255
       Clear OSPF process to force re-election:
       R1# clear ip ospf process
    b. Configuring OSPF Priority
### 4. Modify Sigle-Area OSPFv2
    a. Cisco OSPF Cost Metric
       Cost = Reference Bandwidth/Interface Bandwidth.
       Adjust reference bandwidth for high-speed links:
       Router(config-router)# auto-cost reference-bandwidth <Mbps>
    b. Manual Cost Configuration
       Override default cost on interfaces:
       R1(config-if)# ip ospf cost <value>  
### 5. Default Route Propagation
    a. Configure Default Route:
       Advertise a default route in OSPF:
       R1(config-router)# default-information originate
### 6. Verifying OSPF
       Commands:
       show ip protocols - Verify OSPF settings.
       show ip ospf neighbor - Display OSPF neighbors.
       show ip route - View routing table.
