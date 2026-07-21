TalalAliAlshehri

Enterprise Static Routing Network (Cisco Packet Tracer)
Overview

This project demonstrates the design and implementation of a small enterprise network using Cisco Packet Tracer. The network consists of a headquarters (HQ) and two branch offices connected through static routing. The project focuses on IPv4 addressing, router configuration, LAN connectivity, and end-to-end communication between all sites.
Objectives
	•	Design a multi-site enterprise network.
	•	Configure Cisco routers and switches.
	•	Implement IPv4 addressing.
	•	Configure Static Routing.
	•	Verify end-to-end connectivity.
	•	Document the network configuration following networking best practices.
Network Topology
                HQ-R1
               /     \
              /       \
          BR1-R2     BR2-R3
            |            |
         BR1-SW1      BR2-SW1
         /  |  \       /  |  \
       PC2 PC3 PC4   PC5 PC6 PC7
            |
         HQ-SW1
         /    \
       PC0    PC1

       Devices Used
       |Device|Model          |Quantity|
|------|---------------|--------|
|Router|Cisco 2911     |1       |
|Router|Cisco 2901     |2       |
|Switch|Cisco 2960-24TT|3       |
|PC    |Generic PC     |8       |

Network Design
Headquarters (HQ)
	•	Router: HQ-R1
	•	Switch: HQ-SW1
	•	PCs: PC0, PC1
Branch Office 1
	•	Router: BR1-R2
	•	Switch: BR1-SW1
	•	PCs: PC2, PC3, PC4
Branch Office 2
	•	Router: BR2-R3
	•	Switch: BR2-SW1
	•	PCs: PC5, PC6, PC7
IP Addressing Plan
LAN Networks
|Site       |Network        |Subnet Mask  |Gateway                   |
|-----------|---------------|-------------|--------------------------|
|HQ LAN     |192.168.10.0/24|255.255.255.0|192.168.10.1 (HQ-R1 G0/0) |
|Branch1 LAN|192.168.20.0/24|255.255.255.0|192.168.20.1 (BR1-R2 G0/1)|
|Branch2 LAN|192.168.30.0/24|255.255.255.0|192.168.30.1 (BR2-R3 G0/1)|

Point-to-Point Links (WAN)
|Link   |Network     |Subnet Mask    |HQ-R1 Interface |Remote Interface       |
|-------|------------|---------------|----------------|-----------------------|
|R1 ↔ R2|10.0.12.0/30|255.255.255.252|10.0.12.1 (G0/1)|10.0.12.2 (BR1-R2 G0/0)|
|R1 ↔ R3|10.0.13.0/30|255.255.255.252|10.0.13.1 (G0/2)|10.0.13.2 (BR2-R3 G0/0)|

Host Assignments
|Device|Site   |IP Address   |Gateway     |
|------|-------|-------------|------------|
|PC0   |HQ     |192.168.10.10|192.168.10.1|
|PC1   |HQ     |192.168.10.11|192.168.10.1|
|PC2   |Branch1|192.168.20.10|192.168.20.1|
|PC3   |Branch1|192.168.20.11|192.168.20.1|
|PC4   |Branch1|192.168.20.12|192.168.20.1|
|PC5   |Branch2|192.168.30.10|192.168.30.1|
|PC6   |Branch2|192.168.30.11|192.168.30.1|
|PC7   |Branch2|192.168.30.12|192.168.30.1|

Configuration Summary
Routers
	•	Configured hostname.
	•	Assigned IPv4 addresses to all interfaces.
	•	Enabled interfaces using no shutdown.
	•	Configured Static Routes.
	•	Saved configuration using: copy running-config startup-config
Switches
	•	Connected all end devices.
	•	Provided Layer 2 connectivity.
	•	Default VLAN used.
PCs
Each PC was configured with:
	•	IP Address
	•	Subnet Mask
	•	Default Gateway
Connectivity to the local gateway was verified successfully.
Static Routing
Static routes were configured on all three routers to provide communication between:
	•	Headquarters
	•	Branch Office 1
	•	Branch Office 2
Verification command: show ip route
Verification
The following tests were completed successfully:
	•	✅ PC0 → PC2
	•	✅ PC0 → PC5
	•	✅ PC2 → PC5
	•	✅ Local Gateway Ping
	•	✅ Interface Status Verification
	•	✅ Routing Table Verification
Useful verification commands:show ip interface brief
show ip route
ping
traceroute

Project Structure
Enterprise-Static-Routing-Network/
│
├── Enterprise_Static_Routing.pkt
├── README.md
└── screenshots/
    ├── topology.png
    ├── show_ip_route_R1.png
    ├── show_ip_route_R2.png
    ├── show_ip_route_R3.png
    ├── interfaces.png
    ├── ping_tests.png
    └── running_config.png

Skills Demonstrated
	•	Cisco IOS CLI
	•	IPv4 Addressing
	•	Subnetting
	•	Static Routing
	•	LAN Configuration
	•	Router Configuration
	•	Switch Configuration
	•	Network Verification
	•	Network Troubleshooting
	•	Documentation
Future Improvements
	•	VLANs
	•	Inter-VLAN Routing
	•	DHCP
	•	NAT
	•	ACLs
	•	OSPF
	•	EtherChannel
	•	STP
	•	IPv6 Routing
Author
Talal Ali Alshehri
Information Technology Graduate with a strong interest in Networking, Cisco Technologies, and IT Infrastructure.

