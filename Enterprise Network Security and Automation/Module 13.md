# Network Virtualization

### 1. Cloud Computing
    a. Cloud Overview
       Benefits: Access data anytime, anywhere
               : Reduce IT costs (hardware, energy, maintenance)
               : Scalable to data volume increases
    b. Service Models
       SaaS: Access to software over the internet.
       PaaS: Development tools and environments.
       IaaS: Virtualized infrastructure for IT managers.
    c. Deployment Models: ublic, Private, Hybrid, and Community clouds.
    d. Cloud vs. Data Center
       Data Center: Physical storage and processing facility.
       Cloud: On-demand shared computing resources.
### 2. Virtualization
    a. Concept: Separate OS from hardware to improve resource utilization.
              : Foundation of cloud computing
    b. Server Virtualization: Allows multiple OS instances on one hardware platform.
       HyperVisor: Manages VMs and hardware abstraction.
       Redundancy: Prevents single points of failure.
    c. Advantages:
       Reduce costs (energy, equipment, space)
       Faster provisioning and prototyping.
       Improved Disaster recovery
### 3. Virtual Network Infrastructure
    a. Hypervisort Types
       Type 1 (Bare Metal): Directly on hardware, enterprise-grade.
       Type 2 (Hosted): Runs on an existing OS.
    b. Complexity of Network Virtualization
       VMs create dynamic traffic flows (East-West vs. North-South).
       Solution:
       VLANs, subinterfaces, VRFs for segmentation.
       QoS and automated configurations for traffic management.
### 4. Software-Defined Networking (SDN)
    a. Core Principles: Separates control plane (routing decisions) from data plane (packet forwarding)
                      : Centralized SDN controller manages traffic policies.
    b. SDN Components
       OpenFlow: Protocol for device-controller communication,
       OpenStack: IaaS platform with orchestration capabilities.
       APIs:
       Northbound: Communication between controllers and applications.
       Southbound: Device-specific configuration.
    c. Architechtures:
       Traditional: Contol and data planes on the same device.
       SDN: Centralized control with distributed planes.
### 5. Controllers
    a.  SDN Controllers
       - Define and manage network flows and policies.
       - Populate flow, group, and meter tables for traffic management.
    b. Cisco ACI
       - Combines cloud and data center management
       - Key Components: 
         ANP: Enpoint groups and policies
         APIC: Centralized controller for policy translation.
         Nexus 9000 Switches: Application-aware switching.
       - Use a spine-leaf topology for scalability
