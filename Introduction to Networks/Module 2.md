Basic Switch and End Device Configuration

1. Cisco IOS Access

       a. Operating Systems:
           *Shell - User interface enabling command input such as CLI and GUI
           *Kernel - Manages hardware and software communication. Allocates system resources
           *Hardware - Physical components of devices, including electronics
       b. GUI (Graphical User Interface) - Provide visual navigation with icons and menus. ex. Windows, macOS
       c. Terminal Emulation Programs
           *PuTTY - Popular open-source emulator
           *Tera Term - Lightweight and versatile
           *Secure CRT - For professional-grade management
   
2. IOS Navigation

       a. Primary Command Modes:
           *User EXEC Mode - Basic monitoring commands only | Prompt: Switch>
           *Priveleged EXEC Mode - Full command access for configurations and diagnostics. | Prompt: Switch#
           *Global Configuration Mode - Access via configure terminal, Used for device-wide settings.
           *Subconfiguration Modes:
             >Line Configuration mode - configures console, Telnet, or SSH access.
             >Interface Configuration mode - Configure ports, VLANS and IP settings.

       b. Switching Between modes
           "enable": User EXEC > Privileged EXEC
           "disable": Privileged EXEC > User EXEC
           "exit": Move one mode lower.
           "end": Return to Priveleged EXEC mode.
           Shortcut: Ctrl+Z returns to privileged EXEC mode.

       c.Command Syntax and Hotkeys
         Keywords: Fixed elements (eg. ip)
         Arguments: user-defined values (eg. 192.168.1.1)

3. Basic Device Configuration

        a. Device Names - it distinguish devices in a network. Begin with a letter, No spaces; use letters, digits or dashes, Max length 64 characters.
           Example: hostname Switch1
           To reset to the default name: no hostname

        b. Password Security:
           *User EXEC Password: Secure console access
           *Priveleged EXEC Password: Secures administratice access.
           *VTY Passwords: Secures remote access (Telnet/SSH)
           Guidelines: Use at least 8 characters, Combine upper/lower case letters, number nad symbols, Avoid common words or shared passwords.
           Encryption: Use "service password-encryption" to ensure plaintext passwords.
   <img width="332" height="127" alt="image" src="https://github.com/user-attachments/assets/41e69ebb-391b-4e75-b84a-f023c7d39d95" />

         c. Banner Messages - Display warnings for unauthorozed access
   <img width="657" height="73" alt="image" src="https://github.com/user-attachments/assets/6fb08b1a-a731-4df3-bcc9-a0e44b5d9fdd" />

4. Save Configurations

         Configuration Files:
         *Running-Config - Stored in RAM, Reflects active settings.
         *Startup-Config - Stored in NVRAM, Loaded when the device restarts.
         Save changes: "copy running-config startup-config"
         Erase configurations: "erase startup-config" then "reload"

5. Ports and addresses

         a.IP addressing:
           *IPv4: 32 bit address in dotted format (eg. 192.181.1.1) accoumpanied by subnet mask 255.255.255.0
           *IPv6: 128 bit address in hexadecimal format. Supports greater scalability and improved routing
           *Default gateway: Router ised for communication outside the local network
         b. Interface and Ports:
           *Twisted-pair copper cables; Considerations transmission distance
           *Fiber-optic cables; Considerations environment (Interference)
           *Wireless technologies; Bandwidth requirements

6. Configure IP addressing

         a. Manual Configuration
         b. Dynamic Configuration
         c. Switch Virtual Interface (SVI)

7. Verify Connectivity

         a. Testing Tools: Ping command and Tracerouter command
