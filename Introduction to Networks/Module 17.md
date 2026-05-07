# BUILD A SMALL NETWORK

### 1. Devices in a Small Network
    a. Small Network Topologies
       - Majority of business networks are small.
       - Simple Design with a single WAN connection (DSL, Cable, or Ethernet)
       - Mananged by local IT technicians or contracted professionals.
    b. Device Selection
       Considerations for selecting devices:
       Cost
       Speed and types of ports/interfaces
       Expandability
       Operating system features and services
    c. . IP addressing:
       - Create a unique IP addressing scheme for:
         * End-user devices (wired, wireless, remote access)
         * Servers and peripherals (e.g., printers, security cameras)
         * Intermediar devices (swithces, access points)
        - Document and maintain the scheme to simplify troubleshooting.
     d. Redundnacy
        - Ensures network reliability by eliminating single points of failure.
        Methods:
        Duplicate equipment
        Redundant network links in critical areas
      e. Traffic Management
        - Optimize productivity and minimize downtime
        - Configure routers and switches to support real-time (voice, video)
        - Implement Quality of Service and priority queuing.
  ### 2. Small Network Applications and Protocols
      a. Common Applications:
         Network Applications: Implement application layer protocols and communicatie with lower layers.
         Application Layer Services: Interface with the network for non-network-aware applications.
      b. Common Protocols:
         Remote Access: Telnet, SSH
         Web: HTTP, HTTPS
         Email: SMTP, POP3, IMAP
         File Transfer: FTP, SFTP
         IP configuration: DHCP
         Name resolution: DNS
      c. Voice and Video Applications:
         IP Telephony and straming media for communication and remote network
         Considerations for real-time- traffic:
         Infrastructure capacity
         VoIP vs IP Telephony
         Use of Quality of Service (QoS) and real-time protocols like RTP and RTCP.
  ### 3. Scale to Larger Networks
      a. Small Network Growth
         Elements for scaling:
         Network Documentation (Physical and Logical Topology)
         Device inventory.
         Budget Planning
         Traffic Analysis
      b. Protocol Analysis: Capture and evaluate traffic during peak usage
                            Analyze protocol, source/destination, and type of traffic.
      c. Employee Network Utilization:
         Capture snapshots of:
         OS Version
         CPU/RAM/drive utilization
         Applications (network and non-network)
      d. Verify Connectivity:
         Ping Command: Test Layer 3 connectivity using ICMP echo requests and replies.
         Extended Ping: Cisco IOS allows parameter adjustments in ping tests.
         Traceroute Command: Identifies Layer 3 connectivity problems and path hops.
         Network Baseline: Establish a baseline using tools like ping and traceroute. Store and archive results for comparison overtime.
  ### 4. Troubleshooting Methodoligies
      a. Steps to Troubleshoot
         1. Identify the problem
         2. Establish a theory of probable causes.
         3. Test the Theory
         4. Plan and Implement a Solution
         5. Verify fuctionality and implement preventive
         6. Document findings and outcomes
      b. Resolve or Escalate: Escalate when the problem requires specific expertise or higher access.
      c. Debug Command: Realtime analysis of processes, protocol, and events. use with caution due to resource intensity.
      d. Terminal Monitor Command: Enables logging messages on virtual consoles.
  ### 5. Troubleshooting Scenarios
      a. Duplex Mismatch
         - Occurs when connected devices operate in different duplex modes.
         - Causes lateny and inefficiency
      b. IP addressing Issues
         - Manual Assignment errors or DHCP issues on routers and end devices
         - Use commands like ipconfig or show ip interface
      c. Default Gateway Issues: Misconfigured or missiing default gateways prevent remote communication.
      d. DNS Issues
         - Verify DNS Server settings with ipconfig /all or nslookup.
         - Use secure DNS services like OpenDNS
         
        
         
