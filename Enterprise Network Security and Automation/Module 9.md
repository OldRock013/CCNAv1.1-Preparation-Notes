# QoS Concepts

### 1. Network Transmission Quality
    a. Why QoS?
       - Prioritizes critical traffic during congestion.
       - Improves delivery quality for real-time applications like voice and video.
    a. Key Factors
       Bandwidth: Available data transfer capacity.
       Congestion: Traffic exceeding link capacity
       Delay (latency): Fixed Delay: Serialization, packetization
                      : Variable Delay: Queuing, propagation
       Jitter: Varation in delay, critical for voice/video.
       Packet Loss: Resolts in degraded quality, especially for real-time traffic.
### 2. Traffic Characteristics
    a. Voice Traffic: Smooth and predictable.
                    : Requires low latency (<150ms), jitter (<30ms), and packet loss (<1%)
                    : Bandwidth: 30-128 Kbps
    b. Video Traffic: Bursty and bandwidth-heavy.
                    : Requires low latency (<400ms) and jitter (<50ms).
                    : Bandwidth: 384 Kbps to 20 Mbps.
    c. Data Traffic : Rolerant to delays and loss
                    : Characteristics vary by application (e.g. FTP vs. real-time apps)
### 3. Queuing Algorithms
    a. First-In, First-Out (FIFO): No prioritization; Processes packets in arrival order.
    b. Weighted Fair Queuing (WFQ): Automatically classifies and prioritizes flows.
                                  : Not supported with encrypted tunnels.
    c. Class-Based Weighted Fair Queuing (CBWFQ): User-defined classes with guaranteed bandwidth.
                                                : Handles congestion using policies like tail drop.
    d. Low Latency Queuing (LLQ): Adds strict priority for delay-sensitice traffic (e.g., voice)
                                : Prevents starvation of other queues
### 4. QoS Models
    a .Best-Effort: Default model: no guarantees.
                                 : Scalable but unreliable.
    b. Integrated Services (IntServ): Ensures end-to-end QoS via resource reservation (e.g, RSVP)
                                    : Resources-intensive; limited scalability.
    c. Differentiated Services (DiffServ): Traffic classified into classes with specific QoS policies.
                                         : Scalable; applied on a hop-by-hop basis
### 5. QoS Implementation Techniques
    a. Classification and Marking: Identifies traffic classes using ACLs, interfaces, or NBAR.
       Marks traffic using: Layer 2 (CoS, MPLS EXP)
                          : Layer 3 (DSCP, IP Precedence)
    b. Congestion Avoidance: Techniques like WRED drop low-priority traffic before congestion worsens.
    c. Shaping and Policing: Shaping: Smooths outbound traffic by queuing excess packets.
                             Policing: Enforces inbound traffic limits.
    d. Trust Boundaries: Classify and mark traffic close to its source for efficient QoS application
