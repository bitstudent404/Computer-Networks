# Linux Networking & System Commands Cheat Sheet

> Focused on modern Linux networking and system administration commands for quick revision.

---

# 1. Connectivity Testing

## `ping`

**Definition:** Tests connectivity between your Linux system and another host.

### Syntax

```bash
ping <host>
```

### Example

```bash
ping google.com
```

### Useful Options

```bash
ping -c 4 google.com     # Send only 4 packets
ping -i 2 google.com     # Interval of 2 seconds
```

### What You Learn

* Network connectivity
* Packet loss
* Latency
* ICMP protocol basics

---

## `mtr`

**Definition:** Combines `ping` and `traceroute` for real-time diagnostics.

### Install

```bash
sudo apt install mtr -y
```

### Example

```bash
mtr google.com
```

### What You Learn

* Packet loss per hop
* Route stability
* Network bottlenecks

---

## `traceroute`

**Definition:** Displays the route packets take to reach a destination.

### Install

```bash
sudo apt install traceroute -y
```

### Example

```bash
traceroute google.com
```

### What You Learn

* Routing path
* Hop-by-hop communication
* Latency at each router

---

# 2. DNS & Name Resolution

## `nslookup`

**Definition:** Queries DNS servers for domain or IP information.

### Install

```bash
sudo apt install dnsutils -y
```

### Example

```bash
nslookup google.com
```

### Reverse Lookup

```bash
nslookup 8.8.8.8
```

---

## `dig`

**Definition:** Advanced DNS lookup utility.

### Example

```bash
dig google.com
```

### MX Records

```bash
dig google.com MX
```

### Reverse DNS

```bash
dig -x 8.8.8.8
```

### What You Learn

* DNS records
* TTL values
* DNS troubleshooting

---

# 3. IP Address & Network Interface Commands

## `ip addr`

**Definition:** Displays and manages IP addresses on interfaces.

### Example

```bash
ip addr show
```

### Add Temporary IP

```bash
sudo ip addr add 192.168.1.100/24 dev eth0
```

### Remove IP

```bash
sudo ip addr del 192.168.1.100/24 dev eth0
```

### Modern Replacement For

* `ifconfig`

---

## `ip link`

**Definition:** Displays and manages network interfaces.

### Example

```bash
ip link show
```

### Bring Interface Up

```bash
sudo ip link set eth0 up
```

### Bring Interface Down

```bash
sudo ip link set eth0 down
```

---

## `ifconfig` (Legacy)

**Definition:** Older command for interface configuration.

### Install

```bash
sudo apt install net-tools -y
```

### Example

```bash
ifconfig
```

### Note

Prefer modern `ip` commands.

---

## `hostname`

**Definition:** Displays or sets the system hostname.

### Example

```bash
hostname
```

### Set Temporary Hostname

```bash
sudo hostname mylinux
```

---

## `ip link show` (MAC Address)

**Definition:** Shows MAC addresses of interfaces.

### Example

```bash
ip link show
```

### Output Example

```text
link/ether 08:00:27:12:34:56
```

---

# 4. Routing & ARP

## `route`

**Definition:** Displays or modifies routing tables.

### Example

```bash
route -n
```

### Modern Alternative

```bash
ip route
```

---

## `ip route`

**Definition:** Modern routing table command.

### Example

```bash
ip route
```

### Add Route

```bash
sudo ip route add 10.0.0.0/24 via 192.168.1.1
```

### Delete Route

```bash
sudo ip route del 10.0.0.0/24
```

---

## `arp -a`

**Definition:** Displays ARP cache table.

### Example

```bash
arp -a
```

### Modern Alternative

```bash
ip neigh
```

### What You Learn

* IP ↔ MAC mappings
* LAN communication
* ARP protocol basics

---

# 5. Network Connections & Ports

## `netstat`

**Definition:** Displays network connections and listening ports.

### Install

```bash
sudo apt install net-tools -y
```

### Example

```bash
netstat -tulnp
```

### Flags

| Flag | Meaning      |
| ---- | ------------ |
| `-t` | TCP          |
| `-u` | UDP          |
| `-l` | Listening    |
| `-n` | Numeric      |
| `-p` | Process info |

---

## `ss`

**Definition:** Modern replacement for `netstat`.

### Example

```bash
ss -tulnp
```

### What You Learn

* Open ports
* Active connections
* Listening services
* Socket statistics

---

# 6. Packet Capture & Traffic Analysis

## `tcpdump`

**Definition:** Captures and analyzes network packets.

### Install

```bash
sudo apt install tcpdump -y
```

### Example

```bash
sudo tcpdump -i eth0
```

### Capture ICMP Packets

```bash
sudo tcpdump icmp
```

### Save Packets

```bash
sudo tcpdump -w capture.pcap
```

### What You Learn

* Packet structures
* TCP/IP protocols
* Real network traffic

---

# 7. Remote Access & File Transfer

## `ssh`

**Definition:** Securely connects to remote Linux systems.

### Install

```bash
sudo apt install openssh-client openssh-server -y
```

### Example

```bash
ssh user@192.168.1.10
```

### Generate SSH Key

```bash
ssh-keygen
```

---

## `scp`

**Definition:** Securely copies files between systems.

### Example

```bash
scp file.txt user@192.168.1.10:/home/user/
```

### Copy Directory

```bash
scp -r folder user@192.168.1.10:/home/user/
```

---

# 8. Web Requests & Downloads

## `curl`

**Definition:** Transfers data from or to a server.

### Install

```bash
sudo apt install curl -y
```

### Example

```bash
curl https://example.com
```

### Download File

```bash
curl -O https://example.com/file.zip
```

---

## `wget`

**Definition:** Downloads files from the internet.

### Install

```bash
sudo apt install wget -y
```

### Example

```bash
wget https://example.com/file.zip
```

### Resume Download

```bash
wget -c https://example.com/file.zip
```

---

# 9. Process & System Monitoring

## `ps aux`

**Definition:** Displays all running processes.

### Example

```bash
ps aux
```

### Search Process

```bash
ps aux | grep ssh
```

---

## `kill`

**Definition:** Terminates a process using PID.

### Example

```bash
kill 1234
```

### Force Kill

```bash
kill -9 1234
```

---

## `top`

**Definition:** Displays real-time system and process information.

### Example

```bash
top
```

### What You Learn

* CPU usage
* RAM usage
* Running processes
* System load

---

## `uname -a`

**Definition:** Displays Linux kernel and system information.

### Example

```bash
uname -a
```

### Output Includes

* Kernel version
* Architecture
* Hostname
* OS details

---

## `lscpu`

**Definition:** Displays CPU architecture information.

### Example

```bash
lscpu
```

### What You Learn

* CPU cores
* Threads
* Virtualization support
* Cache details

---

# 10. Samba & Windows Networking Alternatives

## `smbclient`

**Definition:** Accesses Windows shared resources from Linux.

### Install

```bash
sudo apt install smbclient -y
```

### Example

```bash
smbclient -L //192.168.1.10
```

### Linux Alternative For

* `net view`

---

## `nmblookup`

**Definition:** NetBIOS lookup utility.

### Install

```bash
sudo apt install samba-common-bin -y
```

### Example

```bash
nmblookup -A 192.168.1.10
```

### Linux Alternative For

* `nbtstat`

---

# 11. Essential Installation Bundle

## Install Everything Together

```bash
sudo apt update

sudo apt install -y \
net-tools \
iproute2 \
dnsutils \
iputils-ping \
traceroute \
mtr \
tcpdump \
wireshark \
curl \
wget \
openssh-client \
openssh-server \
samba-common-bin \
smbclient
```

---

# 12. Modern Linux Networking Commands vs Legacy Commands

| Modern Command | Legacy Command | Purpose           |
| -------------- | -------------- | ----------------- |
| `ip addr`      | `ifconfig`     | Show IP addresses |
| `ip link`      | `ifconfig`     | Manage interfaces |
| `ip route`     | `route`        | Routing tables    |
| `ss`           | `netstat`      | Network sockets   |
| `ip neigh`     | `arp -a`       | ARP table         |
| `dig`          | `nslookup`     | DNS lookup        |

---

# 13. Beginner Practice Workflow

## Step 1 — Check Interface

```bash
ip link show
```

---

## Step 2 — Check IP Address

```bash
ip addr show
```

---

## Step 3 — Test Internet

```bash
ping 8.8.8.8
```

---

## Step 4 — Test DNS

```bash
ping google.com
```

---

## Step 5 — Check Routes

```bash
ip route
```

---

## Step 6 — Check Open Ports

```bash
ss -tulnp
```

---

## Step 7 — Capture Packets

```bash
sudo tcpdump -i eth0
```

---

## Step 8 — SSH Into Another Machine

```bash
ssh user@192.168.1.10
```

---

# 14. Most Important Commands To Memorize

| Task              | Command      |
| ----------------- | ------------ |
| Show IP           | `ip addr`    |
| Show interfaces   | `ip link`    |
| Show routes       | `ip route`   |
| DNS lookup        | `dig`        |
| Test connectivity | `ping`       |
| Trace route       | `traceroute` |
| View ports        | `ss -tulnp`  |
| Capture packets   | `tcpdump`    |
| Remote login      | `ssh`        |
| File transfer     | `scp`        |
| Monitor processes | `top`        |

---

# 15. Quick Troubleshooting Order

## 1. Check Interface

```bash
ip link
```

## 2. Check IP

```bash
ip addr
```

## 3. Check Gateway

```bash
ip route
```

## 4. Ping Gateway

```bash
ping 192.168.1.1
```

## 5. Ping Public IP

```bash
ping 8.8.8.8
```

## 6. Test DNS

```bash
dig google.com
```

## 7. Check Open Ports

```bash
ss -tulnp
```

---

# 16. Pro Revision Tips

* Prefer `ip` and `ss` over older commands.
* Learn the difference between TCP, UDP, and ICMP.
* Use `tcpdump` with Wireshark for packet analysis.
* Practice networking using Virtual Machines.
* Observe traffic while using `ping`, `curl`, and `ssh`.
* Remember: networking becomes easier once you visualize packet flow.

---

# 17. Fast Revision Summary

| Command      | Main Use             |
| ------------ | -------------------- |
| `ping`       | Connectivity testing |
| `traceroute` | Route tracking       |
| `mtr`        | Live diagnostics     |
| `dig`        | DNS analysis         |
| `ip addr`    | IP addresses         |
| `ip route`   | Routing table        |
| `ss`         | Open ports           |
| `tcpdump`    | Packet capture       |
| `ssh`        | Remote access        |
| `scp`        | Secure file copy     |
| `top`        | System monitoring    |
| `ps aux`     | Process listing      |

---

# Final Advice

Master these commands practically instead of memorizing only syntax.

Best learning method:

1. Run the command
2. Observe the output
3. Capture packets in `tcpdump`
4. Visualize traffic in Wireshark
5. Understand which protocol is being used

That approach builds real networking intuition.
