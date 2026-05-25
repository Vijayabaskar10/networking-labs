# Switch Connectivity and MAC Learning Lab

## Objective
Understand how a switch forwards data, learns MAC addresses, and delivers frames between devices.

---

## Topology
5 PCs connected to a switch.

Communication tested between:
- PC1 → PC4
- ACK from PC4 → PC1

---

## IP Addressing

| Device | IP Address |
|--------|-------------|
| PC1 | 10.10.10.1 |
| PC4 | 10.10.10.4 |

Subnet Mask:
```text
255.255.255.0
```

---

## Verification
- Successful communication between PC1 and PC4
- ACK reply received successfully
- MAC addresses learned dynamically by switch

---

## Commands Used

### Check MAC Address Table
```bash
show mac address-table
```

### Check Running Configuration
```bash
show running-config
```

---

## What I Learned

### Switch Working
A switch is a Layer 2 device that forwards frames using MAC addresses.

Unlike a hub:
- switch sends data only to destination port
- improves speed and security
- reduces unnecessary traffic

---

### MAC Address Learning
The switch learns MAC addresses dynamically from incoming frames.

When PC1 sent data to PC4:
- switch learned PC1 MAC address
- switch learned PC4 MAC address after reply

Other PCs did not appear initially because they had not generated traffic.

---

### Running Configuration
Using:
```bash
show running-config
```

I observed:
- Cisco IOS version
- hostname
- interface information
- spanning-tree configuration
- default switch settings

---

## Concepts Practiced
- Layer 2 Switching
- MAC Address Table
- Frame Forwarding
- Cisco Switch CLI
- Running Configuration
- Basic Network Troubleshooting