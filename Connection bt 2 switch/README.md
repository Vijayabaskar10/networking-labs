# Inter-Switch Communication Lab

## Objective
Understand how switches communicate with each other and how devices connected to different switches exchange data.

---

## Topology

- Switch0 connected with 3 PCs
- Switch1 connected with 2 PCs
- Switch0 connected to Switch1
- Created a network closet and rack for Switch1

---

## Devices Used

- 2 Switches
- 5 PCs
- Copper Straight-Through Cables
- Copper Cross-Over Cable (Switch-to-Switch)
- Rack and Closet

---

## Communication Test

Message sent:
```text
PC0 → PC4
```

Successful communication verified between devices connected to different switches.

---

## What I Learned

### Switch-to-Switch Communication
Two switches can communicate with each other using a switch connection link.

When PC0 sends data to PC4:
- Switch0 receives the frame
- Learns source MAC address
- Forwards frame to Switch1
- Switch1 delivers frame to PC4

---

### MAC Address Learning
Both switches dynamically learn MAC addresses from incoming frames and store them in the MAC address table.

Command used:
```bash
show mac address-table
```

---

### Network Expansion
Using multiple switches helps:
- expand network size
- connect more devices
- improve network organization

---

### Rack and Closet
Created a network closet and rack for Switch1 to understand structured network infrastructure used in enterprises and server rooms.

---

## Concepts Practiced

- Layer 2 Switching
- Inter-Switch Communication
- MAC Address Learning
- Frame Forwarding
- Network Expansion
- Structured Cabling
- Network Rack Organization