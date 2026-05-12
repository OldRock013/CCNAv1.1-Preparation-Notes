# Network Security Conepts

### 1. Current State of Cybersecurity
    a. Definitions
       1. Assets: Anything of value to an organization, including people, equipment, resources, and data.
       2. Vulenerability: A weakness in a system or design that could be exploited.
       3. Threat: A potential danget to assets or data.
       4. Exploit: A mechanism to take advantage of a vulnerability
       5. Mitigation: Countermeasures to reduce risk.
       6. Risk: Likelihood of a threat exploiting a vulnerability.
    b. Attack Vectors
       1. Internal Threats: Diret access to infrastructure, more damaging than external threats.
       2. External Threats: Originating from outside the organization.
    c. Data Loss
       Impact: Brand damage, loss of reputation.
             : Financial loss, customer attrition, litigation.
       Vectors:
       Email/Social Networking
       Unencrypted Devices
       Cloud Storage
       Removeable Media
       Weak Access Control
       Hard Copy Documents
### 2. Threat Actors
    a. Types of hackers
       White Hat Hackers: Ethical hackers who reported vulnerabilities.
       Gray Hat Hackers: Sometimes ethical, often act without permission.
       Black Hat Hackers: Maliciuos hackers aiming for personal gain or damage.
    b. Modern Hacking Terms:
       Script Kiddies: Use pre-written scripts without deep understanding.
       Vulnerability Brokers: Find vulnerabilities, report them for rewards.
       Hacktivists: Protest groups targeting organizations or governments.
       Cybercriminals: Operate for profit, selling stolen data and tools.
       State-Sponsored Hackers: Perform cyber-espionage and sabotage.
       
### 3. Threat Actor Tools
    a. Categories:
       Password Crackers: Tools like John the Ripper, Ophcrack.
       Wireless Hacking Tools: Tools like Aircrack-ng, Kismet.
       Network Scanning Tools: Tools like Nmap, SuperScan.
       Packet Crafting Tools: Tools like Hping, Scapy.
       Packet Sniffers: Tools like Wireshark, Tcpdump.
       Rootkit Detectors: Tools like AIDE, Netfilter.
       Fuzzers: Tools to discover vulnerabilities (e.g., Skipfish).
       Forensic Tools: Tools for data recovery (e.g., Sleuth Kit).
       Encryption Tools: Tools like VeraCrypt, OpenVPN.
       Vulnerability Scanners: Tools like Nessus, OpenVAS.
    b. Attack Types
       Eavesdropping: Captures network traffic.
       Data Modification: Alters data packets.
       IP Spoofing: Fakes source IP.
       Password-Based Attacks: Gains access through valid credentials.
       DoS/DDoS Attacks: Floods targets with traffic.
       Man-in-the-Middle (MITM): Intercepts communications.
       Sniffer Attacks: Reads and captures unencrypted packets.    
### 4. Malware
       Types of Malware:
       Viruses: Propagate through human action. Types: Boot Sector, Firmware, Macro, Program, Script.
       Trojan Horses: Disguise malicious code as useful programs. | Types: Remote Access, Data-Sending, Proxy, Keylogger.
       Adware: Delivers unsolicited ads.
       Ransomware: Encrypts files, demands ransom.
       Rootkits: Provide administrative access for threat actors.
       Spyware: Gathers user data without consent.
       Worms: Self-replicating programs.
### 5. Common Network Attacks
    a. Reconnaissance Attacks
       - Information Queries.
       - Ping Sweeps.
       - Port Scans.
       - Vulnerability Scanners.
       - Exploitation Tools.
    b. Access Attacks
       - Password Attacks.
       - Spoofing (IP, MAC, DHCP).
       - Trust Exploitations.
       - Port Redirections.
       - MITM Attacks.
       - Buffer Overflows.
    c. Social Engineering Attacks
       Techniques: Phishing, Spear Phishing, Baiting. Pretexting, Tailgating, Shoulder Surfing.
        Dumpster Diving, Impersonation.
       Prevention: User Education, Identity validation strategies.
        Pretexting, Tailgating, Shoulder Surfing.
        Dumpster Diving, Impersonation.
    d. DoS and DDoS Attacks
       DoS: Overwhelms a target with traffic or malformed packets.
       DDoS: Uses coordinated sources (zombies) to attack.
### 6. IP Vulnerabilities and Threats
    a. ICMP Attacks: Echo Request/Reply, Mask Reply, Redirects.
    b. Amplification Attacks: Use protocols like DNS, NTP.
    c. Spoofing Attacks: Fake source IP/MAC addresses.
    d. MITM Attacks: Intercept and control communication.
    e. Session Hijacking: Take over active sessions
### 7. Network Security Best Practices
    a. Defense in Depth: Layered security.
    b. Strong Authentication: Use multi-factor authentication.
    c. Secure Configurations: Disable unused ports/services.
    d. Monitoring: Implement intrusion detection/prevention.
    e. User Education: Regular training on security practices
### 8. Cryptograph 
    a. Purpose: Protects data in transit
    b. Techniques:
      Symmetric Encryption: Same key for encryption/decryption.
      Asymmetric Encryption: Public/private key pairs.
      Hashing: Ensures data integrity.
