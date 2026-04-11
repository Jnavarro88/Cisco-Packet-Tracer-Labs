Cisco Networking Labs - Routing Protocols

This repository contains my CCNA-level routing labs focusing on dynamic route propagation and multi-router connectivity.

1. OSPF Multi-Area Configuration

This lab demonstrates a 6-router topology using OSPF to share routing information across different areas.

<img width="1136" height="689" alt="Image" src="https://github.com/user-attachments/assets/80e0f83d-b812-4ea1-baa0-410daa11bbb9" />

Key Configuration (Router 1)

!
!
ip dhcp excluded-address 192.168.10.1 192.168.10.20
!
ip dhcp pool NETWORK-1
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 8.8.8.8
!
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
!
interface Serial0/3/0
 ip address 10.0.0.1 255.255.255.252
 clock rate 2000000
!
interface Serial0/3/1
 ip address 10.0.0.5 255.255.255.252
 clock rate 2000000
!
router ospf 1
 log-adjacency-changes
 network 10.0.0.0 0.0.0.3 area 0
 network 192.168.10.0 0.0.0.255 area 0
 network 10.0.0.4 0.0.0.3 area 0
!
Key Configuration (Router 2)
Key Configuration (Router 3)
Key Configuration (Router 4)
Key Configuration (Router 5)
Key Configuration (Router 6)


