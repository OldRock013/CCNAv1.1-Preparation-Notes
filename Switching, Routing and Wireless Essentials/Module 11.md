# Switch Security Configuration

### 1. Implement Port Security
    a.Secure Unused Ports
      - Disable all unused ports using "shutdown" command.
      - Reactivate ports with the "no shutdown" command.
    b. Mitigate MAC Address Table Attacks
      - Enable port security to limit the number of valid MAC addresses on a port.
      - Manually configure or dynamically learn MAC addresses.
    c. Enable Port Security
      - Use "switchport port-security" on access or trunk ports.
      - Use "show port-security" to verify settings.
      - Port Security Violation Modes
        Shutdown: Default mode, disables port upon violation.
        Restrict: Drops packets and logs violation
        Protect: Drops packets but not log violations
### 2. Mitigate VLAN Attacks
       Steps to mitigate VLAN Hopping
       1. Disable DTP on non-trunking ports using "switchport mode access"
       2. Disable unused ports and assign to an unused VLAN.
       3. Manually enable trunk links and set native VLAN to a non-default VLAN.
### 3. Mitigate DHCP Attacks
       DHCP Snooping - FIlters DHCP messages and creates a DHCP binding table.
       Steps:
       1. Enable DHCP snooping globally.
       2. Configure trusted ports using "ip dhcp snooping trust"
       3. Limit DHCP traffic rate on untrusted ports.
### 4. Mitigate ARP Attacks 
       Dynamic ARP Inspection (DAI)
       1. Verifies ARP packet against the DHCP Snooping table.
       2. Enable DAI on selected VLANs
       3. Configure trusted interfaces for DHCP snooping and ARP inspection.
### 5. Mitigate STP Attacks
       PortFast and BGPU Guard
       PortFast: Immediately Transitions a port to forwarding state.
       BPDU Guard: Disables port upon receiving BPDUs
       
       
       
