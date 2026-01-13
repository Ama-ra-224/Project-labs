# 🔍 Nmap & SMB Enumeration Practice

## 📌 Project Overview
This project documents hands-on practice with **Nmap scanning and SMB enumeration** performed in a controlled lab environment.

The objective of this exercise is to understand network reconnaissance techniques including host discovery, operating system detection, service enumeration, and SMB share analysis.


---

## 🛠️ Tools Used
- Nmap
- Nmap Scripting Engine (NSE)
- smbclient
- Kali Linux

---

## 🌐 Target Information
- **Network Range:** 10.6.6.0/24  
- **Target Host:** 10.6.6.23  

---

## 🔎 Commands, Purpose & Explanation

```bash
# 1. Host Discovery
# Discovers active/live hosts within the specified subnet without scanning ports.
nmap -sn 10.6.6.0/24

# 2. Operating System Detection
# Attempts to identify the operating system running on the target host.
sudo nmap -O 10.6.6.23

# 3. Service & Version Enumeration
# Scans FTP port 21, detects running service versions, enables aggressive scanning,
# and uses a faster timing template.
nmap -p21 -sV -A -T4 10.6.6.23

# 4. SMB Share Enumeration
# Uses an Nmap NSE script to enumerate available SMB shares on the target system.
nmap --script smb-enum-shares.nse -p445 10.6.6.23

# 5. Anonymous SMB Access Test
# Attempts to access the SMB print$ share without authentication.
smbclient //10.6.6.23/print$ -N

