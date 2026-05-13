# VPN and IPsec Concepts

### 1. VPN Technology
    a. What is a VPN?
       - Creates private connections access public networks.
       - Ensures confidentiality via encryption while data traverses public infrastructure.
    b. Benefits of VPNs
       - Cost Savings: Reduces connectivity costs by leveraging internet infrastructure.
       - Security: Uses encryption and authentication protocols to protect data.
       - Scalability: Allows organizations to add users without significant infrastructure changes
       - Compatibility: Works with variuos WAN link options like abroad.
    c. Types of VPNs
       Site-to-Site VPN: Used for secure communication between entire networks.
                         Encrypted between gateways; hosts unaware of the VPN.
       Remote-Access VPN: Dynamically created secure connections between individual clients and VPN devices.
       Modes:
       Clientless: Secured through web browser and SSL.
       Client-based: Requires software like Cisco AnyConnect
    d. Enterprise vs. Service Provider VPNs
       Enterprise VPNs: Managed internally. Uses technology like IPsec or SSL
       Service Provider VPNs: Use MPLS to segregate traffic for secure communication between sites.
### 2. Types of VPNs
    a. SSL VPNs: Uses Public Key (PKI) and digital certificates for authentication.
       Comparison with IPsec: IPsec supports all IP-based applications; SSL is limited to web-based apps.
                            : IPsec requires VPN clients; SSL works via browsers.
        
    b. GRE over IPsec: GRE encapsulates various traffic types, including multicasr and broadcast.
       Encapsulation Layers:
       Passenger Protocol: Original packet (e.g.,IPv4 or IPv6)
       Carrier Protocol: GRE
       Transport Protocol: IPsec
       Example Use: Securing OSPF
    c. Dynamic Multipoint VPNs (DMVPNs): Uses hub-and-spoke configuration for scalable VPNs
                                       : Supports dynamic GRE tunnels for spoke-to-spoke communication.
    d. IPsec Virtual Tunnel Interfaces (VTI): Simplifies VPN configuration by using virtual interfaces.
                                            : Supports unicast and multicast encrypted traffic.                                  
    e. Service Provider MPLS VPNs:
       Layer 2 MPLS VPN: Emulates Ethernet LAN segments.
                       : Customer handles routing.
       Layer 3 MPLS VPN: Provider Participates in customer routing.
### 3. IPsec
    a. Functions
       Confidenditiality: Encrypts data with algorithms like AES, 3DES.
       Integrity: Ensures no data alteration using HMAC with MD5/SHA/
       Authentication: Validates peers with pre-shared kets or RSA.
       Key Exchange: Uses Diffie-Hellman to establish shared secrets securely.
    b. Modes
       Transport Mode: Encrypts payload only.
       Tunnel mode: Encrypts entire IP packet.
    c. Protocols
       Authentication Header (AH): Provides integrity and authentication.
       Encapsulation Security Payload (ESP): Adds confidentiality to AH features.
    d. Encryption Algorithms
       DES: 56-bit key.
       3DES: Three 56-bit keys.
       AES: 128, 192, or 256 bits.
       SEAL: Stream cipher with a 160-bit key.
    e. Diffie-Hellman Groups
       Group 1: 768 bits (deprecated).
       Group 14: 2048 bits.
       Group 20: 384 bits (ECC)
