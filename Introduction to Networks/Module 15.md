# APPLICATION LAYER

### 1. Application, Presentation, and Session

    a. Application Layer:
       Defines the functions for communication between applications.
       Provides an interface between the applications and the underlying network.
       Widely used protocols: HTTP, FTP, TFTP, IMAP, DNS

    b. Presentation Layer:
       Formats data for compatibility between source and destination devices.
       Compresses data for transmission and decompresses it upon receipt.
       Encrypts data for secure communication and decrypts it at the destination.

    c. Session Layer:
       Creates and Maintains dialogs between source and destination applications.
       Handles the initiation, maintenance, and restarting of sessions.

### 2. Peer-to-Peer
    
    a. Client-Server Model:
       Applications use a client-serer model where:
         - Client requests information.
         - Server responds with the requested information.
     b. Peer-to-Peer (P2P) Networks:
        Two or more computers share resources without a dedicated server.
        End devices function as both client and server.
     c. P2P Applications:
        Allows devuces to act as both client and server within a single communication.
        Common applications: Hybrid P2P with index servers for resource location.
        Examples: BitTorrent, Direct Connect, eDonkey, Freenet.

### 3. Web and Email Protocols

     a. HTTP and HTTPS:
        HTTPS is request-response protocol for data exchange (GET, POST, PUT). HTTPS is secured version of HTTP for encrypted communication.
     b. How HTTP works:
        - Browser interprets the URL (protocol, server name, file path).
        - Converts server name to an IP address using DNS.
        - Sends a GET request to the server for the specified file.
        - Server responds with the HTML code.
        - Browser renders the HTML code for the user.
      c. Email Protocols:
        - SMTP (Simple Mail Transfer Protocol)
          *Sends email messages
          *Uses pot 25 for client-server communication.
          *Stores and forwards messages if destination servers are unavailable.
        - POP (Post Office Protocol)
          *Retrieves and deletes messages from the server after download.
          *Uses port 110 and listens for client requests.
        - IMAP (Internet Message Access Protocol)
          *Synchronizes messages with the server.
          *Messages remain on the server unless manually deleted.
### 4. IP addressing Services
      a. DNS (Dynamic Name System)
        - Convets human-readable domain names to IP address
      b. The nslookup Command:
        - Manual too to query DNS servers for resolving hostnames or troubleshooting.
      c. DHCP (Dynamic Host Control Protocol)
        - Automates IP address assignments, subnet masks, and gateways.
        - Dynamic addressing for general-purpose hosts; static for critical devices.
         Operation Process:
         1. Client sends a DHCPDISCOVER broadcast.
         2. Server replies with a DHCPOFFER message
         3. Client responds with DHCPREQUEST to accept the offer.
         4. Server sends DHCPACK to finalize the lease.
### 5. File Sharing Services
      a. File Transfer Protocol (FTP)
         Enables data transfer between client and server.
         Steps:
           1. Control traffic on TCP port 21 for cpmmands and replies
           2. Data transfer on TCP port 20 for actual files.
           3. Supports upload (push) and download (pull)
      b. SMB (Server Message Block)
         File sharing protocol for client-server communication.
         Functions:
           1. Start, Authenticate and terminante sessions.
           2. Control Access to files and printers.
           3. Enable application to exchange messages
         Establishes persistent connections, allowing seamless access to server resources.
    

Application layer protocols support data exchange between programs.

Presentation layer formats, compresses, and encrypts data.

Session layer maintains dialogs between applications.

P2P networks enable direct resource sharing without servers.

HTTP/HTTPS manage web communications, while SMTP, POP, and IMAP handle emails.

DNS resolves names to IPs, and DHCP automates addressing.

FTP and SMB facilitate file sharing with different levels of persistence.
