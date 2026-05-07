# Practical 8 — To Perform Remote Desktop Sharing Within LAN Connection in Cisco Packet Tracer

# Aim

To perform remote desktop sharing within a LAN connection using Cisco Packet Tracer.

---

# Objective

The objective of this practical is to:

- Understand remote desktop communication
- Configure LAN connectivity
- Configure IP addresses
- Enable remote services
- Access one PC from another PC
- Test LAN communication

---

# Theory

# What is Remote Desktop Sharing?

Remote Desktop Sharing allows:

```text
One computer to access and control another computer remotely
```

through a network.

---

# Purpose of Remote Desktop

- Remote system administration
- Technical support
- File access
- Remote monitoring
- Centralized management

---

# Real-Life Examples

| Software | Purpose |
|---|---|
| Remote Desktop Protocol (RDP) | Windows remote access |
| TeamViewer | Remote support |
| AnyDesk | Remote desktop |
| VNC | Screen sharing |

---

# Devices Required

| Device | Quantity |
|---|---|
| Switch | 1 |
| PC | 2 |
| Copper Straight Through Cable | 2 |

---

# Network Topology

```text
PC0 -------- Switch0 -------- PC1
```

---

# IP Addressing Scheme

| Device | IP Address | Subnet Mask |
|---|---|---|
| PC0 | 192.168.1.2 | 255.255.255.0 |
| PC1 | 192.168.1.3 | 255.255.255.0 |

---

# Step-by-Step Procedure

# Step 1 — Open Cisco Packet Tracer

1. Open Cisco Packet Tracer.
2. Wait for workspace to load.

---

# Step 2 — Add Devices

# Add Switch

1. Go to:

```text
Network Devices → Switches
```

2. Select:

```text
2960 Switch
```

3. Drag into workspace.

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
PC0 -------- Switch0 -------- PC1
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

# Connect PC0 to Switch

| Device | Port |
|---|---|
| PC0 | FastEthernet0 |
| Switch0 | FastEthernet0/1 |

---

# Connect PC1 to Switch

| Device | Port |
|---|---|
| PC1 | FastEthernet0 |
| Switch0 | FastEthernet0/2 |

---

# Wait for Green Links

After few seconds:
- all links should become green

Meaning:
- physical connectivity active

---

# Step 5 — Configure PC0 IP Address

Open:

```text
PC0 → Desktop → IP Configuration
```

Set:

| Field | Value |
|---|---|
| IP Address | 192.168.1.2 |
| Subnet Mask | 255.255.255.0 |

---

# Step 6 — Configure PC1 IP Address

Open:

```text
PC1 → Desktop → IP Configuration
```

Set:

| Field | Value |
|---|---|
| IP Address | 192.168.1.3 |
| Subnet Mask | 255.255.255.0 |

---

# Why Same Network?

Both PCs are inside same LAN.

Therefore:
- same subnet is required

---

# Step 7 — Verify Connectivity Using Ping

# From PC0

Open:

```text
Desktop → Command Prompt
```

Run:

```bash
ping 192.168.1.3
```

---

# Expected Output

```text
Reply from 192.168.1.3
```

---

# From PC1

Run:

```bash
ping 192.168.1.2
```

---

# Meaning

Both systems can communicate successfully.

---

# Step 8 — Open Remote Desktop

# On PC0

Go to:

```text
Desktop
```

---

# Open Remote Desktop

Click:

```text
Remote Desktop
```

---

# Enter Target IP Address

Type:

```text
192.168.1.3
```

---

# Click Connect

Connection request will be sent to PC1.

---

# What Happens?

PC0 attempts to:
- establish remote session
- communicate with PC1
- share desktop access

This simulates remote desktop communication inside LAN.

---

# Step 9 — Verify Remote Communication

If properly connected:
- remote session establishes
- communication successful

---

# Important Concepts Learned

| Concept | Explanation |
|---|---|
| LAN | Local Area Network |
| Remote Access | Access another system remotely |
| IP Address | Device identity |
| Switch | Connects devices |
| Remote Desktop | Remote system control |

---

# Verification Commands

# Check Connectivity

```bash
ping 192.168.1.3
```

---

# Check PC Configuration

```bash
ipconfig
```

---

# Troubleshooting

# Problem 1 — Ping Fails

## Causes

- Wrong IP address
- Wrong subnet mask
- Cable issue

---

# Solution

Check:
- IP configuration
- Green links
- Correct cable

---

# Problem 2 — Remote Desktop Not Connecting

## Causes

- Wrong target IP
- Connectivity failure

---

# Solution

Verify:
- successful ping
- correct IP address

---

# Problem 3 — Red Link

## Solution

- reconnect cable
- wait few seconds
- use Straight Through cable

---

# Applications of Remote Desktop

- IT support
- Remote troubleshooting
- Office administration
- Network management
- Server management

---

# Advantages

- Remote control
- Saves time
- Centralized administration
- Easy troubleshooting

---

# Disadvantages

- Security risks
- Requires network connectivity
- Possible unauthorized access

---

# Viva Questions and Answers

# Q1. What is remote desktop sharing?

Accessing and controlling another computer remotely through network.

---

# Q2. Which network is used here?

```text
LAN
```

---

# Q3. Which command checks connectivity?

```bash
ping
```

---

# Q4. Why are both PCs in same subnet?

To communicate inside same LAN.

---

# Q5. Which device connects PCs?

```text
Switch
```

---

# Q6. What is the purpose of remote desktop?

Remote system access and management.

---

# Q7. What happens if ping fails?

Remote desktop communication also fails.

---

# Result

Remote desktop sharing within LAN connection was successfully implemented and verified using Cisco Packet Tracer.

---

# Conclusion

In this practical, we learned:

- LAN communication
- Remote desktop basics
- IP configuration
- Connectivity testing
- Switch-based networking
- Remote access concepts

This practical demonstrates how systems communicate and share remote access within a local network.

---

# Quick Revision Summary

| Task | Action |
|---|---|
| Configure IP | Desktop → IP Configuration |
| Test connectivity | `ping` |
| Open remote desktop | Desktop → Remote Desktop |
| Connect to PC | Enter target IP |

---

# Bonus Learning

Large organizations use remote desktop technologies for:
- remote work
- server management
- cloud administration
- technical support

Remote administration is a major part of:
- cybersecurity
- system administration
- enterprise networking

---

# End of Practical 8