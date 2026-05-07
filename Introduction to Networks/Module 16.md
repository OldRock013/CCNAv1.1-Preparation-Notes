# NETWORK SECURITY FUNDAMENTALS

### 1. Security Threats and Vulnerabilities.
     a. Types of Threat
        - Information Theft
        - Data loss and manipulation.
        - Identity Theft
        - Disruption of Service
     b. Types of Vulnerabilities
         - Technological
           * TCP/IP protocol weaknesses
           * Operating system weaknesses
           * Network equipment weaknesses
         - Configuration
           * Unsecured user accounts
           * Default settings and passwords
           * Misconfigured internet services
         - Security Policy 
           * Lack of Security policies
           * Inadequate access controls
           * Missing disaster recovery plans
      c. Physical Security
         - Hardware threats: Damage to servers, routers, switches, etc.
         - Environmental threats: Temperature or humidity extremes.
         - Electrical threats: voltage spikes, power loss, noise.
         - Maintenance threats: Poor handling, lack of spare parts, misleading.
### 2. Network Attacks
      a. Network attacks
         - Types of Malware
            * Viruses: attach to files, spread through execution.
            * Worms: Standalone; propagate without a host.
            * Trojan Horses: Disguised as legitimate software.
         - Types of attacks
            * Reconnaissance Attacks: Mapping systems and vulnerabilities; Tools: nslookup, whois, ping
            * Access Attacks: 
            Exploit: authentication and service vulnerabilities.
            Methods: Password attacks, trust exploitation, port redirection, main-in-the-middle.
         - Denial of Service (DoS): Consume resources to disrupt communication.
            * Distributed Denial of Service (DDoS): Uses botnets for coordinated attacks.
### 3. Network Attack Mitigation
      a. Defense-in-depth: Uses multitple layers: VPN, firewalls, IPS, ESA/WSA, AAA Servers.
      b. Keep Backups: Regular Full and partial backups. Validate data integrity and secure storage.
      c. Upgrade, Update, and Patch: Apply security updates and pactches regularly. Automate updates for end systems.
      d. Authentication, Authorization, Accounting (AAA)
         Authentication: Who can access.
         Authorization: What actions are allowed.
         Accounting: Logs activities for auditing.
      e. Firewalls: Packet Filtering, Application filtering (ports), URL Filtering, Stateful Packet Inspection (Inspection)
      f. Endpoint Security: Secure Endpoints, Use anti-virus, host intrusion prevention and access controls.
### 4. Device Security
      a. Cisco AutoSecure: Automates securing default configurations.
      b. Password Security: Use complex, lengthly passwods or phrases. Avoid easily guessed, change password regularly.
      c. Addtional Password Security: 
         Encrypt Plaintext passwords (service password-encryption)
         Set minimum password lengths
         Block brute-force attacks with (login block-for)
         Set inactivity timeouts with (exec-timeout)
### 5. Enable SSH
      a. Configure hostname and domain name.
      b. Generate encryption keys.
      c. Authenticate with local database.
      d. Enable SSH Sessions.
### 6. Disbale Unused Services
      a. Disable unused ports and services.
      b. Validate open ports (show ip ports all)or (show control-plane host open-ports)
          
         
Summary:

Identify and mitigate threats.

Employ a layered security approach.

Use strong password policies and AAA.

Secure devices with SSH and disable unused services.
Regularly update and backup configurations.
            
           
           
           


