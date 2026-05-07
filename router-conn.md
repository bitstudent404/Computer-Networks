# Practical 7 — To Implement Connection Between Devices Using a Router in Cisco Packet Tracer

# Aim

To implement communication between devices located in different networks using a router in Cisco Packet Tracer.

---

# Objective

The objective of this practical is to:

- Connect different networks using a router
- Configure router interfaces
- Configure IP addresses
- Configure default gateways
- Perform routing between networks
- Test communication using ping

---

# Theory

# Why Router is Needed?

Devices in:

```text
Different Networks
```

cannot communicate directly.

A router is required to:
- connect different networks
- forward packets
- act as default gateway

---

# Example

| Device | Network |
|---|---|
| PC0 | 192.168.1.0 |
| PC1 | 192.168.2.0 |

Since networks are different:
- communication requires router

---

# Devices Required

| Device | Quantity |
|---|---|
| Router | 1 |
| Switch | 2 |
| PC | 2 |
| Copper Straight Through Cable | 4 |

---

# Network Topology

```text
PC0 ---- Switch0 ---- Router0 ---- Switch1 ---- PC1
```

---

# IP Addressing Scheme

| Device | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| Router0 | G0/0 | 192.168.1.1 | 255.255.255.0 |
| Router0 | G0/1 | 192.168.2.1 | 255.255.255.0 |
| PC0 | FastEthernet0 | 192.168.1.2 | 255.255.255.0 |
| PC1 | FastEthernet0 | 192.168.2.2 | 255.255.255.0 |

---

# Default Gateway Configuration

| Device | Default Gateway |
|---|---|
| PC0 | 192.168.1.1 |
| PC1 | 192.168.2.1 |

---

# Step-by-Step Procedure

# Step 1 — Open Cisco Packet Tracer

1. Open Cisco Packet Tracer.
2. Wait for workspace to load.

---

# Step 2 — Add Devices

# Add Router

1. Go to:

```text
Network Devices → Routers
```

2. Select:
- 1941 Router

3. Drag into workspace.

---

# Add Switches

1. Go to:

```text
Network Devices → Switches
```

2. Add:
- Switch0
- Switch1

---

# Add PCs

1. Go to:

```text
End Devices
```

2. Add:
- PC0
- PC1

---

# Step 3 — Arrange Devices

Arrange devices like:

```text
PC0 ---- Switch0 ---- Router0 ---- Switch1 ---- PC1
```

---

# Step 4 — Connect Devices

# Open Connections

Click:

```text
Connections
```

(lightning icon)

---

# Select Cable

Choose:

```text
Copper Straight Through
```

---

# Make Connections

| Device | Port |
|---|---|
| PC0 | FastEthernet0 |
| Switch0 | FastEthernet0/1 |

---

| Device | Port |
|---|---|
| Switch0 | FastEthernet0/24 |
| Router0 | GigabitEthernet0/0 |

---

| Device | Port |
|---|---|
| Router0 | GigabitEthernet0/1 |
| Switch1 | FastEthernet0/24 |

---

| Device | Port |
|---|---|
| Switch1 | FastEthernet0/1 |
| PC1 | FastEthernet0 |

---

# Wait for Green Links

After a few seconds:
- links should become green

Meaning:
- physical connection active

---

# Step 5 — Configure Router

# Open Router CLI

Double-click:

```text
Router0
```

Open:

```text
CLI
```

---

# Skip Initial Dialog

```bash
no
```

---

# Enter Privileged Mode

```bash
enable
```

---

# Enter Global Configuration

```bash
configure terminal
```

---

# Configure Interface G0/0

```bash
interface gigabitEthernet0/0
```

---

# Assign IP Address

```bash
ip address 192.168.1.1 255.255.255.0
```

---

# Enable Interface

```bash
no shutdown
```

---

# Exit

```bash
exit
```

---

# Configure Interface G0/1

```bash
interface gigabitEthernet0/1
```

---

# Assign IP

```bash
ip address 192.168.2.1 255.255.255.0
```

---

# Enable Interface

```bash
no shutdown
```

---

# Exit

```bash
exit
```

---

# Step 6 — Configure PC0 IP Address

Open:

```text
PC0 → Desktop → IP Configuration
```

Set:

| Field | Value |
|---|---|
| IP Address | 192.168.1.2 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.1.1 |

---

# Step 7 — Configure PC1 IP Address

Open:

```text
PC1 → Desktop → IP Configuration
```

Set:

| Field | Value |
|---|---|
| IP Address | 192.168.2.2 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.2.1 |

---

# Why Default Gateway?

Default gateway tells the PC:

```text
Where to send packets for other networks
```

---

# Step 8 — Verify Router Interfaces

On router:

```bash
show ip interface brief
```

---

# Expected Output

```text
GigabitEthernet0/0   up   up
GigabitEthernet0/1   up   up
```

---

# Meaning

| State | Meaning |
|---|---|
| up/up | Working properly |
| administratively down | Interface disabled |
| down/down | Physical issue |

---

# Step 9 — Test Connectivity

# From PC0

Open:

```text
Desktop → Command Prompt
```

Run:

```bash
ping 192.168.2.2
```

---

# Expected Output

```text
Reply from 192.168.2.2
```

---

# What Happened?

1. PC0 sent packet to router
2. Router checked destination network
3. Router forwarded packet to PC1 network
4. PC1 replied successfully

This process is called:

```text
Routing
```

---

# Step 10 — Save Router Configuration

Return to privileged mode:

```bash
end
```

---

# Save Configuration

```bash
write memory
```

OR

```bash
copy running-config startup-config
```

---

# Full Router Configuration Commands

```bash
enable
configure terminal

interface gigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface gigabitEthernet0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit

end
write memory
```

---

# Verification Commands

# Show Routing Table

```bash
show ip route
```

---

# Show Interface Status

```bash
show ip interface brief
```

---

# Test Connectivity

```bash
ping
```

---

# Important Concepts Learned

| Concept | Explanation |
|---|---|
| Router | Connects networks |
| Routing | Packet forwarding |
| Default Gateway | Path to other networks |
| Interface IP | Router network identity |
| Subnet | Logical network division |

---

# Troubleshooting

# Problem 1 — Ping Fails

## Causes

- Wrong gateway
- Wrong IP address
- Interface shutdown
- Incorrect subnet

---

# Solution

Check:
- `no shutdown`
- IP addresses
- Default gateway
- Correct subnet

---

# Problem 2 — Interface Down

## Solution

Run:

```bash
no shutdown
```

---

# Problem 3 — Red Link

## Solution

- Reconnect cable
- Wait few seconds
- Use correct cable

---

# Applications

- Office networking
- Internet access
- Communication between departments
- Campus networking
- Enterprise infrastructure

---

# Viva Questions and Answers

# Q1. Why is router needed?

To connect different networks.

---

# Q2. What is routing?

Process of forwarding packets between networks.

---

# Q3. What is default gateway?

Address used to communicate outside local network.

---

# Q4. Which OSI layer does router work on?

Layer 3

---

# Q5. Which command enables interface?

```bash
no shutdown
```

---

# Q6. Which command displays routing table?

```bash
show ip route
```

---

# Q7. Why do PCs need gateway?

To communicate with other networks.

---

# Result

Connection between devices using router was successfully implemented and communication between different networks was verified.

---

# Conclusion

In this practical, we learned:

- Router-based communication
- IP addressing
- Default gateway configuration
- Interface configuration
- Packet routing
- Connectivity verification

This practical demonstrates how routers enable communication between different networks.

---

# Quick Revision Summary

| Task | Command |
|---|---|
| Configure interface | `interface g0/0` |
| Assign IP | `ip address` |
| Enable interface | `no shutdown` |
| Verify interfaces | `show ip interface brief` |
| Show routes | `show ip route` |
| Test communication | `ping` |

---

# Bonus Learning

The Internet itself is a massive collection of routers.

Whenever data travels:
- between cities
- between countries
- between networks

routers decide:
- best path
- next destination
- packet forwarding

Routing is the backbone of modern networking.

---

# End of Practical 7