# SWITCHING CONCEPTS

###. 1 Frame Forwarding
      
      a. Ingress: Framce entring the interface.
         Egress: Frame existing the interface
      b. MAC Address Table
         - Switch uses the destination MAC address to determine the egress interface.
         - Builds the MAC address table by recording the source MAC address and the port it was received in,
      c. Learn and Forward Method:
         Step 1: Learn; Adds source MAC to the table if not present. 
                 Resets timeout to 5 minites if source MAC is already in the table.
         Step 2: Forward; Forwards frame if destination MAC is in the table.
                 Floods frame out all interfaces (except ingress) if destination MAC is unknown.
      d. Switch Forwarding Methods:
         Store-and-Forward Switching:
          - Receives the entire frame and checks for errors using Frame Check Sequence (FCS)
          - Buffers the frame to adjust for speed differences between ingress and egress ports.
         Cut-Through Switching - Forwards frame immediately after determining destination MAC address
         Fragment-Free Method: Ensures frame is at least 64 bytes to eliminate runts.
           Characteristics:
           - Low Latency (under 19 microseconds)
           - does not check FCS, may propagate errors.
           - Cannot support differing port speeds.
  ### 2. Switching Domains

      a. Collision Domains:
           - Eliminated in full-duplex links.
           - Present in Half-duplex links, causing contention for bandwidth and possible collisions.
           - Auto-negotiation is the default setting for duplex and speed in most devices.
      b. Broadcast Domains:
           - Extecds across all layer 1 or Layer 2 devices on a LAN
           - Broken by Layer 3 devices (e.g Routers)
           - Broadcast traffic is flooded to all interfaces except the ingress interface.
           - Too many broadcasts can cause congestion and poor performance.
           - Expands with the addition of Layer 1 or Layer 2
      c. Alleviating Network Congestion
           - Fast Port Speed: Up to 100 Gbps depending on the switch model.
           - Fast Internal Switching: Uses fast internnal bus or shared memory
           - Large Frame Buffers: Temporarily stores frams during processing.
           - High Port Density: Provides more ports for devices, reducing local traffic congestion.
### Key learnings:

Ingress is the entry port; egress is the exit port.

Switch builds a MAC address table to forward frames.

Forwarding methods: Store-and-Forward and Cut-Through.

Collision domains exist in half-duplex; full-duplex eliminates them.

Broadcast domains are extended by switches but can be broken by routers.

Switches alleviate congestion by eliminating collisions and using features like fast port speeds and high port density.
