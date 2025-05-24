# Hacking Wireless Devices – Lab Report

## 🧠 Overview

This repository contains the lab report for the wireless hacking module conducted by Group 10 as part of the course  Cyber Security Principles at 
The objective of this lab is to explore wireless network reconnaissance, packet analysis, cracking wireless encryption, and simulating
 rogue access point attacks in a controlled and ethical environment. The exercises provide hands-on experience with 
real-world wireless security tools and techniques.

---

## 🎯 Objectives

- Perform wireless reconnaissance and network scanning  
- Capture and analyze wireless packets  
- Execute WEP and WPA/WPA2 cracking techniques  
- Simulate rogue access point and Evil Twin attacks  
- Practice safe and ethical use of wireless hacking tools  

---

## 🛠️ Tools Used

1. **NetSurveyor** – Wireless network visualization and signal analysis tool  
2. **Wireshark** – Network protocol analyzer for capturing and analyzing packets  
3. **Aircrack-ng** – Wireless security auditing suite for cracking encryption keys  

---

## 👥 Team Members

| Name            | Roll Number |
|-----------------|-------------|
| Hassan Khan     | 2023243     |
| Zammad Safi     | 2023552     |
| Muhammad Shaheer| 2023509     |

**Instructor:** Mr. Abdullah Bin Zarshaid  
**Submission Date:** May 14, 2025  

---

## 🔍 Lab Activities Summary

### 1. Wireless Reconnaissance & Scanning  
- Identified nearby wireless access points using NetSurveyor  
- Analyzed signal strength and channel distribution over time  

### 2. Packet Capture & Analysis  
- Captured wireless packets in monitor mode using Wireshark  
- Inspected 802.11 management, control, and data frames  

### 3. Wireless Encryption Cracking  
- Performed WEP key cracking using Aircrack-ng tools  
- Attempted WPA/WPA2 handshake capture and cracking  

### 4. Rogue Access Point & Evil Twin Simulation  
- Created rogue APs to test network vulnerabilities  
- Simulated Evil Twin attacks to understand man-in-the-middle risks  

---

## 💻 Notable Commands and Usage

```bash
# Enable monitor mode on wireless interface
airmon-ng start wlan0

# Scan wireless networks and WPS-enabled APs
wash -i wlan0mon

# Capture wireless packets using Wireshark
wireshark &

# Crack WEP key
aircrack-ng -a 1 -b [BSSID] -w [wordlist.txt] [capturefile.cap]

# Crack WPA handshake
aircrack-ng -a 2 -b [BSSID] -w [wordlist.txt] [capturefile.cap]
