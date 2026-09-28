Cisco Branch Network Design – VLAN, DHCP & Inter-VLAN Routing
📌 Project Overview

This project is a small enterprise branch network designed and implemented in Cisco Packet Tracer for XYZ Company.

The company requires a separate network for three departments while still allowing communication between them. The network uses VLAN segmentation, Router-on-a-Stick, DHCP, and wireless access points to provide a structured and scalable network.

The branch operates independently from the company's HQ network.

🎯 Objectives
Design a small enterprise branch network.
Separate departments using VLANs.
Provide wireless connectivity for each department.
Automatically assign IPv4 addresses using DHCP.
Enable communication between different VLANs.
Configure Cisco router and switch using CLI.
Practice network troubleshooting and verification.
🏢 Network Requirements

The network contains:

1 Cisco Router
1 Cisco Switch
3 Wireless Access Points
PCs and printers for each department
3 VLANs
DHCP for automatic IP allocation
Inter-VLAN routing
Departments
Department	VLAN
Admin / IT	VLAN 10
Finance / HR	VLAN 20
Customer Service / Reception	VLAN 30
🌐 IP Addressing Scheme

The ISP provided the base network:

192.168.1.0/24

It was subnetted into three /26 networks.

VLAN	Department	Network	Gateway	Usable Hosts
10	Admin / IT	192.168.1.0/26	192.168.1.1	.1 – .62
20	Finance / HR	192.168.1.64/26	192.168.1.65	.65 – .126
30	Customer / Reception	192.168.1.128/26	192.168.1.129	.129 – .190

Subnet Mask:

255.255.255.192
🗺️ Network Topology
                         Cisco Router
                              |
                         G0/0 | Fa0/10
                              |
                            TRUNK
                              |
                        Cisco 2960 Switch
                    _________|_________
                   |         |         |
                VLAN 10   VLAN 20   VLAN 30
                   |         |         |
                  AP1       AP2       AP3
                   |         |         |
                Admin     Finance   Customer
                 Users      Users     Users
🔧 Technologies Used
Cisco Packet Tracer
Cisco IOS CLI
VLAN
802.1Q Trunking
Router-on-a-Stick
Inter-VLAN Routing
DHCP
IPv4 Subnetting
Wireless LAN
Ping / Network Troubleshooting
⚙️ VLAN Configuration

Three VLANs were created on the switch:

VLAN 10 → ADMIN_IT
VLAN 20 → FINANCE_HR
VLAN 30 → CUSTOMER_RECEPTION

Access ports were assigned to their respective VLANs.

The router connection was configured as a trunk port to carry traffic from all three VLANs.

Fa0/10 → Trunk → Router G0/0
🔀 Router-on-a-Stick

Since only one physical router interface is available, subinterfaces were created:

G0/0.10 → VLAN 10 → 192.168.1.1
G0/0.20 → VLAN 20 → 192.168.1.65
G0/0.30 → VLAN 30 → 192.168.1.129

The router performs inter-VLAN routing, allowing devices in different departments to communicate.

📡 Wireless Network

Each department has a dedicated wireless access point.

Admin/IT              → ADMIN_WIFI
Finance/HR            → FINANCE_WIFI
Customer/Reception    → CUSTOMER_WIFI

Users can connect wirelessly to the appropriate departmental network.

📥 DHCP Configuration

DHCP is configured on the router to automatically provide:

IP address
Subnet mask
Default gateway
DNS server

Example:

Admin PC
IP Address:      192.168.1.x
Subnet Mask:     255.255.255.192
Gateway:         192.168.1.1

Finance and Customer devices receive addresses from their respective DHCP pools.

🧪 Network Testing

The network was tested using:

Check VLANs
show vlan brief
Check trunk
show interfaces trunk
Check router interfaces
show ip interface brief
Check DHCP leases
show ip dhcp binding
Test connectivity
ping <destination-ip>

Connectivity was tested between:

Admin → Finance
Admin → Customer
Finance → Customer

Successful communication confirms that inter-VLAN routing is functioning correctly.

📚 Key Concepts Learned

Through this project, I practiced:

IPv4 subnetting
VLAN creation and segmentation
Access and trunk ports
802.1Q encapsulation
Router-on-a-Stick
Inter-VLAN routing
DHCP configuration
Wireless network configuration
Cisco IOS commands
Network troubleshooting
🚀 Future Improvements

The network can be enhanced by adding:

VLAN 99 for switch management
SSH-based switch management
Port security
ACLs between departments
DHCP security
Redundant switches and routers
Firewall/Internet connectivity
Network monitoring
Dynamic routing
Centralized wireless management
👨‍💻 Project Status

Status: Completed / In Progress

Platform: Cisco Packet Tracer

Project Type: Enterprise Network Design & Implementation

Focus: VLANs, DHCP, Wireless Networking & Inter-VLAN Routing

