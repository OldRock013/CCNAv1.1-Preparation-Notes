# Network Troubleshooting

### 1. Network Documentation
    a. Overview: Essential for monitoring and troubleshooting networks.
       Includes:
       Physical and logical topology diagrams.
       Device-specific documentation.
       Baseline performance data
    b. Types of Network diagrams
       - Physical Topology: Maps physical connections.
       - Logical Topology: Mpas data flow and IP addressing.
    c. Network Device Documentation
       - Contains hardware/software details for routers, switches, and end devices.
       - Includes configurations, firmware, and serial numbers.
    d. Establishing a Baseline
       Steps:
       1. Determine data types to collext (e.g. CPU/interface utulization)
       2. Identify key devices and ports.
       3. Set a baseline duration (typically 2-4weeks)
### 2. Troubleshooting Process
    a. Seven-Step Troubleshooting Process
       1. Define the Problem: COnfirm and describe the issue.
       2. Gather Information: Use Tools and user input to identify symptoms.
       3. Analyze information: Narrow down possible causes.
       4. Eliminate Cause: Progressively rule out potential cause.
       5. Propose Hypothesis: Formulate a probable cause.
       6. Test Hypothesis: Apply fixes ad validate results.
       7. Solve the Problem: Document and communicate the resolution.
    b. Questioning Users: Identify symptoms, scope, timing and chages.
       Sample Questions:
       What doesn't work?
       When was the issue noticed?
       Has anything changed recently?
    c. Layered Models in Torubleshooting: OSI and TCP/IP models help isolate issues.
       Example:
       Physical layer: Cabling, power.
       Data link layer: Encapsulation, switches.
       Network layer: Routing tables, IP.
### 3. Troubleshooting Tools
    a. Software Tools:
       Network Management Systems (NMS): Device monitoring and configuration. 
       Protocol Analyzers (e.g., Wireshark): Packet-level troubleshooting.
       Syslog Servers: Log aggregation and analysis.
    b. Hardware Tools
      Digital Multimeters: Voltage/current measurements.
      Cable Testers/Analyzers: Test data communication cables.
      Portable Network Analyzers: VLAN and switch troubleshooting.
### 4. Symptoms and Causes of Network Problems
    a. Physical Layer Issues
       - Symptoms: Connectivity loss, bottlenecks, high CPU usage.
       - Causes: Power issues, cabling faults, attenuation, EMI
    b. Data Link Layer Issues
       - Symptoms: No connectivity, excessive broadcasts, framing errors.
       - Causes: Encapsulation errors, STP loops, address mapping errors
    c. Network Layer Issues
       - Symptoms: Network failures, suboptimal performance.
       - Causes: Routing table errors, neighbor adjacency issues.
    d. Transport Layer Issues
       - Misconfigured ACLs or NAT for IPv4.
       - Common errors: Blocking or misrouting packets.
    e. Application Layer Issues: Protocol-specific problems: SSH, DNS, HTTP, FTP
### 5. Troubleshooting IP Connectivity
       Step-by-Step Approach
       1. Verify physical connectivity.
       2. Check duplex mismatches.
       3. Validate IP configurations.
       4. Verify default gateways.
       5. Check routing paths.
       6. Verify transport layer protocols.
       7. Inspect ACLs.
       8. Validate DNS settings.
