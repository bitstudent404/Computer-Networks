# Practical 3 — Create Bus, Ring, Tree, Hybrid, and Mesh Topologies in Cisco Packet Tracer

# Aim

To create and study different network topologies in Cisco Packet Tracer:

1. Bus Topology
2. Ring Topology
3. Tree Topology
4. Hybrid Topology
5. Mesh Topology

---

# Objective

The objective of this practical is to:

* Understand different network topologies
* Learn physical arrangement of network devices
* Compare topology structures
* Configure communication between devices
* Analyze advantages and disadvantages of each topology
* Observe packet transmission in different network designs

---

# Software Required

| Software            | Purpose                     |
| ------------------- | --------------------------- |
| Cisco Packet Tracer | Network simulation software |

---

# Devices Required

| Device                        | Quantity    |
| ----------------------------- | ----------- |
| PC                            | Multiple    |
| Hub/Switch                    | As required |
| Copper Straight Through Cable | Multiple    |
| Copper Cross-Over Cable       | Multiple    |

---

# Theory

# What is Network Topology?

Network topology refers to the physical or logical arrangement of devices in a computer network.

It defines:

* How devices are connected
* How data flows
* Communication structure
* Network reliability and performance

---

# Types of Topologies Covered

| Topology | Structure                                    |
| -------- | -------------------------------------------- |
| Bus      | Single backbone cable                        |
| Ring     | Circular connection                          |
| Tree     | Hierarchical arrangement                     |
| Hybrid   | Combination of topologies                    |
| Mesh     | Every device connected to every other device |

---

# PART A — BUS TOPOLOGY

# Theory

In Bus topology, all devices are connected to a single backbone cable.

Data travels through the shared communication line.

---

# Structure of Bus Topology

```text
PC0 ---- HUB ---- PC1 ---- HUB ---- PC2
```

---

# Procedure

# Step 1 — Open Cisco Packet Tracer

1. Open Cisco Packet Tracer.
2. Wait for workspace to load.

---

# Step 2 — Add Devices

## Add Hubs

1. Click:

```text
Network Devices
```

2. Select:

```text
Hubs
```

3. Drag 2 hubs into workspace.

---

## Add PCs

1. Click:

```text
End Devices
```

2. Drag:

* PC0
* PC1
* PC2

into workspace.

---

# Step 3 — Arrange Devices

Arrange devices linearly.

Example:

```text
PC0 ---- HUB0 ---- HUB1 ---- PC1 ---- PC2
```

---

# Step 4 — Connect Devices

## Open Connections

Click:

```text
Connections
```

---

## Select Cable

Choose:

```text
Copper Straight Through
```

---

## Connect Devices

Connect:

* PCs to hubs
* Hub to hub

---

# Step 5 — Configure IP Addresses

| Device | IP Address  |
| ------ | ----------- |
| PC0    | 192.168.1.1 |
| PC1    | 192.168.1.2 |
| PC2    | 192.168.1.3 |

Subnet Mask:

```text
255.255.255.0
```

---

# Step 6 — Test Communication

From PC0:

```bash
ping 192.168.1.3
```

---

# Advantages of Bus Topology

* Simple setup
* Low cost
* Less cable required

---

# Disadvantages of Bus Topology

* Backbone failure affects whole network
* Difficult troubleshooting
* More collisions

---

# PART B — RING TOPOLOGY

# Theory

In Ring topology, devices are connected in a circular manner.

Each device connects to two neighboring devices.

---

# Structure of Ring Topology

```text
PC0 ---- PC1
 |         |
 |         |
PC3 ---- PC2
```

---

# Procedure

# Step 1 — Add PCs

Add 4 PCs:

* PC0
* PC1
* PC2
* PC3

---

# Step 2 — Arrange in Circular Form

Arrange devices in ring shape.

---

# Step 3 — Connect PCs

## Select Cable

Choose:

```text
Copper Cross-Over
```

---

## Create Ring

Connect:

| Connection |
| ---------- |
| PC0 ↔ PC1  |
| PC1 ↔ PC2  |
| PC2 ↔ PC3  |
| PC3 ↔ PC0  |

---

# Step 4 — Configure IP Addresses

| Device | IP          |
| ------ | ----------- |
| PC0    | 192.168.1.1 |
| PC1    | 192.168.1.2 |
| PC2    | 192.168.1.3 |
| PC3    | 192.168.1.4 |

---

# Step 5 — Test Communication

From PC0:

```bash
ping 192.168.1.4
```

---

# Advantages of Ring Topology

* Organized communication
* Equal access for devices

---

# Disadvantages of Ring Topology

* Failure of one node may affect network
* Difficult troubleshooting

---

# PART C — TREE TOPOLOGY

# Theory

Tree topology is a hierarchical topology combining multiple star topologies.

---

# Structure of Tree Topology

```text
             MAIN SWITCH
              /      \
             /        \
        SWITCH1      SWITCH2
          /  \         /  \
        PC0  PC1     PC2  PC3
```

---

# Procedure

# Step 1 — Add Devices

Add:

| Device | Quantity |
| ------ | -------- |
| Switch | 3        |
| PC     | 4        |

---

# Step 2 — Arrange Devices

Arrange switches hierarchically.

---

# Step 3 — Connect Switches

Use:

```text
Copper Cross-Over
```

Connect:

* Main Switch ↔ Switch1
* Main Switch ↔ Switch2

---

# Step 4 — Connect PCs

Use:

```text
Copper Straight Through
```

Connect:

* PC0, PC1 → Switch1
* PC2, PC3 → Switch2

---

# Step 5 — Configure IP Addresses

| Device | IP          |
| ------ | ----------- |
| PC0    | 192.168.1.1 |
| PC1    | 192.168.1.2 |
| PC2    | 192.168.1.3 |
| PC3    | 192.168.1.4 |

---

# Step 6 — Test Communication

```bash
ping 192.168.1.4
```

---

# Advantages of Tree Topology

* Scalable
* Easy expansion
* Better management

---

# Disadvantages of Tree Topology

* Main backbone dependency
* More complex setup

---

# PART D — HYBRID TOPOLOGY

# Theory

Hybrid topology combines two or more topologies.

Example:

* Star + Bus
* Ring + Star

---

# Example Hybrid Structure

```text
        STAR NETWORK
             |
             |
BUS -------- SWITCH -------- RING
```

---

# Procedure

# Step 1 — Create Star Section

Create small star topology.

---

# Step 2 — Create Bus Section

Create small bus topology.

---

# Step 3 — Connect Both Sections

Connect both using switch or hub.

---

# Step 4 — Configure IP Addresses

Assign all devices IPs from same network.

Example:

```text
192.168.1.x
```

---

# Step 5 — Test Communication

Use:

```bash
ping
```

between different sections.

---

# Advantages of Hybrid Topology

* Flexible
* Scalable
* Reliable

---

# Disadvantages of Hybrid Topology

* Expensive
* Complex management

---

# PART E — MESH TOPOLOGY

# Theory

In Mesh topology, every device connects directly to every other device.

This provides high reliability.

---

# Structure of Mesh Topology

```text
      PC0 -------- PC1
       | \        / |
       |  \      /  |
       |   \    /   |
       |    \  /    |
       |     \/     |
       |     /\     |
       |    /  \    |
       |   /    \   |
       |  /      \  |
       | /        \ |
      PC2 -------- PC3
```

---

# Procedure

# Step 1 — Add PCs

Add:

* PC0
* PC1
* PC2
* PC3

---

# Step 2 — Arrange Devices

Arrange in square shape.

---

# Step 3 — Connect Every Device

Use:

```text
Copper Cross-Over
```

Connect every PC to every other PC.

Example:

| Connections |
| ----------- |
| PC0 ↔ PC1   |
| PC0 ↔ PC2   |
| PC0 ↔ PC3   |
| PC1 ↔ PC2   |
| PC1 ↔ PC3   |
| PC2 ↔ PC3   |

---

# Step 4 — Configure IP Addresses

| Device | IP          |
| ------ | ----------- |
| PC0    | 192.168.1.1 |
| PC1    | 192.168.1.2 |
| PC2    | 192.168.1.3 |
| PC3    | 192.168.1.4 |

---

# Step 5 — Test Communication

Use:

```bash
ping
```

between multiple devices.

---

# Advantages of Mesh Topology

* Highly reliable
* Multiple communication paths
* Fault tolerant

---

# Disadvantages of Mesh Topology

* Very expensive
* Large number of cables
* Complex setup

---

# Comparison of Topologies

| Topology | Cost      | Reliability | Complexity   |
| -------- | --------- | ----------- | ------------ |
| Bus      | Low       | Low         | Simple       |
| Ring     | Medium    | Medium      | Moderate     |
| Tree     | Medium    | High        | Moderate     |
| Hybrid   | High      | High        | Complex      |
| Mesh     | Very High | Very High   | Very Complex |

---

# Simulation Mode Observation

# Procedure

1. Click:

```text
Simulation Mode
```

2. Send ping packets.
3. Observe:

* Packet movement
* ARP process
* ICMP packets
* Broadcast behavior

---

# Important Concepts Learned

| Concept          | Explanation                 |
| ---------------- | --------------------------- |
| Network Topology | Device arrangement          |
| Backbone         | Main communication line     |
| Broadcast        | Sending data to all devices |
| Scalability      | Ability to expand network   |
| Redundancy       | Backup communication path   |

---

# Troubleshooting

# Problem 1 — Devices Not Communicating

## Causes

* Wrong IP addresses
* Wrong cables
* Different networks

---

## Solution

Verify:

* IP configuration
* Subnet masks
* Cable connections

---

# Problem 2 — Red Connection Lights

## Causes

* Incorrect cable type

---

## Solution

Use proper cable type:

| Connection      | Cable            |
| --------------- | ---------------- |
| PC ↔ Switch     | Straight Through |
| PC ↔ PC         | Cross-Over       |
| Switch ↔ Switch | Cross-Over       |

---

# Viva Questions and Answers

# Q1. What is network topology?

The physical or logical arrangement of devices in a network.

---

# Q2. Which topology uses a central device?

Star topology.

---

# Q3. Which topology is most reliable?

Mesh topology.

---

# Q4. Which topology uses least cable?

Bus topology.

---

# Q5. What is Hybrid topology?

A combination of two or more topologies.

---

# Q6. Why is Mesh topology expensive?

Because every device requires direct connections with all other devices.

---

# Applications of Different Topologies

| Topology | Applications                |
| -------- | --------------------------- |
| Bus      | Small LANs                  |
| Ring     | Older communication systems |
| Tree     | Schools, offices            |
| Hybrid   | Enterprise networks         |
| Mesh     | Military, critical systems  |

---

# Result

Bus, Ring, Tree, Hybrid, and Mesh topologies were successfully created and communication between devices was verified using ping commands in Cisco Packet Tracer.

---

# Conclusion

In this practical, we learned:

* Different network topologies
* Structure of each topology
* Advantages and disadvantages
* Communication flow in different networks
* Cable selection
* IP configuration and testing

This practical helps in understanding network design and architecture fundamentals.

---

# Quick Revision Summary

| Topology | Main Feature           |
| -------- | ---------------------- |
| Bus      | Single backbone        |
| Ring     | Circular structure     |
| Tree     | Hierarchical structure |
| Hybrid   | Combination topology   |
| Mesh     | Fully connected        |

---

# Commands Used

## Ping Command

```bash
ping 192.168.1.4
```

---

# Recommended Practice Exercises

1. Create larger mesh topology.
2. Observe packet flow in Simulation Mode.
3. Disconnect cables and observe effects.
4. Compare communication efficiency.
5. Add switches and routers to topologies.

---

# Bonus Learning

## Why Modern Networks Prefer Hybrid Topologies

Modern enterprise networks often use hybrid topologies because they:

* Combine flexibility and scalability
* Improve reliability
* Support large organizations
* Allow better network segmentation

---

# End of Practical 3
