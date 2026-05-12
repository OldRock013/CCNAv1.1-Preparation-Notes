# ACLs for IPv4 Configuration

### 1. Configure Standard IPv4 ACLs
    a. Planning and Documentation
       - Use a tect esitor to write the ACL policy
       - inlcude remarks to explain the purpose of each ACE
       - Test the AC: throroughly before deployment
    b. Numbered Standard ACLs
       Syntax:
       access-list <1-99 | 1300-1999> {deny | permit} <source> <wildcard>
       Parameters:
       - access-list number: ACL identifier
       - deny / permit: Specifies the action
       - source: Address to filter
       - source-wildcard: Wildcard mask.
       Example:
       Permit 192.161.1.1:
       acccess-list 10 permit 192.168.1.1 0.0.0.0
       Removal: no access-list <number>
    c. Named Standard ACLs
       Syntax: 
       ip access-list standard <name>
       Advantages: Unique, descriptove names for easier management.
       Example:
       ip access-list standard PERMIT-SUBNET
       permit 192.168.1.0 0.0.0.255
    d. Applying Standard ACLs
       - Use "ip access-group" to bind ACL to an interface.
       Example
       interface g0/0
       ip address-group 10 in
### 2. Modify IPv4 ACLs
    a. Methods
       Text Editor: Copy ACL to a text editor, edit and reapply.
       Sequence Numbers: Edit individual ACEs with sequence numbers.
       Example:
       Remove ACE:
       no 10
       Add updated ACE:
       10 permit 192.168.2.0 0.0.0.255ad
    b. Verification
      Use show access-lists for statistics.
      Clear counters with clear access-list counters.
### 3. Secure VTY Ports with Standard ACLs
    a. Configure
       - Use "access-class" for restricting VTY access
       Permit only 192.168.10.10 for SSH:
       access-list 10 permit 192.168.10.10
       line vty 0 4
       access-class 10 in
### 4. Configure Extended IPv4 ACLs
    a. Features
          Filters traffic by:
          Source/Destination addresses.
          Protocols (IP, TCP, UDP)
          Port numbers
    b. Types:
          Numbered:
          access-list <100-199 | 2000-2699> {deny|permit} <protocol> <source> <destination> <port>
           Named:
           ip access-list extended <name>
           Block Telnet:
           ip access-list extended BLOCK-TELNET
           deny tcp any any eq 23
    c. TCP Established: Allows statful inspection for retuning traffic.
       Example:
       Permit established web sessions:
       access-list 110 permit tcp any any established
    d. Placement:
       Apply close to the source for efficiency.
       Example:
       interface G0/1
       ip access-group 110 in
