# ACL Concepts

### 1. Purpose of ACLs
    a. What is ACL?
      - Series of IOS commands use to filter packets based on the header.
      - Contains sequential permit or deny statements known as Access Control Entries (ACEs).
      - Default Behaviour: No ACLs configured on routers.
      - Implicit deny rule at the end of every ACL discards unmatched packets.
      Funtions of ACLs:
       - Limit network traffic to improve performance.
       - Provide traffic flow control
       - Enhance basic network security
       - Filter traffic based on type
       - Screen hosts for access to services.
    b. Packet Filtering
       - Controls access to the network by analyzing packet headers
       - Forward or discard packets based on defined criteria.
       - Operates at Layer 3 (IP) and Later 4 (TCP/UDP)
       Types:
       Standard ACLs: Filter only by source IPv4 address.
       Extended ACLs: Filter by source/destination IPv4 address, protocol type, and Layer 4 port information.
    c. ACL Operation
       - Defines rules for packets entering or leaving interfaces.
       - Can be applied to:
         - Inbound traffic: Filters berfore routing, reducing unnecessary routing overhead.
         - Outbound traffic: Filters after routing is complete.
       - Operational Steps (Inbound Stardard IPv4 ACL)
         1. Router extracts the source IPv4 address.
         2. Compares the address to each ACE in sequential order.
         3. Permits or denies the packet on the first match.
         4. Discards packets if no match (implicit deny)
       - Must include at least one permit statement to avoid blocking all traff
### 2. Wildcard Masks in ACLs
    a. Overview
       - Wildcard masks determine which bits in an addressa are matched or ignored.
       - Opposite logic of subnet masks:
         0: Match the corresponding bit
         1: Ignore the corresponding bit
       - Used in ACEs for packet matching.
    b. Examples:
       0.0.0.0: Match all bits (specific host).
       0.0.0.255: Match first three octets, ignore the fourth (specific subnet).
       0.0.15.255: Match ranges of subnets.
    c. Calculation:
       Subtract the subnet mask from 255.255.255.255 to derive the wildcard mask.
       Shortcut for common masks:
       /24 → 0.0.0.255
       /28 → 0.0.0.15
    d. Keywords:
       host: Matches a single address (0.0.0.0).
       any: Matches all addresses (255.255.255.255).
### 3. Guidelines for ACL Creation
    a. Limits:
       IPv4 and IPv6: One inbound and one outbound ACL per interface.
    b. Best Practices
       1. Base ACLs on the organization's Security polocies
       2. Write and plan ACLs in a text editor before implementation.
       3. Document ACLs using "remark"command for clarity.
       4. Test ACLs in a development environment to avoid costly mistakes.
### 4. Types of IPv4 ACLs
    a. Standard vs. Extended
       Standard
       - Filters by source IPv4 address only.
       - Simpler and less resource-intensive.
       Extended
       - Filters by source and destination IPv4 addresses, protocol types, and port numbers
       - Provides finer control
    b. Numbered vs. Named
       Numbered ACLs: Standard 1-99, 1300-1999
       Named ACLs: Easier to understand and manage. Created with the ip access-list command.
    c. Placement
       Standard ACLs: Place as close to the destination as possible.
       Extended ACLs: Place as close to the source as possible to avoid unwanted traffic crossing the network.
