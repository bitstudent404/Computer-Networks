# Practical 4 — Perform Initial Switch Configuration in Cisco Packet Tracer

# Aim

To perform the initial configuration of a Cisco Switch using Cisco Packet Tracer.

---

# Objective

The objective of this practical is to:

* Access Cisco switch CLI
* Configure hostname
* Configure passwords
* Configure banner message
* Configure management IP address
* Save configuration
* Verify switch settings
* Understand basic switch administration

---

# Devices Required

| Device                        | Quantity |
| ----------------------------- | -------- |
| 2960 Switch                   | 1        |
| PC                            | 1        |
| Copper Straight Through Cable | 1        |

---

# Software Required

| Software            | Purpose            |
| ------------------- | ------------------ |
| Cisco Packet Tracer | Network simulation |

---

# Theory

## What is a Switch?

A switch is a Layer 2 networking device used to connect devices in a LAN.

Functions of a switch:

* Learns MAC addresses
* Forwards frames intelligently
* Reduces collisions
* Improves network efficiency
* Enables communication inside LAN

---

# Why Configure a Switch?

Initial switch configuration is important because it helps:

* Identify the switch
* Secure administrative access
* Configure remote management
* Save configurations permanently
* Manage the network efficiently

---

# Network Topology

```text
PC0 -------- Switch0
```

---

# Cisco IOS Modes

| Mode                         | Prompt                 | Purpose                 |
| ---------------------------- | ---------------------- | ----------------------- |
| User EXEC Mode               | `Switch>`              | Basic commands          |
| Privileged EXEC Mode         | `Switch#`              | Administrative commands |
| Global Configuration Mode    | `Switch(config)#`      | Device configuration    |
| Interface Configuration Mode | `Switch(config-if)#`   | Interface configuration |
| Line Configuration Mode      | `Switch(config-line)#` | Password configuration  |

---

# Step-by-Step Procedure

# Step 1 — Open Cisco Packet Tracer

1. Open Cisco Packet Tracer.
2. Wait for the workspace to load completely.

---

# Step 2 — Add Switch

## Procedure

1. Go to the bottom-left panel.
2. Click:

```text
Network Devices
```

3. Select:

```text
Switches
```

4. Choose:

```text
2960 Switch
```

5. Drag the switch into the workspace.

The switch will appear as:

```text
Switch0
```

---

# Step 3 — Add PC

## Procedure

1. Click:

```text
End Devices
```

2. Select:

```text
PC
```

3. Drag the PC into the workspace.

The device will appear as:

```text
PC0
```

---

# Step 4 — Connect PC to Switch

# Open Connections Menu

1. Click:

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

# Connect Devices

Connect:

| Device  | Port            |
| ------- | --------------- |
| PC0     | FastEthernet0   |
| Switch0 | FastEthernet0/1 |

---

# Verify Connection

After a few seconds:

* Green indicators should appear.

Green means:

```text
Physical Connection Active
```

---

# Step 5 — Open Switch CLI

# Open Switch

Double-click:

```text
Switch0
```

---

# Open CLI Tab

Click:

```text
CLI
```

---

# Initial Configuration Dialog

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

# User EXEC Mode

You will now see:

```text
Switch>
```

This is called:

```text
User EXEC Mode
```

It provides limited access.

---

# Step 6 — Enter Privileged EXEC Mode

Type:

```bash
enable
```

Now the prompt changes to:

```text
Switch#
```

This is:

```text
Privileged EXEC Mode
```

This mode provides administrative access.

---

# Step 7 — Enter Global Configuration Mode

Type:

```bash
configure terminal
```

OR

```bash
conf t
```

Prompt becomes:

```text
Switch(config)#
```

This mode allows device configuration.

---

# Step 8 — Configure Hostname

# Command

```bash
hostname LAB_SWITCH
```

Prompt changes to:

```text
LAB_SWITCH(config)#
```

---

# Purpose

Hostname helps identify the switch in the network.

---

# Step 9 — Configure Enable Password

# Command

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

Prompt becomes:

```text
LAB_SWITCH(config-line)#
```

---

# Set Password

```bash
password admin
```

---

# Enable Login

```bash
login
```

---

# Exit Line Mode

```bash
exit
```

---

# Purpose

The console password secures physical console access.

---

# Step 11 — Configure Banner Message

# Command

```bash
banner motd # Unauthorized Access Prohibited #
```

---

# Purpose

Displays a warning message before login.

---

# Step 12 — Configure Management IP Address

# Enter VLAN Interface

```bash
interface vlan 1
```

---

# Assign IP Address

```bash
ip address 192.168.1.10 255.255.255.0
```

---

# Enable Interface

```bash
no shutdown
```

---

# Exit Interface Mode

```bash
exit
```

---

# Why VLAN 1?

Switches use VLAN interfaces for management configuration.

VLAN 1 is the default management VLAN.

---

# Step 13 — Configure PC IP Address

# Open PC

Double-click:

```text
PC0
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

# Configure IP Settings

| Field       | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.1.2   |
| Subnet Mask | 255.255.255.0 |

---

# Step 14 — Test Connectivity

# Open Command Prompt

```text
PC0 → Desktop → Command Prompt
```

---

# Run Ping Command

```bash
ping 192.168.1.10
```

---

# Expected Output

```text
Reply from 192.168.1.10
```

This confirms successful communication.

---

# Step 15 — Save Configuration

# Return to Privileged Mode

```bash
end
```

OR

```bash
exit
```

---

# Save Running Configuration

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

# Verification Commands

# Show Running Configuration

```bash
show running-config
```

Displays current active configuration.

---

# Show IP Interface Brief

```bash
show ip interface brief
```

Displays interface IP information.

---

# Show VLAN Information

```bash
show vlan brief
```

Displays VLAN details.

---

# Show MAC Address Table

```bash
show mac address-table
```

Displays learned MAC addresses.

---

# Full Command Sequence

```bash
enable
configure terminal
hostname LAB_SWITCH
enable password cisco
line console 0
password admin
login
exit
banner motd # Unauthorized Access Prohibited #
interface vlan 1
ip address 192.168.1.10 255.255.255.0
no shutdown
end
write memory
```

---

# Important Concepts Learned

| Concept          | Explanation                |
| ---------------- | -------------------------- |
| Switch           | Layer 2 device             |
| CLI              | Command Line Interface     |
| VLAN Interface   | Management interface       |
| IOS              | Cisco operating system     |
| Hostname         | Device identity            |
| Console Password | Secures console access     |
| Management IP    | Used for switch management |

---

# Troubleshooting

# Problem 1 — Ping Fails

## Causes

* Wrong IP address
* Interface shutdown
* Incorrect cable
* Wrong subnet mask

---

## Solution

Check:

* IP configuration
* `no shutdown`
* Cable type
* Green indicators

---

# Problem 2 — CLI Not Opening

## Cause

Device not selected properly.

---

## Solution

Double-click switch and open CLI tab again.

---

# Problem 3 — Configuration Lost After Restart

## Cause

Configuration not saved.

---

## Solution

Run:

```bash
copy running-config startup-config
```

---

# Advantages of Switches

* Faster communication
* Intelligent forwarding
* Reduced collisions
* Better LAN performance
* Supports multiple devices

---

# Applications of Switches

* Computer labs
* Offices
* Schools
* Enterprise networks
* Data centers

---

# Viva Questions and Answers

# Q1. What is a switch?

A switch is a Layer 2 networking device used to connect devices in a LAN.

---

# Q2. Which command enters privileged mode?

```bash
enable
```

---

# Q3. Which command enters global configuration mode?

```bash
configure terminal
```

---

# Q4. What is the purpose of hostname?

Hostname identifies the networking device.

---

# Q5. What does `no shutdown` do?

Enables the interface.

---

# Q6. Which command saves configuration?

```bash
write memory
```

---

# Q7. What is VLAN 1?

Default management VLAN on Cisco switches.

---

# Q8. Which OSI layer does switch operate on?

Layer 2.

---

# Result

Initial switch configuration was successfully performed and verified using Cisco Packet Tracer.

---

# Conclusion

In this practical, we learned:

* Basic Cisco switch configuration
* CLI navigation
* Password configuration
* Hostname configuration
* VLAN management IP setup
* Saving configuration
* Connectivity testing using ping

This practical forms the foundation of Cisco switch administration and LAN management.

---

# Quick Revision Summary

| Task                       | Command           |
| -------------------------- | ----------------- |
| Enter privileged mode      | `enable`          |
| Enter global configuration | `conf t`          |
| Configure hostname         | `hostname NAME`   |
| Configure password         | `enable password` |
| Configure VLAN IP          | `ip address`      |
| Enable interface           | `no shutdown`     |
| Save configuration         | `write memory`    |

---

# Bonus Learning

Cisco switches run:

Cisco IOS (Internetwork Operating System)

which is widely used in:

* Enterprise networking
* Data centers
* ISPs
* Campus networks
* Corporate infrastructure

Learning Cisco CLI is one of the most important networking skills.

---

# End of Practical 4
