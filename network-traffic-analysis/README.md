# 📡 Network Configuration & Traffic Capture Practice

## 📌 Project Overview
This project documents hands-on practice with **network configuration analysis** and **network traffic capture** in a controlled lab environment.

The objective of this exercise is to understand:
- Network interface configuration
- Routing table inspection
- DNS configuration
- Packet capture using tcpdump
- Traffic analysis using Wireshark

All activities were performed **ethically and with proper authorization**.

---

## 🛠️ Tools Used
- Linux networking utilities
- tcpdump
- Wireshark
- Kali Linux

---

## 🔎 Commands, Purpose & Explanation

```bash
# 1. Display network interface configuration
# Shows available network interfaces, IP addresses, and MAC addresses.
ifconfig

# 2. Display routing table
# Shows how packets are routed within the network and default gateways.
ip route

# 3. View DNS configuration
# Displays configured DNS servers used for name resolution.
cat /etc/resolv.conf

# 4. Capture network traffic
# Captures all traffic on the eth0 interface and saves it to a PCAP file.
sudo tcpdump -i eth0 -s 0 -w cyber.pcap

# 5. Analyze captured traffic
# Opens the PCAP file in Wireshark for graphical traffic analysis.
wireshark cyber.pcap
