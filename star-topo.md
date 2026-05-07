# Practical 2 — Create Star Topology Using Hub and Switch in Cisco Packet Tracer

# Aim

To create and study Star Topology using:

1. Hub
2. Switch

in Cisco Packet Tracer.

---

# Objective

The objective of this practical is to:

* Understand Star Topology
* Learn centralized network communication
* Differentiate between Hub and Switch
* Configure IP addresses on multiple PCs
* Test communication between devices
* Understand collision and broadcast domains

---

# Software Required

| Software            | Purpose                     |
| ------------------- | --------------------------- |
| Cisco Packet Tracer | Network simulation software |

---

# Devices Required

# Part A — Star Topology Using Hub

| Device                        | Quantity |
| ----------------------------- | -------- |
| Hub-PT                        | 1        |
| PC                            | 4        |
| Copper Straight Through Cable | 4        |

---

# Part B — Star Topology Using Switch

| Device                        | Quantity |
| ----------------------------- | -------- |
| 2960 Switch                   | 1        |
| PC                            | 4        |
| Copper Straight Through Cable | 4        |

---

# Theory

# What is Star Topology?

Star topology is a network topology where all devices are connected to a central device.

The central device can be:

* Hub
* Switch

---

# Structure of Star Topology

```text
          PC1
           |
           |
PC2 ---- HUB/SWITCH ---- PC3
           |
           |
          PC4
```

---

# Characteristics of Star Topology

* Centralized communication
* Easy troubleshooting
* Easy to expand
* Failure of one cable affects only one device
* Failure of central device affects entire network

---

# Difference Between Hub and Switch

| Hub                            | Switch                         |
| ------------------------------ | ------------------------------ |
| Layer 1 Device                 | Layer 2 Device                 |
| Broadcasts data to all devices | Sends data only to destination |
| Slower                         | Faster                         |
| More collisions                | Fewer collisions               |
| No MAC table                   | Uses MAC address table         |
| Less secure                    | More secure                    |

---

# PART A — STAR TOPOLOGY USING HUB

# Procedure

# Step 1 — Open Cisco Packet Tracer

1. Open Cisco Packet Tracer.
2. Wait for workspace to load.

---

# Step 2 — Add Hub

## Procedure in Cisco Packet Tracer

1. Go to bottom-left panel.
2. Click:

```text
Network Devices
```

3. Select:

```text
Hubs
```

4. Drag:

```text
Hub-PT
```

into the workspace.

---

# Step 3 — Add PCs

## Procedure in Cisco Packet Tracer

1. Click:

```text
End Devices
```

2. Select:

```text
PC
```

3. Drag 4 PCs into workspace.

Devices will appear as:

```text
PC0
PC1
PC2
PC3
```

---

# Step 4 — Arrange Devices

Arrange devices around the Hub.

Example:

```text
          PC0
           |
           |
PC1 ---- HUB ---- PC2
           |
           |
          PC3
```

---

# Step 5 — Connect PCs to Hub

## Procedure in Cisco Packet Tracer

### Open Connections Menu

1. Click:

```text
Connections
```

(lightning bolt icon)

---

### Select Cable

Choose:

```text
Copper Straight Through
```

---

### Connect Devices

Connect each PC to Hub.

Example:

| Device | Port          |
| ------ | ------------- |
| PC0    | FastEthernet0 |
| Hub    | Port 1        |
| PC1    | FastEthernet0 |
| Hub    | Port 2        |
| PC2    | FastEthernet0 |
| Hub    | Port 3        |
| PC3    | FastEthernet0 |
| Hub    | Port 4        |

---

# Step 6 — Configure IP Addresses

# Configure PC0

```text
PC0 → Desktop → IP Configuration
```

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.1   |
| Subnet Mask | 255.255.255.0 |

---

# Configure PC1

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.2   |
| Subnet Mask | 255.255.255.0 |

---

# Configure PC2

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.3   |
| Subnet Mask | 255.255.255.0 |

---

# Configure PC3

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.4   |
| Subnet Mask | 255.255.255.0 |

---

# Step 7 — Verify Physical Connection

After successful connection:

* Green lights should appear.

Green indicates:

```text
Active Connection
```

---

# Step 8 — Test Communication

# Open Command Prompt

Example:

```text
PC0 → Desktop → Command Prompt
```

---

# Run Ping Command

```bash
ping 192.168.1.4
```

---

# Expected Output

```text
Reply from 192.168.1.4
```

---

# Understanding Hub Communication

When PC0 sends data:

* Hub broadcasts data to all ports.
* Every PC receives the frame.
* Only destination PC accepts it.

This creates:

* More traffic
* More collisions
* Less efficiency

---

# PART B — STAR TOPOLOGY USING SWITCH

# Procedure

# Step 1 — Remove Hub (Optional)

You may either:

* Delete Hub topology
  OR
* Create new topology separately.

---

# Step 2 — Add Switch

## Procedure in Cisco Packet Tracer

1. Click:

```text
Network Devices
```

2. Select:

```text
Switches
```

3. Drag:

```text
2960 Switch
```

into workspace.

---

# Step 3 — Connect PCs to Switch

## Select Cable

Choose:

```text
Copper Straight Through
```

---

## Connect PCs

Connect:

| PC  | Switch Port     |
| --- | --------------- |
| PC0 | FastEthernet0/1 |
| PC1 | FastEthernet0/2 |
| PC2 | FastEthernet0/3 |
| PC3 | FastEthernet0/4 |

---

# Step 4 — Configure IP Addresses

Use same IP addresses as previous configuration.

---

# Step 5 — Test Communication

From PC0:

```bash
ping 192.168.1.4
```

---

# Expected Output

```text
Reply from 192.168.1.4
```

---

# Understanding Switch Communication

When PC0 sends data:

* Switch checks MAC address table.
* Data is sent only to destination device.
* Other devices do not receive unnecessary traffic.

Advantages:

* Faster communication
* Better efficiency
* Reduced collisions
* Improved security

---

# Simulation Mode Observation

# Procedure

1. Click:

```text
Simulation Mode
```

(bottom-right corner)

2. Send ping packet.
3. Observe:

* Packet movement
* ARP process
* ICMP packets
* Broadcast behavior

---

# Important Concepts Learned

| Concept          | Explanation                     |
| ---------------- | ------------------------------- |
| Star Topology    | Centralized network design      |
| Hub              | Broadcast device                |
| Switch           | Intelligent forwarding device   |
| MAC Address      | Physical hardware address       |
| ICMP             | Protocol used by ping           |
| Broadcast Domain | Area where broadcasts propagate |

---

# Troubleshooting

# Problem 1 — No Communication

## Causes

* Wrong IP configuration
* Cable issue
* Different subnet

---

## Solution

Verify:

* IP addresses
* Subnet masks
* Cable connections
* Green indicators

---

# Problem 2 — Red Connection Lights

## Causes

* Wrong cable
* Interface issue

---

## Solution

Use:

```text
Copper Straight Through
```

---

# Problem 3 — Ping Request Timed Out

## Causes

* Incorrect IP
* Network mismatch

---

## Solution

Ensure all devices belong to:

```text
192.168.1.0/24
```

---

# Advantages of Star Topology

* Easy management
* Easy fault detection
* Better performance
* Easy expansion
* Reliable communication

---

# Disadvantages of Star Topology

* Central device dependency
* More cable requirement
* Higher setup cost

---

# Viva Questions and Answers

# Q1. What is Star Topology?

A topology where all devices connect to a central device.

---

# Q2. Which devices are used as central devices?

* Hub
* Switch

---

# Q3. Which cable is used between PC and Switch?

```text
Copper Straight Through
```

---

# Q4. Difference between Hub and Switch?

Hub broadcasts data to all devices while switch sends data only to destination device.

---

# Q5. Which OSI layer does Switch operate on?

Layer 2 (Data Link Layer).

---

# Q6. Which OSI layer does Hub operate on?

Layer 1 (Physical Layer).

---

# Q7. Why is switch better than hub?

Because it reduces collisions and improves efficiency.

---

# Applications of Star Topology

* Schools
* Offices
* Computer labs
* LAN networks
* Enterprise networks

---

# Result

Star topology using both Hub and Switch was successfully created and communication between devices was verified using the ping command.

---

# Conclusion

In this practical, we learned:

* How to create Star topology
* Difference between Hub and Switch
* How centralized communication works
* How to configure multiple PCs
* How to test communication using ping
* Basic packet flow understanding

This practical helps build strong fundamentals in LAN networking and topology design.

---

# Quick Revision Summary

| Task               | Action                     |
| ------------------ | -------------------------- |
| Add central device | Hub/Switch                 |
| Add end devices    | PCs                        |
| Connect devices    | Straight Through Cable     |
| Configure IPs      | Desktop → IP Configuration |
| Test network       | `ping`                     |
| Observe packets    | Simulation Mode            |

---

# Commands Used

## Ping Command

```bash
ping 192.168.1.4
```

---

# Recommended Practice Exercises

1. Add more PCs to topology.
2. Compare Hub vs Switch behavior.
3. Observe packet broadcast in Simulation Mode.
4. Create star topology with 8 PCs.
5. Disconnect one cable and observe impact.

---

# Bonus Learning

## Why Switches Are Preferred Today

Modern networks prefer switches because:

* Faster communication
* Better bandwidth usage
* Fewer collisions
* Improved security
* Intelligent packet forwarding

Hubs are mostly obsolete in modern networking.

---

# End of Practical 2
