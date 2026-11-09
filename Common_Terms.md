# A
## Automatic Private IP Addressing (APIPA) 
Networking feature that allows a device to self-assign an IPv4 address when it cannot reach a DHCP (Dynamic Host Configuration Protocol) server.

• IP Address Range: 169.254.0.1 to 169.254.255.254 (designated by IANA for link-local use).
• Subnet Mask: 255.255.0.0 (/16).
• Default Gateway: 0.0.0.0 (non-routable).




## Address Resolution Protocol (ARP)
Network communication protocol used to map an IPv4 address to a physical MAC (Media Access Control) address on a local area network (LAN)





# D 
## Dynamic Host Configuration Protocol (DHCP)
DHCP is the protocol that automatically assigns ip addresses on a network. 
- Usually the dhcp sercer runs on the router, which is resposible for assigning each device a ip address. 
**DORA**
1. Discover: The client broadcasts a message (DHCPDISCOVER) across the network to find any available DHCP server.
2. Offer: The DHCP server responds with an offer (DHCPOFFER) containing an available IP address, subnet mask, default gateway, DNS server, and lease duration.
3. Request: The client replies with a request (DHCPREQUEST) to formally accept the offered IP address.
4. Acknowledge: The server sends a final confirmation (DHCPACK), officially assigning the IP and parameters to the client

If DORA fails, the client gives itself an APIPA address (169.254.x.x). Also, in businesses the DHCP server is often a dedicated server rather than the router.


# I 
## Inter-process communication (IPC)
## IEEE 
Institute of Electrical and Electronics Engineers

## IEEE WIFI GENERATIONS

## IEEE WIFI GENERATIONS

### 802.11
Original (no Wi-Fi number)
Released in 1997, operating at 2.4 GHz with raw data rates up to 2 Mbps

### 802.11b
Wi-Fi 1
Released in 1999, operating at 2.4 GHz with speeds up to 11 Mbps

### 802.11a
Wi-Fi 2
Released in 1999, operating at 5 GHz with speeds up to 54 Mbps

### 802.11g
Wi-Fi 3
Introduced in 2003, operating at 2.4 GHz with speeds up to 54 Mbps

### 802.11n
Wi-Fi 4
Introduced in 2009. Introduced MIMO (multiple-input and multiple-output) antenna technology and reached speeds up to 600 Mbps across 2.4 GHz and 5 GHz bands

### 802.11ac
Wi-Fi 5
Introduced in 2013, operating in the 5 GHz band only, with wider 80 MHz/160 MHz channels, MU-MIMO (downlink), and multi-gigabit speeds up to 3.5 Gbps+

### 802.11ax
Wi-Fi 6 & 6E
Introduced in 2019, operating at 2.4 GHz and 5 GHz (6E adds the 6 GHz band). Added OFDMA (Orthogonal Frequency-Division Multiple Access) and MU-MIMO for dense public areas, with speeds up to 9.6 Gbps

### 802.11be
Wi-Fi 7
Ratified via IEEE Std 802.11be-2024, operating at 2.4, 5, and 6 GHz. Introduced 320 MHz channels, Multi-Link Operation (MLO), and data rates up to about 46 Gbps

**Memory hook:** b and g = 2.4 GHz, a and ac = 5 GHz, n and ax = both bands









## 802.1Q
Industry-standard networking protocol that allows multiple Virtual Local Area Networks (VLANs) to share the same physical Ethernet link


Frame Tagging: When a data frame crosses a trunk port between switches, IEEE 802.1Q inserts a 4-byte (32-bit) tag right after the source MAC address. This alters the standard Ethernet frame size and requires a recomputation of the Frame Check Sequence (FCS)


Tag Breakdown: The 4-byte tag contains:• TPID (16 bits): Tag Protocol Identifier, fixed at 0x8100 to show the frame is 802.1Q-tagged.
• PCP (3 bits): Priority Code Point (IEEE 802.1p), used for Quality of Service (QoS) traffic prioritization (values 0–7).
• DEI (1 bit): Drop Eligible Indicator (formerly CFI), used to indicate frames that can be dropped during congestion.
• VID (12 bits): VLAN Identifier, supporting 4,096 unique VLANs (IDs 1–4094 usable, while 0 and 4095 are reserved).
### Native VLAN
- The one VLAN whose frames cross a trunk untagged (VLAN 1 by default)
- Untagged frames arriving on a trunk are placed in the native VLAN
- Both ends of the trunk must match, or you get a native VLAN mismatch
- Security: change it from VLAN 1 to prevent VLAN hopping (double tagging)

# N
## Network Address Translation (NAT) 
- The process in which a router translates a  an IP address from a private network to the public internet 

Local Ip -> Gateway -> Public Internet 
Public Internet -> Gateway -> Local IP 


### Main Types of NAT
• Static NAT: Creates a permanent, one-to-one mapping between a single private IP address and a dedicated public IP address (commonly used for public-facing web or mail servers).
• Dynamic NAT: Maps private IP addresses to a temporary pool of public IP addresses on a first-come, first-served basis.
• Port Address Translation (PAT / NAT Overload): Allows hundreds or thousands of private devices to share one single public IP address by assigning unique source port numbers to each connection. This is the most common type used in home and small office routers.
• Carrier-Grade NAT (CGNAT): Implemented by an Internet Service Provider (ISP) to share a pool of public IP addresses across multiple residential customers.

### DNS VS NAT
1. DNS (The Phonebook): You type a URL (like google.com). Your device queries a DNS server to look up the phone number. The DNS server replies: "The IP address for google.com is 142.250.190.46."
2. NAT (The Border Control): Your device now tries to send data to that IP address. The data hits your router (Gateway). Because your device has a private IP address, the router uses NAT to swap it for your public IP address before pushing the data out to the internet.

# P 
## PAT (Port Address Translation
aka **NAT Overload** 
An example from Google Gemini 
As a regular user, your ISP provides you with exactly one public IP address. To get all your phones, laptops, and smart TVs online simultaneously, your router uses ports (digital extension numbers).
Using the apartment mailroom analogy, PAT works like this:
• Your Phone visits a site → Router labels it: Public IP + Extension 5001
• Your Laptop visits a site → Router labels it: Public IP + Extension 5002

# R

## Remote Authentication Dial-In User Service 

Networking protocol that provides centralized AAA 
- Authentication 
- Authorization 
- Accounting 
management for users connecting to a network service
### How it Works 
• Authentication: Verifies a user or device's identity against a central database (such as Active Directory or LDAP).
• Authorization: Determines what network services, VLANs, or permissions the authenticated user is allowed to access.
• Accounting: Tracks session usage metrics—such as login time, data packets, and bandwidth—for monitoring, auditing, and billing.



# S

## SFTP (SSH File Transfer Protocol)secure network protocol used to access, transfer, and manage files over a single encrypted connection 

## Secure Copy Protocol (SCP) 

a network protocol used to securely transfer files between a local host and a remote host, or between two remote hosts



## SIMPLE NETWORK MANAGEMENT PROTOCOL (SNMP) 

**Application-layer** networking protocol used to: 
- monitor, 
- configure, 
- manage 
IP network devices such as routers, switches, servers, and printers
Runs over UDP 
Port 161 for queries and 162 for alerts 

## SERVER MESSAGE BLOCK (SMB) 
**Server Message Block** 
**Application Layer** network communication protocol used to provide shared access to
- files 
- printers 
- serial ports
- inter-process communications across a network 


## SPANNING TREE PROTOCOL (STP) 
- Protocol used to prevent data from looping between ethernet networks
- If there is redundency in the network, data frames will loop continuiously between networks and can potentially crash the networks. 
**CAN CAUSE** 
• Broadcast storms that flood the network
• High CPU utilization on switches
• MAC address table instability
**STP** *solves this* by placing **redundant ports** into a **blocking** **(standby)** state, creating a:
- loop-free, 
- logical tree topology 
while keeping backup paths ready in case a main link fails
### Example: The Three-Switch Triangle
        Core Switch 
         /        \
        /          \
  (Active)       (Active)
      /              \
     /                \
    Sales  ---X---  HR 
         (Blocking)
### The Connections:
• Core Switch connects to Sales Switch.
• Core Switch connects to HR Switch.
• Sales Switch connects to HR Switch.
 The **Problem**: Broadcast traffic sent from Sales could go to HR, then up to the Core, and back down to Sales forever.
**How STP Acts**: STP will detect the loop and select one link to block—for example, the link between Sales and HR.
**The Result**: The port connecting Sales to HR is placed in a blocking (standby) state. If the Core Switch dies or a cable to the Core snaps

# V
## Virtual Local Area Network (Vlan)

VLAN is achieved directly on a network switch. 
Logical subnetwork that splits a single physical network or switch into multiple independent broadcast domains at Layer 2

Isolation: Devices in the same VLAN communicate directly as if they are plugged into the same physical switch. Devices in different VLANs cannot talk to each other directly
Trunk Links: A single physical cable (trunk port) can carry tagged traffic for multiple VLANs between switches or routers\
**Important Note**
VLANs can talk, but only through a router or Layer 3 switch (inter-VLAN routing)

### VID
VLAN ID (VID

