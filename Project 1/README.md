# Accounts and Delivery Department Network Design using Cisco Packet Tracer

## Overview

This project demonstrates the design and implementation of a basic enterprise network in Cisco Packet Tracer. The network connects the **Accounts** and **Delivery** departments using a router and switches, enabling communication between devices located in different subnets.

The project focuses on:

* Network topology design
* IPv4 subnetting
* Router and switch connectivity
* IP address configuration
* Inter-department communication
* Network testing and verification

---

## Objectives

* Connect the Accounts and Delivery departments through a routed network.
* Configure separate subnets for each department.
* Assign valid IP addresses, subnet masks, and default gateways.
* Enable communication between departments.
* Verify connectivity using ICMP (Ping).

---

## Network Topology

```text
+-------------------+                     +-------------------+
| Accounts Dept.    |                     | Delivery Dept.    |
|                   |                     |                   |
| PC0    PC1        |                     | PC2    PC3        |
+----+----+---------+                     +----+----+---------+
     |    |                                    |    |
     +----+                                    +----+
        |                                         |
   +---------+                             +---------+
   |Switch 0 |                             |Switch 1 |
   +----+----+                             +----+----+
        |                                       |
        +---------------+   +-------------------+
                        |   |
                  +-----+---+-----+
                  | Cisco Router  |
                  | (2911 / 1941) |
                  +---------------+
```

---

## Devices Used

| Device                     | Quantity |
| -------------------------- | -------- |
| Cisco Router (2911/1941)   | 1        |
| Cisco 2960 Switch          | 2        |
| PCs                        | 4        |
| Network Printer (Optional) | 1        |

---

## Network Addressing

### Base Network

```text
192.168.40.0/24
```

### Subnetting

The network is divided into two equal-sized subnets.

| Department | Network Address | CIDR | Subnet Mask     |
| ---------- | --------------- | ---- | --------------- |
| Accounts   | 192.168.40.0    | /25  | 255.255.255.128 |
| Delivery   | 192.168.40.128  | /25  | 255.255.255.128 |

---

## Subnet Details

### Accounts Department

| Parameter         | Value          |
| ----------------- | -------------- |
| Network ID        | 192.168.40.0   |
| First Host        | 192.168.40.1   |
| Last Host         | 192.168.40.126 |
| Broadcast Address | 192.168.40.127 |

### Delivery Department

| Parameter         | Value          |
| ----------------- | -------------- |
| Network ID        | 192.168.40.128 |
| First Host        | 192.168.40.129 |
| Last Host         | 192.168.40.254 |
| Broadcast Address | 192.168.40.255 |

---

## IP Address Allocation

### Router Interfaces

| Interface          | IP Address     | Subnet Mask     |
| ------------------ | -------------- | --------------- |
| GigabitEthernet0/0 | 192.168.40.1   | 255.255.255.128 |
| GigabitEthernet0/1 | 192.168.40.129 | 255.255.255.128 |

---

### Accounts Department

| Device | IP Address   | Default Gateway |
| ------ | ------------ | --------------- |
| PC0    | 192.168.40.2 | 192.168.40.1    |
| PC1    | 192.168.40.3 | 192.168.40.1    |

---

### Delivery Department

| Device | IP Address     | Default Gateway |
| ------ | -------------- | --------------- |
| PC2    | 192.168.40.130 | 192.168.40.129  |
| PC3    | 192.168.40.131 | 192.168.40.129  |

---

## Router Configuration

```bash
enable
configure terminal

interface gigabitEthernet 0/0
 ip address 192.168.40.1 255.255.255.128
 no shutdown
 exit

interface gigabitEthernet 0/1
 ip address 192.168.40.129 255.255.255.128
 no shutdown
 exit

end
write memory
```

---

## Implementation Steps

1. Place one Cisco Router (2911/1941) in the workspace.
2. Add two Cisco 2960 switches.
3. Add two PCs for the Accounts department.
4. Add two PCs for the Delivery department.
5. Connect:

   * PCs to switches using Copper Straight-Through cables.
   * Switches to router interfaces using Copper Straight-Through cables.
6. Configure IP addresses and default gateways on all PCs.
7. Configure router interfaces with the assigned IP addresses.
8. Save the configuration.

---

## Connectivity Verification

### Test from Delivery Department

```bash
ping 192.168.40.2
ping 192.168.40.3
```

### Test from Accounts Department

```bash
ping 192.168.40.130
ping 192.168.40.131
```

### Expected Output

```text
Reply from 192.168.40.2
Reply from 192.168.40.3

Reply from 192.168.40.130
Reply from 192.168.40.131
```

Successful replies indicate that routing between the two departments is functioning correctly.

---

## Skills Demonstrated

* Cisco Packet Tracer
* IPv4 Addressing
* Subnetting (/25 Networks)
* Router Configuration
* Switch Configuration
* Inter-Network Communication
* Network Troubleshooting
* Enterprise Network Design Fundamentals

---

## Learning Outcomes

After completing this project, you will understand:

* How subnetting divides a network into multiple logical segments.
* How routers enable communication between different subnets.
* How to configure IP addresses and gateways.
* How to verify connectivity using network diagnostic tools.
* Basic network design principles used in organizational environments.

---

## Project Result

The Accounts and Delivery departments were successfully connected using a routed network architecture. Separate subnets were created for each department, router interfaces were configured as gateways, and end-to-end communication was verified through successful ping tests between departmental PCs.
