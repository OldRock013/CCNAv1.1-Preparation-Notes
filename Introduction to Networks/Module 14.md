# TRANSPORT LAYER

### 1. Transportation of Data

  Responsible for logical Communications betwen applications running on different hosts. Links the application layer with lower network layers.

    a. Responsibilities:
       Tracking individual conversations.
       Segmenting data and reassembling segments.
       Adding header information.
       Identifying, separating and managing multiple conversations.
       Using segmentation and multiplexing to interleave communication.

    b. Transport Layer Protocols:
       Specifies how to transfer messages and manage reliability.
       TCP and UDP primary protocols.

    c. Transmission Control Protocol:
       Provides reliability and flow control.
       Tracks data segments, acknowledges received data, retransmits unacknowledged data, sequences out-of-order data, and adjust transmission rates.

    d. User Datagram Protocol (UDP)
       Basic functions with minimal overhead.
       Connectionless protocol with best-effort delivery.
       No acknowledgedment or retransmission.

    e. TCP: Criticak for ordered, reliable data transmission.
       UDP: Ideal for minimal data or quick retransmissions.

### 2. TCP Overview

    a. Features:
       Establishes ressions with a connection-oriented approach.
       Ensures reliable delivery despite network issues.
       Provides same-order delivery for applications requiring sequence integrity.
       Supports flow control to manange data rate.
    b. Header:
       Includes essential fields for reliability:
       Source port - identifies sending port
       Destination port - identifies receiving port.
       Sequence Number - ensures data is delivered reliably and in the correct order.
       Acknowledgedment Number - acknowledgeds receipt of all prior bytes.
       Header length
       Control bits
       Window Size
       Checksum
       Urgent Pointer

  <img width="1071" height="462" alt="image" src="https://github.com/user-attachments/assets/9a1af148-b0c6-4da4-8f8c-d1b5948d3a9b" />
      
      c. Applications: ensures reliabile data streaming, essential for services requiring consistent dataflow.
  
### 3. UDP Overview

    a. Features:
       Reconstructs data in received order.
       No retransmission for lost segments.
       No session establishment or acknowledgedments

    b. Header:
       Source Port
       Destination Port
       Length
       Checksum
  <img width="1118" height="447" alt="image" src="https://github.com/user-attachments/assets/5eef20e1-658d-49d8-867e-3a3538fadc34" />

    c. Applications: VoIP, Streaming, DNS, DHCP, and other time-sensitive operations.

### 4. Port Numbers

    a. Purpose: Enables multiple simultaneous communications.
    b. Socket Pairs: Combines source and destination IP addresses with port numbers.
    c. Port Groups:
       Well-known ports (0 - 1023): Reserved for common services.
       Registered Ports (1024 - 49151): Assigned by IANA for specific applications.
       Private/Dynamic Ports (49152 - 65535): Assigned dynamically by the OS.
   
### 5. TCP Communication Process

    1. Server Processes: Applications configured with unique port numbers.
    2. Connection Establishment: Three-way handshake
      a. SYN: Request to connect
      b. SYN-ACK: Acknowledgement request
      c. ACK: Confirm connection
    3. Session Termination: Four-step FIN-ACK exchange
    4. Control Flags: URG, ACK, PSH, RST, SYN, FIN: COntrol session beheaviors.
    5 Three-Way handshake analysis: Confirms destination availability, active services, and readiness to establish a session.

### 6. Reliability and Flow Control

    a. Reliability: 
       Sequence numbers for ordered data delivery.
       Retransmission for lost segments.
       SACK: Acknowledges received bytes selectively.
    b. Flow Control:
       Window size management
       Congestion avoidance with timers and algorithms.
       Maximum Segment Size: Typically 1460 bytes (1500 MTU minus headers)

### 7. UDP Communication

    a. Efficiency: Low overhead with fast transmission.
    b. Reassembly: No Sequence trancking: reassembles in received order.
    c. Server Processes: Assigned well-known or registered ports.
    d. Client processes: Dynamically assigns source ports.
       
