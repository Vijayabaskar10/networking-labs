# Hub Connectivity Lab

## Objective
Understand how a hub works by connecting six PCs in the same network and testing communication between devices.

## Topology
6 PCs connected using a Hub.

## IP Addressing

| Device | IP Address |
|--------|-------------|
| PC1 | 10.10.10.1 |
| PC2 | 10.10.10.2 |
| PC3 | 10.10.10.3 |
| PC4 | 10.10.10.4 |
| PC5 | 10.10.10.5 |
| PC6 | 10.10.10.6 |

Subnet Mask:
```text
255.255.255.0
```

## Communication Test
- Message sent from PC1 to PC4
- ACK received from PC4 to PC1
- Successful communication verified

## What I Learned

### How Hub Works
A hub is a Layer 1 networking device that broadcasts incoming signals to all connected devices without checking destination addresses.

When PC1 sends data to PC4:
- Hub receives the signal
- Hub forwards the signal to every connected PC
- Only PC4 processes the message
- Other PCs ignore it

### Advantages of Hub
- Simple device
- Low cost
- Easy to connect devices

### Disadvantages of Hub
- Broadcasts data to all devices
- High collision chances
- Low security
- Shared bandwidth
- Slower compared to switches

## Concepts Practiced
- Basic networking
- IP addressing
- Hub communication
- Broadcast behavior
- Packet delivery
- ACK response