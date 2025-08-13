# TryHackMe Lab: Nmap

## NMAP
Nmap is a tool used to **identify systems that are online** and the **services running on those systems**.  

**Note:** It's important to first identify online systems before running port scans to avoid unnecessary network noise.

---

## Methods to Discover Live Hosts
- **ARP Scan** (Data-Link Layer)  
- **ICMP Scan** (Network Layer)  
- **TCP/UDP Scan** (Transport Layer)  

**Notes:**  
- Unlike ARP and ICMP scans, TCP/UDP scans send packets to ports to determine live hosts.  
- `-sL` → Lists hosts without scanning (with DNS reverse resolution)  
- `-n` → Disables DNS resolution  

---

## Nmap Host Discovery Using ARP
- `-sn` → Discovers online hosts without port scanning  
- `-PR -sn` → Discovers online hosts using ARP without port scanning  

**Examples:**  
- `sudo nmap -PR -sn <IP_ADDRESS>`  
- Using ARP-Scan: `sudo arp-scan <IP_RANGE>`

---

## Nmap Host Discovery Using ICMP
- `-PE` → Discover live hosts using Echo Request (Ping)  
- `-PP` → Discover live hosts using ICMP Timestamp  
- `-PM` → Discover live hosts using Address Mask  

---

## Nmap Host Discovery Using TCP/UDP
- `-PS` → SYN Ping to discover live hosts  
  - Can specify ports: e.g., `-PS21`, `-PS21-25`, `-PS80,443,8080`  
- `-PA` → ACK Ping (privileged users only)  
  - Defaults to port 80 if no port is specified  
- `-PU` → UDP Ping  

---

## Using Reverse-DNS Lookup
- `-R` → Queries a DNS server for hostnames of live hosts

