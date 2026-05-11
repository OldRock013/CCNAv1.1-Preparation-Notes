# WLAN Configuration

### 1. Remote Site WLAN Configuration
    a. The Wireles Router
       - Integrated router with switch, WAN port, and wireless access.
       - Provides DHCP, NAT, QoS, and WLAN security.
    b. Basic Network Setup
       - Log in to the router GUI
       - Change default administrative credentials
       - Configure DHCP IPv4 addresses.
       - Renew and verify configurations.
    c. Basic Wireless Setup
       - Configure SSID, security mode, and passphrase
       - Avoid channel overlap by selecting non-overlapping channels.
       - Adjust network mode for specific 802.11 standards.
    d. Wireless Mesh Networks
       - Extend WLAN Range using additional access points.
       - Create a wireless mesh by configuring APs with identical settings and non-overlapping channels
### 2. Configure a Basic WLAN on the WLC
    a. WLC Overview
       - Uses Lightweight Access Point Protocol (LWAPP) for managing multiple APs
       - Provides a centralized management interface for WLANs
    b. Steps to Configure a WLAN
       1. Create and Enable a WLAN
       2. Assign a VLAN interface to the WLAN.
       3. Configure SSID and security settings.
       4. Monitor WLAN performance and connected clients
### 3. Configure a WPA2 Enterprise WLAN on the WLC
    a. WPA2 Enterprise Features
       - Uses 802.1X with RADIUS server for authentication.
       - Encrypts traffic with AES for enhanced security.
    b. Steps to Configure WPA2 Enterprise WLAn
       1. Configure SNMP and RADIUS server settinds on the WLC
       2. Deploy a new VLAN interface for the WLAN
       3. Assign the VLAN to the WLAN and enable WPA2-Enterprise security.
       4. Verify the RADIUS server and client connectivity.
### 4. Troubleshoot WLAN Issues
    a. Common Issues and Solutions
       - Verify network settings using ipconfig.
       - Check physical setup and AP configurations.
       - Monitor WLAN performance and interference.
    b. Optimize Network Performance
       - Upgrade wireless clients to newer standards (e.g., 802.11ac)
       - Use dual-band routers to distribute traffic between 2.4GHz and 5 GHz
       
    
       
