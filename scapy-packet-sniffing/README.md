# 🐍 Scapy Packet Sniffing & ICMP Analysis

## 📌 Project Overview
This project demonstrates hands-on packet sniffing and analysis using **Scapy**.  
The goal is to capture live network traffic, filter ICMP packets, and inspect packet details at different layers.

All activities were performed in a controlled lab environment.

---

## 🛠️ Tools Used
- Scapy
- Linux (Kali)
- Wireshark
- Ping (ICMP traffic generation)

---

## 🔎 Commands, Actions & Explanations

### 1️⃣ Gain Root Privileges
sudo su  

This command is required because packet sniffing needs administrative (root) privileges to access network interfaces.

---

### 2️⃣ Launch Scapy Interactive Shell
scapy  

This starts the Scapy interactive environment, allowing packet sniffing, storage, and inspection.

---

### 3️⃣ Start Packet Sniffing
sniff()  

This captures all packets on the default network interface continuously until manually stopped.

---

### 4️⃣ Generate ICMP Traffic
ping google.com  

This sends ICMP Echo Request packets to Google, generating network traffic for Scapy to capture.

---

### 5️⃣ Store Captured Packets & View Summary
paro = _  
paro.summary()  

- `_` represents the last captured output in the Scapy shell  
- Packets are stored in the variable `paro`  
- `summary()` displays a brief, one-line overview of each captured packet

---

### 6️⃣ Sniff Traffic on a Specific Interface
sniff(iface="br-internal")  

This captures packets only from the `br-internal` network interface, commonly used in virtualized or internal network setups.

---

### 7️⃣ Store Interface-Specific Packets
paro2 = _  
paro2.summary()  

The captured packets from the `br-internal` interface are stored and summarized for analysis.

---

### 8️⃣ Filter ICMP Traffic and Limit Capture
sniff(iface="br-internal", filter="icmp", count=5)  

- Captures only ICMP packets  
- Listens on `br-internal` interface  
- Stops automatically after capturing 5 packets  

This reduces noise and focuses on specific traffic.

---

### 9️⃣ Generate ICMP Traffic to Local Host
ping 10.6.6.23  

This sends ICMP packets to a local network host to test filtered packet capture.

---

### 🔟 Inspect Captured ICMP Packets
paro3 = _  
paro3.summary()  
paro3[3]  

- Stores filtered ICMP packets  
- Displays a summary of captured packets  
- `paro3[3]` shows the full details of the 4th packet, including protocol layers, source/destination IPs, and payload data

---

## 🧠 Key Takeaways
- Packet sniffing requires root privileges
- Scapy can capture, store, and analyze live network traffic
- Filtering traffic improves clarity and focus
- ICMP traffic is useful for testing packet capture
- Individual packets can be inspected at multiple protocol layers

---

## ⚠️ Ethical Disclaimer
This project was conducted **strictly in a controlled lab environment** for educational and learning purposes only.
