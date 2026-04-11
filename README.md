Cisco Networking Labs - OSPF Multi-Area Technical Report

🏗️ Topology & Design

This lab features a 6-router OSPF backbone. The goal was to achieve full reachability across Area 0 while maintaining a hierarchical network design.

1. OSPF Multi-Area Configuration

This lab demonstrates a 6-router topology using OSPF to share routing information across different areas.

<img width="792" height="717" alt="Image" src="https://github.com/user-attachments/assets/8ba2ba9d-bd99-4c36-a998-804153984f39" />


Key Configuration (Router 1)

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
 

<br>
Key Configuration (Router 2)

ip dhcp excluded-address 192.168.11.1 192.168.11.20

!

ip dhcp pool NETWORK-2

 network 192.168.11.0 255.255.255.0
 
 default-router 192.168.11.1
 
 dns-server 8.8.8.8
 
!

interface GigabitEthernet0/0.20

 encapsulation dot1Q 20
 
 ip address 192.168.11.1 255.255.255.0
 
!

interface Serial0/3/0

 ip address 10.0.0.10 255.255.255.252
 
 clock rate 2000000
 
!

interface Serial0/3/1

 ip address 10.0.0.13 255.255.255.252
 
 clock rate 2000000
 
!

router ospf 1

 log-adjacency-changes
 
 network 10.0.0.8 0.0.0.3 area 0
 
 network 192.168.11.0 0.0.0.255 area 0
 
 network 10.0.0.12 0.0.0.3 area 0

 <br>
Key Configuration (Router 3)

ip dhcp excluded-address 192.168.12.1 192.168.12.20

!

ip dhcp pool NETWORK-3

 network 192.168.12.0 255.255.255.0
 
 default-router 192.168.12.1
 
 dns-server 8.8.8.8
 
!

interface GigabitEthernet0/0.30

 encapsulation dot1Q 30
 
 ip address 192.168.12.1 255.255.255.0
 
!

interface Serial0/3/0

 ip address 10.0.0.18 255.255.255.252
 
 clock rate 2000000
 
!

interface Serial0/3/1

 ip address 10.0.0.21 255.255.255.252

!

router ospf 1

 log-adjacency-changes
 
 network 10.0.0.16 0.0.0.3 area 0
 
 network 192.168.12.0 0.0.0.255 area 0
 
 network 10.0.0.20 0.0.0.3 area 0

 <br>
Key Configuration (Router 4)

interface Serial0/0/0

 ip address 10.0.0.30 255.255.255.252
 
 clock rate 2000000
 
!

interface Serial0/2/0

 ip address 10.0.0.17 255.255.255.252
 
!

interface Serial0/3/0

 ip address 10.0.0.2 255.255.255.252
 
!

interface Serial0/3/1

 ip address 10.0.0.9 255.255.255.252
 
!

router ospf 1

 log-adjacency-changes
 
 network 10.0.0.0 0.0.0.3 area 0
 
 network 10.0.0.8 0.0.0.3 area 0
 
 network 10.0.0.16 0.0.0.3 area 0
 
 network 10.0.0.28 0.0.0.3 area 0

 <br>
Key Configuration (Router 5)

interface Serial0/0/0

 ip address 10.0.0.6 255.255.255.252
 
!

interface Serial0/0/1

 ip address 10.0.0.14 255.255.255.252
 
!

interface Serial0/1/0

 ip address 10.0.0.22 255.255.255.252
 
 clock rate 2000000
 
!

interface Serial0/1/1

 ip address 10.0.0.25 255.255.255.252
 
 clock rate 2000000
 
!

router ospf 1

 log-adjacency-changes
 
 network 10.0.0.4 0.0.0.3 area 0
 
 network 10.0.0.12 0.0.0.3 area 0
 
 network 10.0.0.20 0.0.0.3 area 0
 
 network 10.0.0.24 0.0.0.3 area 0

<br>
Key Configuration (Router 6)

interface Serial0/0/1

 ip address 10.0.0.29 255.255.255.252
 
!

interface Serial0/1/0

 ip address 10.0.0.26 255.255.255.252
 
!

router ospf 1

 network 10.0.0.24 0.0.0.3 area 0
 
 network 10.0.0.28 0.0.0.3 area 0

<br>
Validation:


 <img width="878" height="889" alt="Image" src="https://github.com/user-attachments/assets/35d72e7d-fa4d-4072-9604-453e75983305" />

 
<img width="828" height="749" alt="Image" src="https://github.com/user-attachments/assets/9644165d-01e9-4f64-8193-3d32356d5b5f" />
