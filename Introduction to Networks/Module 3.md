PROTOCOLS AND MODELS

1. The Rules

       a. Communication Fundamentals - Networks require a source (Sender), destination (receiver), and channel (media)
       b. Communication Protocols - Protocols ensure successful communication through common aggrements
                                  - Governed by protocols specifying rules for communication.
       c. Rule Establishment - Identified sender and receiver, common language, timing and acknowledgement
       d. Network Protocol Requirements - message encoding, formatting, size, timing and delivery options.
       e. Message Encoding - Converts information into a transmittable format.
                           - Decoding interprets transmitted information back to its original form.
       f. Message Formatting and Encapsulation - Requires specific formats for message type and channel.
       g. Message Timing - Include flow control, response timeout, and access methods.
       h. Message Delivery Options - Types: Unicast, Milticast, Broadcast.
                                   - IPv6 introduces Anycast.

2. Protocols

       a. Network Protocol Overview - Rules include addressing, reliability, flow control, sequencing, and error detection.
                                    - Protocols interact, such as HTTP, TCP, IP, Ethernet.
       b. Network Protocol Functions - Addressing identifies sender and receiver.
                                     - Reliability ensures guranteed delivery.
                                     - Flow control and error detection manage data integrity.

3. Protocol Suites - A group of interrelated protocols necessary for communication.

        Examples:
        a. TCP/IP: Open, standards-based, and widely used.
        b. OSE, AppleTalk, Novell NetWare
        Layered Models: 
        TCP/IP (Transmossion Control Protocol/Internet Protocol): Application > Transport, Internet, Network Access Layers
        OSI (Open Systems Interconnection) Model: Application > Presentation > Session > Transport > Network > Data > Physical
        Comparison: OSI provides detailed layers; TCP/IP focuses on practical implementation

    <img width="332" height="257" alt="image" src="https://github.com/user-attachments/assets/1f424d57-c0c8-4603-806f-7787c406e18f" />

4. Data Encapsulation

         Process:
         Encapsulation: Data > Segment > Packet > Frame > Bits
         De-encapsulation: Bits > Frame > Packet > Segment > Data
         Protocol Data Units (PDUs) - Include Data, Segment, Packet, Frame, Bits

5. Data Access

         Layer 3 (Network Layer) - Uses IP addressing and routing packets into different networks.
         Layer 2 (Data Link layer) - Uses MAC addressing for local delivery.
         Local vs Remote Networks - Local: Devices share a network portion of their IP address.
                                  - Remote: Devices rely on routers and gateways for communication.

6. Standards Organizations

         Open Standards - Promote interoperability, competition, and innovation.
                        - Organizations inlcude ISOC, IAB, IETF, IRTF.
                        - ICANN Manage IP allocation and domain names.
                        - IEEE, EIA, TIA, ITU-T develop various standards.



   
   
