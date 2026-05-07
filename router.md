# Practical 5 — Perform Initial Router Configuration in Cisco Packet Tracer

# Aim

To perform the initial configuration of a Cisco Router using Cisco Packet Tracer.

---

# Objective

The objective of this practical is to:

- Access router CLI
- Configure hostname
- Configure passwords
- Configure interfaces
- Assign IP addresses
- Enable interfaces
- Configure banner message
- Test connectivity
- Save configuration

---

# Theory

## What is a Router?

A router is a Layer 3 networking device used to:

- Connect different networks
- Forward packets using IP addresses
- Choose the best path for data transfer

---

# Difference Between Switch and Router

| Switch | Router |
|---|---|
| Works on Layer 2 | Works on Layer 3 |
| Uses MAC address | Uses IP address |
| Connects devices in same LAN | Connects different networks |
| Forwards frames | Routes packets |

---

# Devices Required

| Device | Quantity |
|---|---|
| Router (1941/2911) | 1 |
| PC | 2 |
| Copper Straight Through Cable | 2 |

---

# Network Topology

```text
PC0 ---- Router0 ---- PC1
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

# Cisco IOS Modes

| Mode | Prompt | Purpose |
|---|---|---|
| User EXEC Mode | `Router>` | Basic commands |
| Privileged EXEC Mode | `Router#` | Administrative commands |
| Global Configuration Mode | `Router(config)#` | Device configuration |
| Interface Configuration Mode | `Router(config-if)#` | Interface configuration |
| Line Configuration Mode | `Router(config-line)#` | Password configuration |

---

# Step-by-Step Procedure

# Step 1 — Open Cisco Packet Tracer

1. Open Cisco Packet Tracer.
2. Wait for workspace to load completely.

---

# Step 2 — Add Router

## Procedure

1. Go to:

```text
Network Devices → Routers
```

2. Select:

```text
1941 Router
```

3. Drag router into workspace.

The router appears as:

```text
Router0
```

---

# Step 3 — Add PCs

1. Go to:

```text
End Devices
```

2. Add:
- PC0
- PC1

---

# Step 4 — Connect Devices

# Open Connections

Click:

```text
Connections
```

(lightning bolt icon)

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
| Router0 | GigabitEthernet0/0 |

---

| Device | Port |
|---|---|
| PC1 | FastEthernet0 |
| Router0 | GigabitEthernet0/1 |

---

# Expected Topology

```text
PC0 ---- Router0 ---- PC1
```

---

# Step 5 — Open Router CLI

1. Double-click:

```text
Router0
```

2. Open:

```text
CLI
```

---

# Initial Prompt

You may see:

```text
Continue with configuration dialog? [yes/no]:
```

Type:

```bash
no
```

Press Enter.

---

# Step 6 — Enter Privileged EXEC Mode

```bash
enable
```

Prompt becomes:

```text
Router#
```

---

# Step 7 — Enter Global Configuration Mode

```bash
configure terminal
```

OR

```bash
conf t
```

Prompt becomes:

```text
Router(config)#
```

---

# Step 8 — Configure Hostname

```bash
hostname LAB_ROUTER
```

Prompt changes to:

```text
LAB_ROUTER(config)#
```

---

# Purpose

Hostname identifies the router in network administration.

---

# Step 9 — Configure Enable Password

```bash
enable password cisco
```

---

# Purpose

Protects privileged EXEC mode.

---

# Step 10 — Configure Console Password

# Enter Console Line

```bash
line console 0
```

---

# Configure Password

```bash
password admin
```

---

# Enable Login

```bash
login
```

---

# Exit

```bash
exit
```

---

# Step 11 — Configure Banner Message

```bash
banner motd # Unauthorized Access Prohibited #
```

---

# Purpose

Displays warning message before login.

---

# Step 12 — Configure Router Interfaces

# Configure G0/0

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

# Configure G0/1

```bash
interface gigabitEthernet0/1
```

---

# Assign IP Address

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

# Important Concept

Router interfaces are:

```text
shutdown by default
```

Therefore:

```bash
no shutdown
```

is mandatory.

---

# Step 13 — Configure PC0 IP Address

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

# Step 14 — Configure PC1 IP Address

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

The router acts as:

```text
Gateway to other networks
```

---

# Step 15 — Verify Interfaces

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

# Meaning of Interface States

| State | Meaning |
|---|---|
| up/up | Interface working properly |
| administratively down | Interface shutdown |
| down/down | Physical connection problem |

---

# Step 16 — Test Connectivity

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

The router:
- Received packet
- Checked destination network
- Forwarded packet to correct interface

This process is called:

```text
Routing
```

---

# Step 17 — Save Configuration

# Return to Privileged Mode

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

# Expected Output

```text
[OK]
```

---

# Full Command Sequence

```bash
enable
configure terminal
hostname LAB_ROUTER
enable password cisco

line console 0
password admin
login
exit

banner motd # Unauthorized Access Prohibited #

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

# Show Running Configuration

```bash
show running-config
```

Displays active configuration.

---

# Show Routing Table

```bash
show ip route
```

Displays routing table.

---

# Show Interface Summary

```bash
show ip interface brief
```

Displays interface status and IP addresses.

---

# Important Concepts Learned

| Concept | Explanation |
|---|---|
| Router | Layer 3 device |
| Routing | Packet forwarding |
| Interface IP | Network identity |
| Default Gateway | Exit point from network |
| CLI | Cisco command interface |

---

# Troubleshooting

# Problem 1 — Ping Fails

## Causes

- Interface shutdown
- Wrong gateway
- Wrong subnet
- Incorrect cable

---

# Solution

Check:
- `no shutdown`
- IP addresses
- Default gateway
- Cable type

---

# Problem 2 — Interface Down

## Solution

Run:

```bash
no shutdown
```

---

# Problem 3 — Wrong Network

Devices must belong to correct subnet.

---

# Applications of Routers

- Internet connectivity
- Communication between networks
- Enterprise networking
- WAN communication
- Traffic routing

---

# Viva Questions and Answers

# Q1. What is a router?

A Layer 3 networking device that forwards packets between networks.

---

# Q2. Which OSI layer does router work on?

Layer 3

---

# Q3. What is routing?

The process of forwarding packets between networks.

---

# Q4. Why do we configure default gateway?

To communicate outside local network.

---

# Q5. Which command enables interface?

```bash
no shutdown
```

---

# Q6. Which command shows routing table?

```bash
show ip route
```

---

# Q7. Why is router interface configured with IP address?

To identify networks connected to the router.

---

# Result

Initial router configuration was successfully performed and communication between different networks was verified.

---

# Conclusion

In this practical, we learned:

- Router configuration
- Interface configuration
- IP addressing
- Gateway configuration
- Packet routing
- Connectivity testing
- Cisco IOS CLI basics

This practical forms the foundation of routing and inter-network communication.

---

# Quick Revision Summary

| Task | Command |
|---|---|
| Enter privileged mode | `enable` |
| Enter global config | `conf t` |
| Configure hostname | `hostname NAME` |
| Configure interface | `interface g0/0` |
| Assign IP | `ip address` |
| Enable interface | `no shutdown` |
| Save configuration | `write memory` |

---

# Bonus Learning

Routers make the Internet possible.

Every time data moves:
- Between WiFi and Internet
- Between offices
- Between countries

routers decide:
- Where packets should go
- Best path for communication

Routing is one of the core foundations of Computer Networks.

---

# End of Practical 5