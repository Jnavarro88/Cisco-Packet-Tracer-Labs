Technical Report: EIGRP Enterprise Implementation

📌 Project Overview

The goal of this lab was to implement Enhanced Interior Gateway Routing Protocol (EIGRP) across a multi-router mesh topology. EIGRP was selected for this environment due to its rapid convergence times and its use of the Diffusing Update Algorithm (DUAL) to maintain loop-free paths.

🏗️ Network Architecture

Protocol: EIGRP (Autonomous System 10)

Algorithm: DUAL (Diffusing Update Algorithm)

Metric: Composite (Bandwidth + Delay)

Topology: Multi-router mesh with redundant pathing.

<img width="1136" height="689" alt="Image" src="https://github.com/user-attachments/assets/555cc632-ea6a-44a6-b4a2-8ad7290b8319" />

⚙️ Configuration & Implementation Logic
<br>
Router A

ip dhcp excluded-address 192.168.10.1 192.168.10.10

!

ip dhcp pool Router-A

 network 192.168.10.0 255.255.255.0
 
 default-router 192.168.10.1
 
 dns-server 8.8.8.8
 
!

interface GigabitEthernet0/0

 ip address 10.0.0.1 255.255.255.252
 
 duplex auto
 
 speed auto
 
!

interface GigabitEthernet0/1.1

 encapsulation dot1Q 10
 
 ip address 192.168.10.1 255.255.255.0
 
!

interface Serial0/0/0

 ip address 10.0.0.5 255.255.255.252
 
 clock rate 2000000
 
!

router eigrp 1

 network 10.0.0.0 0.0.0.3
 
 network 192.168.10.0
 
 network 10.0.0.4 0.0.0.3
 
 network 10.0.0.8 0.0.0.3

 <br>

 
