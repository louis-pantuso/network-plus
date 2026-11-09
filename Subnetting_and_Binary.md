# Subnetting

A comprehensive sheet all about subnetting. 


## What is a bit 
A **bit** is the smallest unit of data a computer can process 
A **Byte** is 8 bits 

An Ip Address is 32 bits or 4 bytes 



## IP addresses 


Class A: 
    1.0.0.0 - 126.255.255.255 
Class B: 
    128.0.0.0 - 191.255.255.255 
Class C: 
    192.0.0.0 - 223.255.255.255

** Special Mentions ** 

Class D (224–239, multicast) 
Class E (240–255, experimental)

Private Ranges 
 Loopback
   172.16.0.0/12,
   192.168.0.0/16
   127.0.0.0/8
 APIPA
   169.254.0.0/16 

## Binary Math 

1 means true 
0 means false 

| _  | _  | _  | _  | _ | _ | _ | _ |
| 128| 64 | 32 | 16 | 8 | 4 | 2 | 1 |

When looking at an octet, say 192 for example, 
We can Write it like this. 

| **1**  | **1**  | 0  | 0  | 0 | 0 | 0 | 0 |
| 128| 64 | 32 | 16 | 8 | 4 | 2 | 1 |

**192.168.0.1** can be written like:
**11000000.10101000.00000000.00000001**

## CIDR NOTATION | HOST | NETWORK BLOCKS
| CIDR  | Binary                              | Network Block | Host   |   
|-------|-------------------------------------|---------------|--------|
| /8    |  11111111.00000000.00000000.00000000|16777216       |16777214|
| /9    |  11111111.10000000.00000000.00000000|8388608        |8388608 |
| /10   |  11111111.11000000.00000000.00000000|4194304        |4194302 |
| /11   |  11111111.11100000.00000000.00000000|2097152        |2097150 | 
| /12   |  11111111.11110000.00000000.00000000|1048576        |1048574 | 
| /13   |  11111111.11111000.00000000.00000000|524288         | 524286 |
| /14   |  11111111.11111100.00000000.00000000|262144         | 262142 | 
| /15   |  11111111.11111110.00000000.00000000|131072         | 131070 | 
| /16   |  11111111.11111111.00000000.00000000|65536          | 65534  | 
| /17   |  11111111.11111111.10000000.00000000|32768          | 32766  |
| /18   |  11111111.11111111.11000000.00000000|16384          | 16382  |
| /19   |  11111111.11111111.11100000.00000000|8192           | 8190   |
| /20   |  11111111.11111111.11110000.00000000|4096           | 4094   |
| /21   |  11111111.11111111.11111000.00000000|2048           | 2046   |
| /22   |  11111111.11111111.11111100.00000000|1024           | 1022   |
| /23   |  11111111.11111111.11111110.00000000|512            | 510    |
| /24   |  11111111.11111111.11111111.00000000|256            | 254    |
| /25   |  11111111.11111111.11111111.10000000|128            | 126    |
| /26   |  11111111.11111111.11111111.11000000| 64            | 62     |
| /27   |  11111111.11111111.11111111.11100000| 32            | 30     |
| /28   |  11111111.11111111.11111111.11110000| 16            | 14     |
| /29   |  11111111.11111111.11111111.11111000|  8            | 6      |
| /30   |  11111111.11111111.11111111.11111100|  4            | 2      | 
| /31   |  11111111.11111111.11111111.11111110|  2            | 2      |    
| /32   |  11111111.11111111.11111111.11111111|  0            | 1      |

To find how many networks are avaliable: 
2 ^ subnetbits 

To find how many hosts are on a network 
(2 ^ Host bits) - 2


Each subnet neets a **Network ID** and a **BroadCast ID**


# Seven Second Subnetting (Magic Number Chart)

| Bits | Mask | Magic # (Block) | 1st Octet | 2nd Octet | 3rd Octet | 4th Octet |
|------|------|-----------------|-----------|-----------|-----------|-----------|
| 1    | 128  | 128             | /1        | /9        | /17       | /25       |
| 2    | 192  | 64              | /2        | /10       | /18       | /26       |
| 3    | 224  | 32              | /3        | /11       | /19       | /27       |
| 4    | 240  | 16              | /4        | /12       | /20       | /28       |
| 5    | 248  | 8               | /5        | /13       | /21       | /29       |
| 6    | 252  | 4               | /6        | /14       | /22       | /30       |
| 7    | 254  | 2               | /7        | /15       | /23       | /31       |
| 8    | 255  | 1               | /8        | /16       | /24       | /32       |

## How to use it
1. Find your CIDR in the chart. Its row gives you the mask and the magic number, and its column tells you which octet is "interesting."
2. Magic number = 256 − mask (for example, 256 − 224 = 32).
3. **Network ID** = the biggest multiple of the magic number at or below your IP's interesting octet.
4. **Broadcast** = next network − 1.
5. **First usable** = network + 1. **Last usable** = broadcast − 1.
6. **Hosts** = (2 ^ host bits) − 2.

## Example: 192.168.20.141/27
- /27 is in the 4th octet column, so the mask is 224 and the magic number is 32.
- Multiples of 32: 0, 32, 64, 96, **128**, 160 → network = .128
- Next network .160 − 1 = broadcast .159
- Usable: .129 – .158 (30 hosts)

