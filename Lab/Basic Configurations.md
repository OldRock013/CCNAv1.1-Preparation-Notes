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
   
8. Exec timeout - used to set an inactivity timer for console or VTY (Telnet/SSH) sessions. If a session remains idle for the specified time, it will automatically disconnect

       CLI:
       R1(config)#line console 0
       R1(config-line)#exec-timeout 5 00
   
10. Logging Synchronous - used to prevent syslog messages from interrupting user input on the console or VTY lines. By default, system messages (like interface status changes) can appear while you're typing a command, making it difficult to read or complete your input.

        CLI:
        R1(config)#line console 0
        R1(config-line)#logging synchronous

11. Disabling ip domain lookup - a feature that allows the router to resolve unrecognized commands or hostnames into IP addresses using DNS. 

- Avoids delays when mistyping commands.

- Prevents unnecessary DNS queries, improving responsiveness.

- Enhances security by reducing external DNS dependency.

        CLI:
        R1(config)#no ip domain-lookup  
        
12. IP domain name - used to set a domain name for the device, which is often required for features like SSH, PKI certificates, and DNS resolution

        CLI:
        R1(config)#ip domain-name cisco.com
14. Username and password
15. Encrypting all passwords
16. Set Current Clock Time
17. Set management IP Address-SW
18. Prevent Brute-force Attack-Router
19. Viewing Running & Startup Configs
20. Saving running into startup configs
       
