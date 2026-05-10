# WLAN Concepts

### 1. Introduction to Wireless
    a. Benefits of Wireless
       - Enables mobility in homes, offices, and campuses.
       - Adapts to changing needs and technologies.
    b. Types of Wireless Networks
       WPAN: Short-range (20-30ft), IEEE 802.15 standard (e.g., Bluetooth.)
       WLAN: Medium-range (up to 300ft), IEEE 802.11 standard.
       WMAN: Large geographic areas like cities.
       WWAN: Global communication using licensed frequencies.
       Standard,Wi-Fi Generation,Release Year,Frequency Band,Max Data Rate (Theoretical)
<img width="746" height="237" alt="image" src="https://github.com/user-attachments/assets/6eee443a-da85-4a94-a3cb-cc1d581fa329" />

### 2. WLAN Components
    a. Wireless Access Points (APs)
       - Clients associate and Authenticate with APs
       - Categories: Autonomuos (Standalone) and Controller-Based (managed by WLC)
    b. Wireless Antennas
       - Omnidirectional: 360-degree coverage.
       - Directional: Focused signals, e.g., Yagi Antennas.
### 3. WLAN Operation
       802.11 Topology Modes:
       Ad hoc: Peer-to-Peer communication.
       Infrastructure: APs connect clients to the network
       CSMA/CA: Avoids collisions using RTS/CTS messages.
       Three stages: Discovery, authetication, and association.
### 4. CAPWAP Operation
       - Manages APs and WLANs using tunnels (UDP ports 5246/5247)
       - DTLS encrypts control channel betwrrn AP and WLC.
### 5. Frequency Bands
       2.4 GHz: 1, 6, and 11 for non-overlapping usage.
       5 GHz: Channels 36, 46, and 60 for non-overlapping usage.
### 6. WLAN Threats
       a. Common Threats - Data INterception, wireless intruders, DoS attacks, and rogue APs.
       b. Mitigation Techniques - Use strong authentication, encryption, and rouge AP monitoring
### 7. Secure WLANs
       Authentication and Encryption
       - WPA2/WPA3: Use AES for strong encryption.
       - WPA3 introduces SAE for personal security and PMF for enterprise.
       
       
