# Network Automation

### 1. Automation Overview
    a. Definition and Benefits: Automation reduces human intervention by enabling systems to operate autonomously.
       Benefits:
       - Machines work 24/7, increasing output
       - Uniform product quality
       - Data collection and analysis to guide processes
       - Enhances safety in dangerous environments (e.g., mining, firefighting)
    b. Thingking Devices: Devices incorporate smart technology to adapt behavior based on external output.
       Examples: Smart appliances lower energy consumption during peak demand.
               : Self driving cars make real-time decisions.
       Smart devices rely on programming via network automation tools.
### 2. Data Formats
    a. Overview: Structured formats store and exchange data.
       Common formats:
       - JSON: Lightweight, human readable.
       - XML: Tag-based, self-descriptive.
       - YAML: Minimalist and readable, a super set of JSON.
    b. Comparison of Formats:
       JSON: Uses braces {} for objects and brackets [] for arrays
           : Keys are strings; values can be strings, number, arrays, or other objects.
       YAML: Use indentation instead of braces
           : Keys and values are separated by colon :
           : Lists are represented with hypen -
       XML : Encapsulates data with tags <tag>value</tag>
           : Allows nested structures but lacks predefined tags.
    c. JSON Syntax Rules
        - Keys in double quotes.
        - Key/value pairs separated by colons.
        - Arrays enclosed in brackets [ ] with items separated by commas.
        - Supports nesting.
### 3. APIs
    a. Definition: API: A set of rules enabling software applications to communicate
       API Request: Sent by the client to retrieve data or services.
       API Response: Sent by the server containing the requested data.
    b. Types of APIs
       Open APIs: Public and unrestricted, may require a key for usage tracking.
       Internal APIs: For internal organizational use only.
       Partner APIs: For licensed business partners
    c. Types of Web Service APIs
       SOAP: XML-based, robust but less flexible.
       REST: Most popular, supports multiple data formats like JSON and XML.
       XML-RPC: Simple, relies on XML.
       JSON-RPC: Similar to XML-RPC but uses JSON
    d. REST and RESTful APIs
       - Rest APIs work over HTTP/HTTPs.
       a. Principles:
          Stateless: No session data stored on the server.
          Cacheable: Clients can cache responses
          CRUD Operations: POST (Create), GET (Read), PUT/PATCH (Update), DELETE (Delete)
       b. Components of RESTful Requests:
          URI: Identifies the resource.
          Query: Specifies parameters (e.g., format, key, data)
### 4. Configuration Management Tools
    a. Traditional Network Configuration - Manual CLI entry for all configurations.
       Challenges: Time consuming for large networks
                 : Complex configurations prone to errors.
    b. Modern Configuration Tools
       Examples:
         Ansible: Agentless, uses YAML playbooks.
         Chef: Ruby-based, uses cookbooks for automation.
         Puppet: Uses manifests and supports both agent-based and agentless models.
         SaltStack: Python-based, supports agent and agentless setups.
       Benefits: 
         Automation of repetitive tasks.
         Scalable to thousands of devices.
         Orchestration ensures workflow coordination
    c. Key Functions
       Software version control.
       Device provisioning and configuration.
       Protocol and ACL automation.
### 5. Intent-Based Networking (IBN)
    a. Overview: Builds on SDN, focusing on automation and business-driven policies.
       Key Functions: 
       Translation: Converts business goals into network configurations.
       Activation: Deploys configurations using automation.
       Assurance: Validates that network behavior aligns with intent.
    b. Network Infrastructure as Fabric
       Fabric: Logical overlay for connecting devices virtually.
       Components:
       Overlay: Encapsulation protocols (e.g., IPsec) for logical connectivity.
       Underlay: Physical topology defining hardware connections.       
### 6. Cisco Digital Network Architecture (DNA)
    a. Integrates IBN principles into enterprise networks.
       Components:
       SD-Access    : Unified LAN and WLAN Traffic.
                    : Automates user and device segmentation
       SD-WAN       : Secure cloud-delivered WAN management
                    : Enhances user experience for cloud/on-premise applications
       DNA Assurance: Uses manchine learning for proactive problem detection.
                    : Provides root-cause analysis and recommendation.
       DNA Security : Real-time threat analysis
                    : Enforces granular access control
