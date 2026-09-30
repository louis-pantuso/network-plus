# 1.1 OSI model 


**Date** : 09/29/26
**Source** : https://www.professormesser.com/network-plus/n10-009/n10-009-video/understanding-the-osi-model-n10-009/
**Objective** Explore and explain the OSI model




*O*pen 
*S*ystems 
*I*nterconnection Reference Model


**ALl People Seem to Need Data Processing** 

| Layer   | Layer Name   | 
|---------|--------------|
| Layer 7 | Application  | your eyes 
| Layer 6 | Presentation | (ssl/tsl)
| Layer 5 | Session      | Control protocols 
| Layer 4 | Transport    | TCP/UDP
| Layer 3 | Network      | IP, MAC Address
| Layer 2 | Data         | ethernet frames. EUI , switch
| Layer 1 | Physical     | cables, fibers etc 


- Layer 1 
    - The Physical Level. 
    - Signals over protocols at this level

- Layer 2 
    - Datalink layer 
    - Media Access Control( MAC ) Layer
    - NIC sends frames through either the wire or air via radio waves 

    frame
    : A frame is the unit of data used at the data link layer (Layer 2). It is what a switch or network card actually sends on a local link (Ethernet, Wi-Fi, etc.).

- Layer 3 Routing Layer 

    - The layer the router uses 
    - Ip addresses get introduced on this level 
    - Anything related to ip or routing is this 

- Layer 4  Transport 
    
    - Post office layer, responsible for _transporting_ data 
    - transmission control protocol 
    - user datagran protocol  

- Layer 5 Session 
    - Communication management 
        - start, stop , restart 
    - Control Protocols 



- Layer 6 Presentation
    - Character Encoding 
    - Application Encrption 
    - Often associated with layer 7 


- Layer 7 Applicaiton layer 
    
    - What we see 
    - Common Applications 
        - Common Applications 
           1. Http 
           2. ftp 
           3. dns 
           4. pop3
            and many more 

