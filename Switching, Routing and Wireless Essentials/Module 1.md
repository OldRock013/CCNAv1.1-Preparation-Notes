# BASIC DEVICE CONFIGURATION

### 1. Configure a switch with Initial Settings:
    a. Switch Boot Sequence
       Step 1: Power-on Self-test (POST) program checks CPU , DRAM, and flash file system.
       Step 2: Boot loader software initialized CPU registers and flash file system.
       Step 3: Boot loader loads default IOS operating system.
    b. The Boot System Command:
       Automatically boots using BOOT environment variable.
       Command: boot system flash:<path>/<IOS file>
       Use show boot to verify current IOS boot file
    c. Switch LED Indicators
       System LED (SYST): Power and Functionality
       Redundant Power Supply LED (RPS): RPS Power
       Port Status LED (STAT): Port status mode.
       Port Duplex LED (DUPLX): Duplex mode.
       Port Speed LED (SPEED): Speed mode.
       Power over Ethernet LED (PoE): PoE status. 
    d. Recovering from system crash:
       Access boot loader via console connection.
       Steps: Connect console cable , power cycle switch, press mode button, access boot loader prompt.
    e. Switch Management Access:
       Configure IP address and subnet mask for remote manangement
       Assign IP to Switch Virtual Interface (SVI)
    f. SVI configuration
       Configure IPv4 and IPv6 addresses
       Enable management interface with ni shutdown.
       Configure default gateway for remote management
### 2. Configure Switch Ports
    a. Duplex Communication:
        - Full-duplex: Bidirectional communication, no collisions.
        - Half-duplex: Unidirectional, prone to collisions
    b. Configure Physical Layer Settings:
        - Commands: duplex <mode>, speed <value>
        - Default: Auto-negotiation for speed and duplex.
    c. Auto-MDIX: Automaticallu detects cable type (straight-through or crossover)
        - Enable by default on newer switches
    d. Switch Verification Commands
        - show interfaces: Displays interface status and statistics.
        - show running-config: Verifies configuration.
        - show mac address-table: Displays MAC address table.
    e. Troubleshooting Network Access Layer Issues
       - Use show interfaces to detect media errors (e.g., CRC, collisions)
       - Common errors: Runts, giants, late collisions
### 3. Secure Remote Access
    a. Telnet: Uses TCP Port 23. Unsecure plaintect transmission
    b. SSH: Uses TCP port 22. Secure encrypted management connection.
       Steps to configure:
       1. Verify SSH Support (show ip ssh)
       2. Configure IP domain name
       3. Generate RSA key pairs.
       4. Configure user authentication
       5. Enable SSH on vty lines
       6. Enable SSH version 2
    c. Verify SSH: Use show ip ssh to verify SSH configuration. Test SSH connection using a client like PuTTY
### 4. Basic Router Configuration
    a. Initial Configuration Tasks:
        1. Name the device
        2. Configure passwords
        3. Configure banner for legal notofication
        4. Save configuration
    b. Router Interfaces:
        1. Configure IPv4 and IPv6 addresses
        2. activate interfaces with no shutdown.
        3. Add descriptions for interfaces.
    c. IPv4 Loopback Interface
        - Logical interface internal to the router.
        - Always in "up" state
        - Useful for testing and management
### 5. Verify Directly Connected networks
    a. Interface Verification Commands:
           show ip interface brief: Summary of IPv4 interfaces
           show ipv6 interface brief: Summary of IPv6 interfaces
           show running-config interface: Displays applied commands.
    b. Verify Routes:
           show ip route: Displays IPv4 routing table.
           show ipv6 route: Displays IPv6 routing table
           Connected routes marked with "C"
           Local routes marked with "L"
    c. Filter show Command Output: Use pipe | with parameters
    d. Command History
        - Recall commands with Ctrl+P or Up Arrow.
        - Veiw history with show history
        - Adjust buffer size with terminal history size
        
       
