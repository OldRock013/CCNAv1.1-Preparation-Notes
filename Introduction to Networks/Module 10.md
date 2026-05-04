# BASIC ROUTER CONFIGURATION

  Implement initial settings on routers and end devices

### 1. Configure Initial Router Settings

    a. Configure the device name.
       Command: Router(config)# hostname hostname
    b. Secure privileged EXEC mode
       Command: Router(config)# enable secret password
    c. Secure User EXEC mode
        Commands:
        Router(config)# line console 0
        Router(config-line)# password password
        Router(config-line)# login
    d. Secure remote Telnet/SSG access
       Commands:
       Router(config)# line vty 0 4
       Router(config-line)# password password
       Router(config-line)# login
       Router(config-line)# transport input {input | telnet}
    e. Encrypt all plaintext passwords
       Commands:
       Router(config)# service password-encryption
    f. Provide legal notification.
       Commands:
       Router(config)# banner motd #message#
    g. Save the configuration
      Commands: 
      Router# copy running-config startup-config

Example Basic router configuration:

      Router(config)# hostname R1
      R1(config)# enable secret class
      R1(config)# line console 0
      R1(config-line)# password cisco
      R1(config-line)# login
      R1(config-line)# line vty 0 4
      R1(config-line)# password cisco
      R1(config-line)# login
      R1(config-line)# transport input ssh telnet
      R1(config-line)# exit
      R1(config)# service password encryption
      R1(config)# banner motd #WARNING: Unauthorized access is prohibited#
      R1(config)# exit
      R1# copy running-config startup-config
     
### 2. Configure Interfaces

  Steps to configure router interfaces:

      1. Access interface
      Command: R1(config)# interface type-and number
      2. Add a description
      Command R1(config-if)# description description text
      3. Configure IPv4 address and subnet mask
      Command: R1(config-if)# ip address ipv4-address subnet-mask
      4. Configure IPv6 address and prefix length
      Command: Router(config-if)# ipv6 address ipv6-address/prefix-length
      5. Activate the interface:
      Command: Router(config-if)# no shutdown

  Verification commands:

      show ip interface brief: Displays interface status and assigned IPv4 addresses.
      show ipv6 interface brief: Displays interface status and assigned IPv6 addresses.
      show ip route: Displays IPv4 routing table.
      show ipv6 route: Displays IPv6 routing table.
      show interfaces: Displays detailed statistics for all interfaces.

  Configure Default Gateway

      Used to forward packets to remote networks.
      Default gateway is typically the router interface connected to the host network.
      Example: For PC3 to reach PC1, the default gateway for PC3 is the G0/0/0 interface of R1

 Configure the default gateway on a switch
      
      Required for remote management.
      Command: ip default-gateway ip-address
