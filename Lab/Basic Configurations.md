# Basic Configuration

### Topology

<img width="257" height="127" alt="image" src="https://github.com/user-attachments/assets/3a6d71a8-d347-4eb3-b27b-35f141308f92" />

In this LAB includes:

    1. Hostname
    2. Banner motd/message
    3. Enable Password
    4. Line console password
    5. Line VTY password
    5. Exec timeout
    6. Logging Synchronous
    7. Disabling ip domain lookup
    8. IP domain name
    9. Username and password
    10. Encrypting all passwords
    11. Set Current Clock Time
    12. Set management IP Address-SW
    13. Prevent Brute-force Attack-Router
    14. Viewing Running & Startup Configs
    15. Saving running into startup configs

### Configurations:

1. Hostname - Used to set or change the name of a device.

       CLI:
       Router>enable
       Router#configure terminal 
       Router(config)#hostname R1
       R1(config)#
2. Banner motd/message - used to configure a Message of the Day (MOTD) banner, which is displayed to users when they connect to the device via console, Telnet, or SSH. This banner is often used for security warnings, system notices, or general information.

       CLI:
       Router#configure terminal 
       R1(config)#banner motd *Authorized Access Only*
        
3. Enable Password - used to set a password for privileged EXEC mode, preventing unauthorized access to critical system configurations. However, it stores the password in plaintext, making it less secure.

       CLI:
       R1(config)#enable password MySecurePass

4. Line console password - used to configure console access settings, including setting a password for users connecting via the console port.

       CLI:
       R1(config)#line console 0
       R1(config-line)#password MySecureConsole
       R1(config-line)#login
        
6. Line VTY password - used to configure Virtual Terminal (VTY) lines, which control remote access to the device via Telnet or SSH. Setting a password ensures that only authorized users can connect remotely.

       CLI:
       R1(config)#line vty 0 15
       R1(config-line)#password MySecureVTY
       R1(config-line)#login
   
7. Exec timeout - used to set an inactivity timer for console or VTY (Telnet/SSH) sessions. If a session remains idle for the specified time, it will automatically disconnect

       CLI:
       R1(config)#line console 0
       R1(config-line)#exec-timeout 5 00
   
8. Logging Synchronous - used to prevent syslog messages from interrupting user input on the console or VTY lines. By default, system messages (like interface status changes) can appear while you're typing a command, making it difficult to read or complete your input.

        CLI:
        R1(config)#line console 0
        R1(config-line)#logging synchronous

9. Disabling ip domain lookup - a feature that allows the router to resolve unrecognized commands or hostnames into IP addresses using DNS. 

- Avoids delays when mistyping commands.

- Prevents unnecessary DNS queries, improving responsiveness.

- Enhances security by reducing external DNS dependency.

        CLI:
        R1(config)#no ip domain-lookup  
        
10. IP domain name - used to set a domain name for the device, which is often required for features like SSH, PKI certificates, and DNS resolution

        CLI:
        R1(config)#ip domain-name cisco.com
11. Username and password - Configure local usernames and passwords to authenticate users accessing the device via console, Telnet, or SSH.

Example:
           
        R1(config)#username admin ?
        password   Specify the password for the user
        privilege  Set user privilege level
        secret     Specify the secret for the user
        <cr>
        R1(config)#username admin privilege ?
        <0-15>  User privilege level
        R1(config)#username admin privilege 15 ?
        password  Specify the password for the user
        secret    Specify the secret for the user
        
        CLI:
        R1(config)#username admin privilege 15 secret S3cur3P@ss
        **********Applying to Console &VTY lines***************
        R1(config)#line console 0
        R1(config-line)#login local
        R1(config-line)#line vty 0 15 
        R1(config-line)#login local
        
12. Encrypting all passwords - Encrypts passwords using Type 7 encryption (Vigenère cipher).  Prevents passwords from being visible in show running-config. Not highly secure—Type 7 encryption is reversible.


        CLI:
        R1(config)#service password-encryption

14. Set Current Clock Time -To manually set the current clock time on a Cisco IOS device

        CLI:
        R1#clock set 01:31:00 June 1 2026
    
15. Set management IP Address-SW - typically configure an interface that will be used for remote management, such as a VLAN interface or a loopback interface.

        CLI:
        R1(config)#interface vlan 1
        R1(config-if)#ip address 192.168.1.1 255.255.255.0
        R1(config-if)#no shutdown
        
16. Prevent Brute-force Attack-Router -Blocks login for 120 seconds if there are 3 failed attempts within 60 seconds. Helps mitigate dictionary attacks and denial-of-service (DoS) attacks.

        Example:
        R1(config)#login ?
        block-for   Set quiet-mode active time period
        on-failure  Set options for failed login attempt
        on-success  Set options for successful login attempt
        R1(config)#login block-for ?
          <1-65535>  Time period in seconds
        R1(config)#login block-for 120 ?
        attempts  Set max number of fail attempts
        R1(config)#login block-for 120 attempts ?
          <1-65535>  Fail attempts max value
        R1(config)#login block-for 120 attempts 3
        R1(config)#login block-for 120 attempts 3 ?
          within  Watch period for fail attempts
        R1(config)#login block-for 120 attempts 3 within ?
          <1-65535>  Time period in seconds
        ===============================================================  
        CLI:
        R1(config)#login block-for 120 attempts 3 within 60

18. Viewing Running & Startup Configs and Saving running into startup configs

    Runing Config:

    - Displays the current settings stored in RAM.

    - Changes made here are not saved unless explicitly copied to startup config

    Startup Config:

    - Stored in NVRAM.

    - If different from the running config, the device will revert to this on reboot
    
    Copy run startup:

    - Saves the current settings to NVRAM.

    - Prevents loss of configuration after a power cycle

          CLI:
          R1# show running-config
          R1# show startup-config
          R1# copy running-config startup-config
      
          
