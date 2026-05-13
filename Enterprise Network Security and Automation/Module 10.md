# Network Management

### 1. Device Discovery
    a. Cisco Discovery Protocol (CDP): Ciscp proprietary Layer 2 protocol for discovering neighboring Cisco devices.
       Features: Enabled by default on Cisco devices.
               : Shares information about device type, name and interfaces.
       Configuration:
       Enable/disable globally: cdp run / no cdp run
       Enable/Disable on interfaces: cdp enable / no cdp enable
       View neighbor: Show cdp neighbors or show cdp neighbors detail
    b. Link Layer Discovery Protocol (LLDP): Vendor-neutral Layer 2 discovery protocol.
       Configuration:
       Enable globally: lldp run
       Enable transmission/reception: lldp transmit, lldp receive
       Verify: show lldp or show lldp neighbors detail    
### 2. Time Synchronization
       - Ensures synchronized time accross network devices.
    a. NTP hierarchy:
       Stratum 0: High-precision time sources
       Stratum 1: Directly connected devices.
       Stratum 2+: Devices synchronizing to stratum 1 or peers.
    b. Ports: UDP 123
    c. Configuration:
       Set NTP Server: ntp server <IP>
       Verify: show ntp status, show ntp associations
### 3. SNMP
       - Application Layer protocol for network monitoring management
    a. Components:
          SNMP Manager: Collects and modifies device data.
          SNMP Agent: Resides on managed devices.
          MIB: Database storing device information.
    b. Versions:
          SNMPv1: Basic community-string authentication.
          SNMPv2c: Adds bulk retrieval.
          SNMPv3: Enhanced security with encryption and authentication.
    c. Commmands: SNMP GET, SET, TRAP         
### 4. Syslog
       - Event logging protocol using UDP port 514.
    a. Message Components: Severity levels (0: Emergency, 7:debug).
                         : Facilities (e.g., IP, OSPF, SYS)
    b. Configuration: Enable timestamps: service timestamps log datetime
                    : Output destinations: buffer, console, terminal, or Syslog server.
### 5. File Maintenance
       Backup and Restore:
         a. TFTP:
            Backup: copy running-config tftp.
            Restore: copy tftp running-config.
         b. USB:
            Backup: copy running-config usbflash0:.
            Restore: copy usbflash0:/<file> running-config.
         c. Text files:
            Backup via Tera Term.
            Restore by pasting commands.
### 6. IOS Image Management
    a. Backup IOS: Ping TFTP server to verify connectovity
                 : Copy immage: copy flash tftp 
    b. Upgrade IOS:
       Copy image to device: copy tftp flash.
       Set boot system: boot system <image>.
       Save config and reload
