# Cybersecurity & Ethical Hacking Internship 
**Cybersecurity & Ethical Hacking Internship - Task 1**

**Company:** ApexPlanet Software Pvt. Ltd.  
**Domain:** Cybersecurity & Ethical Hacking  
**Task:** Foundations of Cybersecurity & Environment Setup  
**Timeline:** Days 1–12  

---

## 📌 Objective
To establish strong core fundamentals in cybersecurity, networking protocols, cryptographic mechanisms, and Linux administration, while building a secure and isolated virtual penetration testing lab environment.

---

## 🛠️ Lab Environment Setup
- **Virtualization Platform:** Vmware Workstation Pro
- **Attacker Machine:** Kali Linux (Rolling Release)
- **Target Machine:** Metasploitable2 / DVWA (Damn Vulnerable Web App)
- **Network Configuration:** Host-Only Adapter (Isolated Private Lab Network to ensure safety and prevent unauthorized external traffic)

---

## 📖 Key Concepts & Technical Overview

### 1. Cybersecurity Foundations
- **CIA Triad:**
  - **Confidentiality:** Protecting data from unauthorized access through access controls and strong encryption.
  - **Integrity:** Ensuring information remains untampered and authentic using cryptographic hash functions.
  - **Availability:** Guaranteeing systems, networks, and applications remain accessible to authorized users when needed.
- **Threat Types:** Analysis of attack methodologies including Phishing, Malware (Ransomware, Trojans), Denial of Service (DDoS), SQL Injection, and Brute Force attacks.
- **Attack Vectors:** Threat channels across Social Engineering, Vulnerable Wireless Networks, and Insider Threats.

---

### 2. Networking Basics & Fundamentals
- **OSI Model Layers & Functions:**
  1. *Physical Layer:* Bitstream transmission via physical media.
  2. *Data Link Layer:* Node-to-node transfer and MAC addressing.
  3. *Network Layer:* Routing packets across networks using IP addressing.
  4. *Transport Layer:* End-to-end reliability and flow control (TCP/UDP).
  5. *Session Layer:* Managing communication sessions between applications.
  6. *Presentation Layer:* Data translation, formatting, and encryption.
  7. *Application Layer:* End-user interface and network services (HTTP, FTP, SSH).
- **TCP/IP Protocol Suite:**
  - **TCP (Transmission Control Protocol):** Connection-oriented protocol using a 3-way handshake (SYN, SYN-ACK, ACK) to guarantee delivery.
  - **UDP (User Datagram Protocol):** Connectionless, lightweight protocol prioritized for speed without delivery guarantees.
  - **IP, ICMP, ARP:** Protocol stack responsible for packet addressing, control messaging/diagnostics, and resolving IP addresses to physical MAC addresses.
- **DNS & HTTP/HTTPS Deep Dive:**
  - **DNS (Domain Name System):** Resolves human-readable domain names into IP addresses via recursive and authoritative lookups.
  - **HTTP vs HTTPS:** HTTP transmits data in plaintext over port 80. HTTPS encrypts traffic over port 443 using SSL/TLS protocols to secure client-server sessions.
- **IP Addressing, Subnetting, and NAT:**
  - **IP Addressing:** IPv4 (32-bit) and IPv6 (128-bit) structure differentiating public and private address ranges.
  - **Subnetting:** Segmenting networks using Subnet Masks (e.g., CIDR notation `/24`) to optimize performance and security boundaries.
  - **NAT (Network Address Translation):** Maps private internal IP addresses to a public IP to conserve address space and mask internal topology.

---

### 3. Cryptography Basics
- **Symmetric vs Asymmetric Encryption:**
  - **Symmetric:** Uses a single shared key for both encryption and decryption (e.g., AES-256). Fast and suited for bulk data encryption.
  - **Asymmetric:** Uses a mathematically linked key pair—Public Key for encryption and Private Key for decryption (e.g., RSA, ECC).
- **Hashing Algorithms:**
  - One-way deterministic functions generating fixed-length outputs.
  - **MD5 (128-bit):** Legacy algorithm, prone to collision attacks.
  - **SHA-256 (256-bit):** Cryptographically secure standard used for integrity verification and digital signatures.
- **Digital Certificates & SSL/TLS:**
  - **PKI (Public Key Infrastructure):** System of digital certificates and Certificate Authorities (CAs) that authenticate entity identities.
  - **SSL/TLS Handshake:** Secure key-exchange process establishing encrypted symmetric channels for web communication.
- **Hands-On Cryptography:** Practiced symmetric cipher encryption/decryption and integrity verification using OpenSSL via CLI.

---

## 🐧 Linux Commands Cheat-Sheet

### File System Navigation
```bash
pwd                 # Display current working directory
ls -la              # List all files and directories including hidden ones
cd /path/to/dir     # Change directory
mkdir test_folder   # Create a new directory

 ## **Permission & Ownership**      
chmod 755 file.txt  # Change file permissions (Read/Write/Execute)
chown user:group file.txt # Change file owner and group ownership


## Networking Commands    
ip a                # Display IP addresses of all interfaces
ifconfig            # Check network interface details
ping -c 4 <IP>      # Check connectivity to a target IP
netstat -tuln       # Show active listening ports

## Package Management
sudo apt update && sudo apt upgrade -y # Update system repositories
sudo apt install nmap wireshark -y    # Install tools

## AES-256 Encryption & Decryption
openssl enc -aes-256-cbc -pbkdf2 -salt -in secret.txt -out secret.enc     # Encrypt a text file 
openssl enc -d -aes-256-cbc -pbkdf2 -in secret.enc -out decrypted.txt     # Decrypt the file

# SHA-256 Hashing
sha256sum secret.txt     # Generate SHA-256 checksum to verify file integrity. 
```

``                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       **# 🛡️Cybersecurity & Ethical Hacking Internship - Task 2**

**Company:** ApexPlanet Software Pvt. Ltd.  
**Domain:** Cybersecurity & Ethical Hacking  
**Task Name:** Network Security & Scanning  
**Timeline:** Days 13–24  

---

## 📌 Objective
To perform reconnaissance, scanning, network traffic analysis, vulnerability assessment, and configure host-based firewalls in a secure virtual lab environment.

---

## 🛠️ Lab Setup & Target Topology
- **Attacker Machine:** Kali Linux (Rolling Release)
- **Target Machine:** Metasploitable2 / Test VM
- **Network Mode:** Host-Only Private Subnet (Isolated Virtual Lab)
- **Tools Utilized:** Nmap, Tenable Nessus, Wireshark, hping3, iptables, WHOIS, Nslookup

---

## 📖 Key Concepts & Technical Overview

### 1. Reconnaissance (Information Gathering)
- **Passive Reconnaissance:** Gathering domain and DNS details without directly interacting with the target system to avoid detection.
- **Active Reconnaissance:** Probing the target network directly using ICMP and ARP sweeps to discover live hosts.

### 2. Port & Service Scanning
- **Stealth Scanning (TCP SYN):** Sending TCP SYN packets to identify open ports without completing the full three-way handshake.
- **Service & OS Detection:** Interrogating open ports to extract banner information, service versions, and operating system fingerprints.

### 3. Vulnerability Scanning
- **Automated Scanning:** Using Tenable Nessus to scan target ports against CVE databases, identifying missing security patches, weak configurations, and exploitable flaws.

### 4. Packet Analysis & Traffic Inspection
- **Packet Sniffing:** Capturing live traffic using Wireshark to isolate sensitive plain-text data (e.g., FTP logins, HTTP POST parameters).
- **Attack Simulation:** Generating TCP SYN flood traffic using `hping3` to analyze Denial-of-Service (DoS) behavior in packet captures.

### 5. Host-Based Firewall Configuration
- **Packet Filtering (`iptables`):** Configuring Linux netfilter rules to enforce access policies, manage port permissions, and drop unauthorized ping/scan requests.

---

## 📖 Step-by-Step Execution Guide & Commands

### Step 1: Reconnaissance (Information Gathering)
```bash
# Passive Reconnaissance - Domain & DNS Lookups
whois example.com
nslookup example.com

# Active Reconnaissance - Ping Sweep for Live Hosts
nmap -sn 192.168.1.0/24
**Step 2: Port & Service Scanning (Nmap)**
Bash
# TCP SYN Stealth Scan
sudo nmap -sS <Target_IP>

# UDP Port Scan
sudo nmap -sU <Target_IP>

# Service Version Detection
sudo nmap -sV <Target_IP>

# Operating System Fingerprinting
sudo nmap -O <Target_IP>

# Comprehensive Scan & Export Output to File
sudo nmap -sS -sV -O -p- -oN nmap_report.txt <Target_IP>
**Step 3: Vulnerability Scanning (Tenable Nessus)**
Bash
# Start Nessus Service
sudo systemctl start nessusd

# 1. Open browser and navigate to: https://localhost:8834
# 2. Select "New Scan" -> "Basic Network Scan"
# 3. Enter Target IP (Metasploitable2) and execute scan
# 4. Export findings as PDF/HTML report
**Step 4: Packet Analysis with Wireshark & Traffic Simulation**
Bash
# Launch Wireshark
sudo wireshark

# Wireshark Filter Expressions:
# - FTP Plain-text Credentials: ftp
# - HTTP POST Data: http.request.method == "POST"
# - TCP SYN Packets: tcp.flags.syn == 1 and tcp.flags.ack == 0

# Simulate SYN Flood Attack (hping3)
sudo hping3 -S --flood -p 80 <Target_IP>
**Step 5: Firewall Rules Configuration (iptables)**
Bash
# View Active Firewall Rules
sudo iptables -L -v -n

# Allow Inbound Traffic on HTTP Port 80
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT

# Block Inbound Traffic on SSH Port 22
sudo iptables -A INPUT -p tcp --dport 22 -j DROP

# Drop ICMP Echo Requests (Block Ping / Port Scan Discovery)
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j DROP

# Clear/Flush All Rules (Reset)
sudo iptables -F
