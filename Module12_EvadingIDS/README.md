
# CEH Module 12 – Evading IDS & Firewalls (Lab Report)  
🧠 **Overview**  
This lab focuses on configuring **Snort IDS** to detect ICMP-based attacks and evade intrusion detection systems in a controlled environment.  

👥 **Team Members**  
- Aayan Rashid – 2023002  
- Ali Uzair – 2023102  
- Muaaz Bin Salman – 2023338  
**Instructor:** Sir Abdullah Bin Zarshaid  
**Submission Date:** May 14, 2025  

---

## 🛠️ **Environment Setup**  
**Operating Systems:**  
- **Target:** Windows Server 2019 (IP: `192.168.162.130`)  
- **Attacker:** Windows 11  

**Virtualization:** VMware Workstation  
**Network Configuration:** NAT  

---

## 🔍 **Lab Activities Summary**  
- **Task 1:** Installed Snort and configured `snort.conf` with `HOME_NET = 192.168.162.130`  
- **Task 2:** Verified network interfaces using `snort -W`  
- **Task 4:** Triggered ICMP ping alerts and analyzed logs in `C:\Snort\log\`  

---

## 🧪 **Tools Used**  
- **Snort v2.9.15**: Intrusion Detection System  
- **WinPcap**: Packet capture library  
- **VMware Workstation**: Virtualization  

---

## 💻 **Notable Commands**  
```bash
snort -W                          # List interfaces  
snort -dev -i 1                   # Capture traffic on interface 1  
ping 192.168.162.130 -t           # Simulate ICMP attack  
```

---

## ⚠️ **Issues Faced**  
- **Interface Misidentification:** Fixed with `snort -W` to verify indexes.  
- **Preprocessor Warnings:** Adjusted `snort.conf` to comment unused modules.  

---

## 🎓 **Learning Outcomes**  
- Configured Snort IDS for real-time traffic monitoring.  
- Analyzed ICMP-based attack patterns and logs.  
- Troubleshooted network interface and configuration errors.  

---

## 📁 **Contents**  
- `CEH_Module12-13_report_group07.docx`  
- `tools_module12.txt`: Tool versions and purposes  
- `commands_module12.txt`: Lab commands with explanations  

---

## 📜 **License**  
*For educational use only. Unauthorized network monitoring is illegal.*  

