# Practical 6 — To Implement Client Server Network in Cisco Packet Tracer

# Aim

To implement a Client-Server Network using Cisco Packet Tracer.

---

# Objective

The objective of this practical is to:

- Understand client-server architecture
- Configure server IP address
- Configure client IP addresses
- Enable network services
- Establish communication between client and server
- Test connectivity using ping and browser

---

# Theory

# What is Client-Server Network?

A Client-Server network is a network model where:

- A central device called Server provides services/resources
- Multiple Clients request and use those services

---

# Examples of Server Services

| Service | Purpose |
|---|---|
| HTTP | Website hosting |
| DNS | Domain name resolution |
| FTP | File transfer |
| DHCP | Automatic IP assignment |
| Email | Mail services |

---

# Client-Server Architecture

```text
          SERVER
             |
        ------------
        |          |
      PC0        PC1
```

---

# Devices Required

| Device | Quantity |
|---|---|
| Server | 1 |
| PC | 2 |
| Switch | 1 |
| Copper Straight Through Cable | 3 |

---

# Network Topology

```text
          Server0
              |
           Switch0
          /       \
       PC0        PC1
```

---

# IP Addressing Scheme

| Device | IP Address | Subnet Mask |
|---|---|---|
| Server0 | 192.168.1.10 | 255.255.255.0 |
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

# Add Server

1. From:

```text
End Devices
```

2. Select:

```text
Server
```

3. Drag into workspace.

---

# Step 3 — Connect Devices

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
| PC1 | FastEthernet0 |
| Switch0 | FastEthernet0/2 |

---

| Device | Port |
|---|---|
| Server0 | FastEthernet0 |
| Switch0 | FastEthernet0/3 |

---

# Expected Topology

```text
          Server0
              |
           Switch0
          /       \
       PC0        PC1
```

---

# Step 4 — Configure Server IP Address

# Open Server

Double-click:

```text
Server0
```

---

# Open Desktop Tab

Click:

```text
Desktop
```

---

# Open IP Configuration

Click:

```text
IP Configuration
```

---

# Configure IP

| Field | Value |
|---|---|
| IP Address | 192.168.1.10 |
| Subnet Mask | 255.255.255.0 |

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

# Step 7 — Verify Physical Connections

Wait a few seconds.

All links should turn:

```text
Green
```

Meaning:
- Physical connectivity active

---

# Step 8 — Test Connectivity Using Ping

# From PC0

Open:

```text
Desktop → Command Prompt
```

Run:

```bash
ping 192.168.1.10
```

---

# Expected Output

```text
Reply from 192.168.1.10
```

---

# Test from PC1

```bash
ping 192.168.1.10
```

---

# Meaning

Clients can successfully communicate with server.

---

# Step 9 — Enable HTTP Service on Server

# Open Server

Double-click:

```text
Server0
```

---

# Open Services Tab

Click:

```text
Services
```

---

# Select HTTP

Click:

```text
HTTP
```

---

# Enable HTTP Service

Turn:

```text
HTTP → ON
```

---

# Purpose

The server can now host webpages.

---

# Step 10 — Access Server Website from Client

# Open Web Browser on PC0

Go to:

```text
Desktop → Web Browser
```

---

# Enter Server IP

```text
http://192.168.1.10
```

---

# Expected Result

Default Cisco Packet Tracer webpage appears.

---

# What Happened?

- Client requested webpage
- Server responded using HTTP protocol

This demonstrates:
- Client-server communication
- Web service hosting

---

# Step 11 — Save Packet Tracer File

1. Click:

```text
File → Save
```

2. Save practical.

---

# Important Concepts Learned

| Concept | Explanation |
|---|---|
| Client | Requests services |
| Server | Provides services |
| HTTP | Web communication protocol |
| LAN | Local Area Network |
| Switch | Connects devices |

---

# Real-Life Examples

| Client | Server |
|---|---|
| Browser | Web Server |
| Gmail App | Google Mail Server |
| WhatsApp App | WhatsApp Server |
| YouTube App | YouTube Server |

---

# Verification Commands

# Ping Server

```bash
ping 192.168.1.10
```

---

# Check Connectivity

```bash
ipconfig
```

---

# Troubleshooting

# Problem 1 — Ping Fails

## Causes

- Wrong IP address
- Wrong cable
- Devices in different subnet

---

# Solution

Check:
- IP addresses
- Subnet masks
- Cable type
- Green links

---

# Problem 2 — Webpage Not Opening

## Causes

- HTTP service OFF
- Wrong IP entered

---

# Solution

Check:
- Services → HTTP → ON
- Correct server IP

---

# Problem 3 — Red Links

## Solution

- Reconnect cable
- Wait few seconds
- Use Straight Through cable

---

# Advantages of Client-Server Network

- Centralized management
- Better security
- Resource sharing
- Easy backup
- Better control

---

# Disadvantages

- Server failure affects clients
- Costly server setup
- Requires administration

---

# Applications

- Websites
- Banking systems
- College networks
- Cloud computing
- Enterprise networks

---

# Viva Questions and Answers

# Q1. What is a client?

A device that requests services from server.

---

# Q2. What is a server?

A device that provides services/resources to clients.

---

# Q3. What protocol is used for websites?

```text
HTTP
```

---

# Q4. Which device connects all systems in LAN?

```text
Switch
```

---

# Q5. Which command checks connectivity?

```bash
ping
```

---

# Q6. Why do all devices use same subnet here?

Because all devices are inside same LAN.

---

# Q7. What is the role of HTTP service?

To host webpages for clients.

---

# Result

Client-server network was successfully implemented and communication between clients and server was verified.

---

# Conclusion

In this practical, we learned:

- Client-server architecture
- IP configuration
- HTTP service configuration
- LAN communication
- Connectivity testing
- Web access using browser

This practical demonstrates how real networks provide centralized services to users.

---

# Quick Revision Summary

| Task | Action |
|---|---|
| Add server | End Devices → Server |
| Configure IP | Desktop → IP Configuration |
| Enable HTTP | Services → HTTP → ON |
| Test connectivity | `ping` |
| Open webpage | Web Browser |

---

# Bonus Learning

Most modern Internet services work on client-server model.

Examples:
- Google
- YouTube
- Instagram
- Netflix
- Online games

Your phone/computer acts as:
```text
Client
```

while company systems act as:
```text
Servers
```

---

# End of Practical 6