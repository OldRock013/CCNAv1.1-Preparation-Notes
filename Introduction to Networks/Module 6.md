# Data Link Layer

### 1. Purpose of the Data Link Layer

   a. Responsible for NIC to NIC communications.

   b. Encapsulates Layer 3 *Packets* into Layer 2 *Frames*

   c. Performs Error Detection, rejects corrupt frames.

   d. IEEE 802 LAN/MAN Data Link Sublayers:

       Logical Link Control (LLC) sublayer for software to hardware communication.
       Media Access Control (MAC) sublayer for data encapsulation and media access control.

   e. Providing access to media - Router functions at each hop (frame acceptance, de-encapsulation, re-encapsulation, forwarding)
   d. Data Link Layer Standards - Defined by organizations like IEEE, ITU, ISO, ANSI

### 2. Topologies
  
  a. Physical and Logical Topologies 

      Physical Topology: Actual connections between devices.
      Logical Topology: Virtual connections based on interfaces and IP schemes.

  b. WAN Topologies:

      Point-to-Point: Simplest, direct link betwrrn two endpoints.
      Hub and Spoke: central site connects to branch sites.
      Mesh: all-to-all connection for high availabilitu.
  
  c. Point-to-Point Topologies - Direct connection between two node, no sharing of media. | Protocols can be simple due to direct line of communication.

  d. LAN Topologies

     Star and Extended star: common, scalable, east to troubleshoot.
     Bus: all devices on a single cable use, terminated at ends.
     Ring: eash device connected to neighbors in a loop.

  e. Half and Full duplex: Half Duplex - one device sends/ receive at a time | Full-duplex - Simultaneous send/receive.

  f. Access Control Methods

      Contention-based:
         CSMA/CD - Ethernet, detects collisions; Devices detecs collisions, wait, then retransmit after a random delay.
         CSMA/CA - WLANs, avoids collision.; Devices broadcast transmission duration to avoid collisions.
      Controlled access: deterministic, each node gets specific time.
      
   ### 3. Data Link Frame

   The frame consists of Header, data and trailer. Controls information varies by protocol and topology.
   <img width="751" height="515" alt="image" src="https://github.com/user-attachments/assets/5ad4ed3c-9484-4862-89c0-880ac803d8df" />
   <img width="715" height="381" alt="image" src="https://github.com/user-attachments/assets/15e0fb24-50ea-4718-afa8-eae097a10c7c" />


      Frame Fields:
      Preamble: allows devices to synchronize their receiver clocks. Length: 7 bytes = 56 bits
      Frame Start and Stop: signals beginning and end. Lenght 1 byte = 8 bits
      Addressing: source and destination indentifiers. Source and destination: 6 bytes (48 bits)
      Type: specifies encapsulated Layer 3 protocol. length: 2 bytes = 16 bits
      Control: Flow control information. length: 4 bytes = 32 bits.
      Data: Actual frame payload.
      Error Detection: checks for transmisson errors.

      Ethernet header = Preamble + SFD + Destination + Source + Type = 7 + 1 + 6 + 6 + 2 = 22 bytes
      Ethernet Trailer = FCS (Error detection and control flow) = 6 bytes
      Packet or data = 46 bytes (minimun)
      Minimum size ethernet frame is 64 bytes.
      Preamble and SFD are not part of Ethernet header
      Therefore Ehternet header + Trailer = 18 bytes
<img width="700" height="198" alt="image" src="https://github.com/user-attachments/assets/d4f766f6-ee66-4a3a-bad6-3857c181eb51" />
