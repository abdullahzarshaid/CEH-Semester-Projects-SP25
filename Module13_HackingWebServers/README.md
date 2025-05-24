# CEH Module 13 – Hacking Web Servers
🧠 **Overview**  
This lab simulates FTP credential cracking using dictionary attacks and evaluates web server vulnerabilities.  

👥 **Team Members**  
- Aayan Rashid – 2023002  
- Ali Uzair – 2023102  
- Muaaz Bin Salman – 2023338  
**Instructor:** Sir Abdullah Bin Zarshaid  
**Submission Date:** May 14, 2025  

---

## 🛠️ **Environment Setup**  
**Operating Systems:**  
- **Attacker:** Parrot Security OS  
- **Target:** Windows 11 (IP: `10.1.164.60`)  

**Virtualization:** VMware / VirtualBox  
**Network Configuration:** Bridged  

---

## 🔍 **Lab Activities Summary**  
- **Task 1:** Scanned FTP port with `nmap -p 21 -sV <target_IP>`  
- **Task 2:** Cracked credentials using Hydra  
- **Task 4:** Created "hacked" directory to test write permissions.  

---

## 📂 **Files & References**  
- **Tools Used:** Detailed tool descriptions in [`tools_module13.md`](tools_module13.md).  
- **Commands Executed:** Complete command syntax in [`commands_module13.md`](commands_module13.md).  

---

## ⚠️ **Issues Faced**  
- **Hydra Syntax Errors:** Fixed by correcting command spacing.  
- **Account Lockouts:** Reset with `net user <username> /active:yes`.  

---

## 🎓 **Learning Outcomes**  
- Exploited weak FTP credentials using automated tools.  
- Identified risks of unsecured protocols (FTP vs. SFTP).  
- Practiced post-exploitation file manipulation.  

---

## 📁 **Contents**  
- `CEH_Module13_report_group07.docx`  
- `tools_module13.md`: Tools like Hydra, Nmap, and IIS  
- `commands_module13.md`: Attack and validation commands  

---

## 📜 **License**  
*Ethical use only. Unauthorized attacks are prohibited.* 
