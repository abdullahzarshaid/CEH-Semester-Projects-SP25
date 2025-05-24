CEH Module 6 – System Hacking (Lab Report)
🧠 Overview
This repository contains the lab report for Module 6: System Hacking conducted by Group 3 for the course CY201 – Cyber Security Principles and Concepts at [Your Institution].

The objective of this module is to explore and understand how attackers gain unauthorized access to computer systems using real-world tools and techniques in a controlled lab environment. The exercises cover password cracking, privilege escalation, maintaining access, hiding activity, and clearing traces.
👥 Team Members
• Ali Muntazir – 2023098
• Muhammad Ismail – 2023453
• Abdullah Ahtasham – 2023033
Instructor: Mr. Abdullah Bin Zarshaid
Submission Date: May 14, 2025
🛠️ Environment Setup
Operating Systems:
- Windows 11
- Parrot OS
- Windows Server 2022

Virtualization: VirtualBox
Network Configuration: NAT & Host-Only Adapter
🔍 Lab Activities Summary
🔐 Lab 1 – Gain Access to the System
- Task 2: Audited system passwords using L0pht Crack
- Task 3: Identified known vulnerabilities using Exploit DB
- Task 5: Performed remote access using Armitage and Nmap
🧱 Lab 2 – Privilege Escalation
⚠️ Note: This lab was skipped due to unavailability of spyware tools.
🕵️ Lab 3 – Maintain Remote Access & Hide Activities
- Task 3: Used NTFS Streams to hide files via Command Prompt
- Task 5: Applied OpenStego for image steganography
🧹 Lab 4 – Clear Logs & Hide Evidence
- Task 1: Used AuditPol to view and clear audit logs
- Task 4: Hid artifacts using CMD on Windows and MATE Terminal on Linux
🧪 Tools Used
- L0pht Crack – Password auditing tool
- Armitage – Pen testing attack manager
- Nmap – Network scanning and vulnerability assessment
- OpenStego – Steganography tool
- Command Prompt / MATE Terminal – Command-line interfaces
💻 Notable Commands
cd C:\magic                         # Access folder
notepad read.txt                   # Create a text file
type calc.exe > read.txt:calc.exe # Hide EXE inside text file (NTFS stream)
mklink backdoor.exe read.txt:calc.exe # Link EXE to backdoor
⚠️ Issues Faced
- VM Connectivity: Resolved by using NAT + Host-Only network adapters
- John the Ripper Tool Access: Unable to run it on Ubuntu or Parrot OS despite download
🎓 Learning Outcomes
• Gained hands-on experience with real-world hacking tools and techniques
• Learned how to detect and exploit vulnerabilities in systems and websites
• Understood the importance of hiding artifacts and clearing audit logs for stealth
• Developed awareness of how attackers maintain access and evade detection

This knowledge enhances our ability to defend against cyberattacks by understanding how they work from the attacker’s perspective.
📁 Contents
- CEH_Module6_LabReport_Group3.docx – Full lab report documentation
📜 License
This project is for educational purposes only. Use responsibly and ethically.
