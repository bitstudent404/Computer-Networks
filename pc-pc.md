# Practical 1 — Study and Perform PC to PC Communication in Cisco Packet Tracer

# Aim

To study and perform communication between two PCs using Cisco Packet Tracer.

---

# Objective

The purpose of this practical is to:

* Understand basic computer networking
* Learn how two computers communicate in a LAN
* Configure IP addresses manually
* Understand subnet masks
* Test communication using the `ping` command
* Learn basic troubleshooting in networks

---

# Software Required

| Software            | Purpose                     |
| ------------------- | --------------------------- |
| Cisco Packet Tracer | Network simulation software |

---

# Devices Required

| Device                  | Quantity |
| ----------------------- | -------- |
| PC                      | 2        |
| Copper Cross-Over Cable | 1        |

> Note: In newer versions of Packet Tracer, automatic cable selection may also work.

---

# Theory

## What is PC to PC Communication?

PC to PC communication refers to the exchange of data between two computers connected through a network.

For successful communication:

* Both PCs must be connected physically.
* Both must have valid IP addresses.
* Both must belong to the same network.
* Subnet masks must match.

---

# Important Networking Concepts

## 1. IP Address

An IP address uniquely identifies a device on a network.

Example:

```text
192.168.1.1
```

---

## 2. Subnet Mask

A subnet mask defines the network portion and host portion of an IP address.

Example:

```text
255.255.255.0
```

This means:

* Network: `192.168.1.x`
* Hosts can communicate directly.

---

## 3. Ping

`ping` is used to test connectivity between devices.

It uses the ICMP protocol.

Example:

```bash
ping 192.168.1.2
```

---

# Network Topology

```text
PC0  <-------->  PC1
```

Both PCs are directly connected using a Copper Cross-Over cable.

---

# Procedure

This practical is performed completely inside Cisco Packet Tracer.

Follow every step carefully.

---

# Step 1 — Open Cisco Packet Tracer

## Procedure in Cisco Packet Tracer

1. Open Cisco Packet Tracer software.
2. Wait for the workspace to load.
3. You will see:

   * Device-Type Selection Box (bottom-left)
   * Workspace Area (center)
   * Connections Section
   * Real-Time and Simulation Mode options

---

# Cisco Packet Tracer Interface Overview

| Section         | Purpose                     |
| --------------- | --------------------------- |
| End Devices     | PCs, laptops, servers       |
| Network Devices | Routers, switches, hubs     |
| Connections     | Different cable types       |
| Workspace       | Network design area         |
| Simulation Mode | Visual packet flow analysis |

---

Open:

Cisco Packet Tracer

---

# Step 2 — Add PCs

## Procedure in Cisco Packet Tracer

### Open End Devices

1. Go to the bottom-left corner.
2. Click:

```text
End Devices
```

You will now see:

* PC
* Laptop
* Server
* Printer
* Tablet

---

### Add First PC

1. Select:

```text
PC
```

2. Drag it into the workspace.
3. A device named:

```text
PC0
```

will appear.

---

### Add Second PC

1. Again select:

```text
PC
```

2. Drag another PC into the workspace.
3. It will appear as:

```text
PC1
```

---

### Final Workspace

Your workspace should now contain:

```text
PC0            PC1
```

---

---

# Step 3 — Connect the PCs

## Procedure in Cisco Packet Tracer

### Open Connections Menu

1. Go to the bottom-left panel.
2. Click:

```text
Connections
```

This is represented by a lightning bolt icon.

---

### Select Cable Type

Choose:

```text
Copper Cross-Over
```

Why?

Because similar devices (PC ↔ PC) require a cross-over cable.

---

### Connect PC0

1. Click on:

```text
PC0
```

2. A popup will appear.
3. Select:

```text
FastEthernet0
```

---

### Connect PC1

1. Click on:

```text
PC1
```

2. Select:

```text
FastEthernet0
```

---

### Verify Connection

After connecting:

* A cable line should appear.
* Green lights should appear on both ends.

Green means:

```text
Connection Successful
```

---

## Connect Devices

Connect:

| Device | Port          |
| ------ | ------------- |
| PC0    | FastEthernet0 |
| PC1    | FastEthernet0 |

---

# Step 4 — Configure IP Address on PC0

## Procedure in Cisco Packet Tracer

### Open PC0

1. Double-click on:

```text
PC0
```

A new window will open.

---

### Open Desktop Tab

1. Click:

```text
Desktop
```

You will see:

* IP Configuration
* Command Prompt
* Web Browser
* Terminal
* Text Editor

---

### Open IP Configuration

Click:

```text
IP Configuration
```

---

### Enter IP Address

Fill the fields:

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.1   |
| Subnet Mask | 255.255.255.0 |

Packet Tracer may automatically fill the subnet mask.

---

### Close Window

After entering details:

* Close the configuration window.

---

## Enter Configuration

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.1   |
| Subnet Mask | 255.255.255.0 |

---

# Step 5 — Configure IP Address on PC1

## Procedure in Cisco Packet Tracer

### Open PC1

1. Double-click:

```text
PC1
```

---

### Open Desktop Tab

Click:

```text
Desktop
```

---

### Open IP Configuration

Click:

```text
IP Configuration
```

---

### Enter IP Details

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.2   |
| Subnet Mask | 255.255.255.0 |

---

### Close Window

Close the configuration window after entering the details.

---

## Enter Configuration

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.2   |
| Subnet Mask | 255.255.255.0 |

---

# Step 6 — Verify Physical Connection

After successful connection:

* Green indicators should appear on both cable ends.

If red:

* Wrong cable selected
* Interface problem
* Device still booting

---

# Step 7 — Test Communication Using Ping

## Procedure in Cisco Packet Tracer

### Open PC0

1. Double-click:

```text
PC0
```

---

### Open Desktop Tab

Click:

```text
Desktop
```

---

### Open Command Prompt

Click:

```text
Command Prompt
```

A terminal window will appear.

---

## Run Ping Command

```bash
ping 192.168.1.2
```

---

# Expected Output

```text
Pinging 192.168.1.2 with 32 bytes of data:

Reply from 192.168.1.2: bytes=32 time<1ms TTL=128
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128

Ping statistics for 192.168.1.2:
Packets: Sent = 4, Received = 4, Lost = 0
```

---

# Understanding the Output

| Term       | Meaning                  |
| ---------- | ------------------------ |
| Reply from | Destination reachable    |
| bytes=32   | Packet size              |
| time<1ms   | Delay/latency            |
| TTL        | Time To Live value       |
| Lost = 0   | Successful communication |

---

# Troubleshooting

# Problem 1 — Request Timed Out

## Causes

* Wrong IP address
* Wrong subnet mask
* Cable not connected
* Incorrect cable type

---

## Solution

Check:

* IP addresses
* Subnet masks
* Cable type
* Green connection lights

---

# Problem 2 — Red Cable Indicator

## Causes

* Wrong cable used
* Interface issue

---

## Solution

Use:

```text
Copper Cross-Over
```

---

# Problem 3 — Different Networks

## Example

| PC  | IP          |
| --- | ----------- |
| PC0 | 192.168.1.1 |
| PC1 | 192.168.2.2 |

These PCs cannot communicate directly without a router.

---

# Important Concepts Learned

| Concept             | Explanation                   |
| ------------------- | ----------------------------- |
| LAN                 | Local Area Network            |
| IP Address          | Unique device identifier      |
| Subnet Mask         | Defines network boundary      |
| ICMP                | Protocol used by ping         |
| Packet Transmission | Data transfer between systems |

---

# Viva Questions and Answers

# Q1. What is an IP address?

An IP address is a logical address used to identify a device in a network.

---

# Q2. What is the purpose of subnet mask?

A subnet mask identifies the network and host portions of an IP address.

---

# Q3. Which command is used to test connectivity?

```bash
ping
```

---

# Q4. Which protocol is used by ping?

ICMP (Internet Control Message Protocol).

---

# Q5. Why do we use a cross-over cable?

A cross-over cable is used to directly connect similar devices like PC-to-PC.

---

# Q6. What happens if subnet masks are different?

Devices may fail to communicate properly.

---

# Q7. What is TTL?

TTL (Time To Live) prevents packets from circulating forever in a network.

---

# Advantages of PC to PC Communication

* Simple communication
* Easy file sharing
* Basic networking understanding
* Foundation for advanced networking

---

# Limitations

* Limited scalability
* No centralized management
* Not suitable for large networks

---

# Real-Life Applications

* Home networks
* Small office communication
* Direct device file transfer
* Gaming networks

---

# Result

The communication between two PCs was successfully established and verified using the `ping` command in Cisco Packet Tracer.

---

# Conclusion

In this practical, we learned:

* How to connect two PCs directly
* How to assign IP addresses
* How to configure subnet masks
* How to test communication using ping
* Basic troubleshooting techniques

This practical forms the foundation of computer networking and helps in understanding how devices communicate within a LAN.

---

# Quick Revision Summary

| Task               | Action                     |
| ------------------ | -------------------------- |
| Add devices        | Use End Devices            |
| Connect PCs        | Copper Cross-Over          |
| Configure IPs      | Desktop → IP Configuration |
| Test communication | `ping` command             |
| Successful output  | Reply received             |

---

# Commands Used

## Ping Command

```bash
ping 192.168.1.2
```

---

# Recommended Practice Exercises

1. Change IP addresses and test again.
2. Try wrong subnet masks and observe results.
3. Add more PCs and create a small LAN.
4. Observe packet flow in Simulation Mode.
5. Use automatic connection option.

---

# Bonus Learning

## Simulation Mode

Packet Tracer provides a Simulation Mode where you can visually observe:

* ICMP packets
* ARP requests
* Packet movement
* Data flow between devices

This helps in understanding real packet transmission behavior.

---

# End of Practical 1
