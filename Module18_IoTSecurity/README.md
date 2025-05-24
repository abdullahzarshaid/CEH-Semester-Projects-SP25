# IoT and OT Hacking Laboratory Manual

## Course Information
- **Course**: CY201 – IoT Security Module
- **Module**: Module 18 - IoT Security
- **Institution**: Ghulam Ishaq Khan Institute of Engineering Sciences and Technology, Topi
- **Faculty**: Faculty of Cyber Security
- **Instructor**: Mr. Abdullah Bin Zarshaid

## Team Members
- **Rida Shahid Malik** (2023610)
- **Ummama Khan** (2023738)
- **Momna Jamil** (2023336)

## Objective

This laboratory exercise focuses on developing comprehensive practical skills in ethical hacking of Internet of Things (IoT) and Operational Technology (OT) systems. The primary objectives encompass three critical areas of cybersecurity assessment:

**Intelligence Gathering and Footprinting**: Students learn to perform systematic reconnaissance on IoT and OT devices using industry-standard tools and methodologies. This includes identifying device specifications, network configurations, service banners, and potential attack surfaces through passive and active information gathering techniques.

**Network Traffic Analysis**: The lab emphasizes capturing and analyzing network communications between IoT devices, with particular focus on the Message Queuing Telemetry Transport (MQTT) protocol. Students gain hands-on experience in packet analysis, protocol dissection, and identifying security vulnerabilities in device communications.

**Vulnerability Assessment and Attack Simulation**: Through controlled simulation environments, students learn to identify, analyze, and exploit common vulnerabilities found in IoT and OT infrastructures, including weak authentication mechanisms, unencrypted communications, and misconfigured services.

## Environment Setup and Infrastructure

### Laboratory Environment Architecture

The laboratory exercise is structured across three interconnected labs, each designed to build upon previous knowledge while introducing new concepts and tools.

### Lab 1 Environment Configuration
**Primary Operating System**: Windows 11 Virtual Machine (VM)
- **Purpose**: Serves as the main reconnaissance and footprinting platform
- **Justification**: Provides a controlled environment for web-based reconnaissance tools while maintaining isolation from the host system
- **Configuration**: Standard Windows 11 VM with internet connectivity for accessing online reconnaissance platforms

### Lab 2 and Lab 3 Environment Configuration
**Multi-System Architecture**:
- **Windows 11 Home VM**: Acts as the MQTT broker host and primary control system
- **Host Operating Systems**: Two additional host systems for distributed testing
- **Windows Server 2019 (Standard Edition)**: Dedicated server environment for IoT device simulation and network traffic generation

**Network Architecture**: The multi-system setup allows for realistic network traffic simulation and comprehensive packet analysis across different network segments.

### Tool Suite and Justification

**Wireshark Network Protocol Analyzer**
- **Primary Function**: Network traffic capture and deep packet inspection
- **Application**: Analysis of MQTT protocol communications, identification of unencrypted data transmission, and protocol behavior analysis
- **Configuration**: Configured with custom filters for MQTT traffic isolation and analysis

**Shodan Internet-Connected Device Search Engine**
- **Primary Function**: Discovery and reconnaissance of internet-connected IoT devices
- **Application**: Identification of vulnerable devices, open ports analysis, geolocation mapping, and service banner collection
- **Search Methodology**: Utilization of specific search queries (port:1883 for MQTT devices) to identify potential targets

**Bevywise MQTTRoute Broker Management Platform**
- **Primary Function**: MQTT broker setup, configuration, and management
- **Application**: Creation of controlled MQTT communication environment for traffic generation and analysis
- **Configuration**: Default installation with web-based management interface accessible via port 8080

## Lab 1: Comprehensive Footprinting and Reconnaissance

### Step 1: Virtual Machine Setup
Configure a Windows 11 VM to serve as the primary environment for reconnaissance tasks.

**VM Configuration Requirements:**
- Memory allocation optimized for concurrent web browser sessions
- Network configuration allowing full internet access while maintaining host system isolation
- Security settings configured to prevent accidental exposure of host system information

### Step 2: Domain Intelligence Gathering through Whois Analysis

1. **Access Whois Service**: Navigate to `whois.com/whois/` using your web browser
2. **Target Selection**: Search for `oasis-open.org` to perform comprehensive domain registration analysis
3. **Information Extraction**: Collect registrar details, administrative contacts, technical contacts, name server information, and IP address ranges
4. **Intelligence Analysis**: Evaluate collected information to identify potential attack vectors and organizational structure

**Key Intelligence to Gather:**
- Domain registration timeline and renewal patterns
- Administrative and technical contact information
- DNS infrastructure and name server configurations
- Associated IP address ranges and network blocks

### Step 3: Advanced Google Dorking for SCADA System Discovery

1. **Access Google Hacking Database**: Navigate to `exploit-db.com/google-hacking-database`
2. **Search for SCADA Dorks**: Enter "scada" in the Quick Search to find pre-crafted search queries
3. **Select Target Dork**: Choose any SCADA-specific Google dork from the results
4. **Execute Search**: Copy the selected dork and paste it into Google search engine
5. **Analyze Results**: Review search results to identify exposed SCADA systems

**SCADA System Analysis Process:**
- Verify identified systems to confirm SCADA functionality
- Assess systems for common vulnerabilities including default credentials
- Document authentication weaknesses and interface exposure risks

### Step 4: Shodan-Based IoT Device Discovery

1. **Account Setup**: Create and verify a Shodan account at `shodan.io`
2. **Login Process**: Access the Shodan dashboard using your credentials
3. **Device Discovery**: Use the search query `port:1883` to identify MQTT-enabled IoT devices
4. **Results Analysis**: Review discovered devices for:
   - Geographic distribution and organizational attribution
   - Service banners and device metadata
   - Open ports and supported protocols
   - Potential security vulnerabilities

**Intelligence Collection Focus:**
- Device inventory with associated metadata
- Vulnerability assessment based on service banners
- Geographic distribution patterns
- Organizational analysis for potential target assessment

## Lab 2: MQTT Broker Implementation and IoT Device Simulation

### Step 1: MQTT Broker Infrastructure Setup

1. **Launch MQTTRoute**: Click on the MQTTRoute application to open the broker service
2. **Network Configuration**: 
   - Open Command Prompt (Win + R, type `cmd`)
   - Use `ipconfig` to identify your Ethernet adapter IPv4 address
   - Note the IP address (example: 192.168.56.1) for broker configuration
3. **Web Interface Access**: Navigate to `<Your_IP>:8080` to access the broker management interface

### Step 2: Broker Authentication and Configuration

1. **Locate Configuration**: Navigate to the Bevywise folder and enter the config directory
2. **Retrieve Credentials**: Open the config file in Notepad to find default credentials
3. **Login Process**: Use the default credentials (username: admin, password: admin)
4. **Dashboard Access**: Verify successful login to the MQTTRoute dashboard

### Step 3: IoT Device Simulation Environment Setup

1. **Windows Server 2019 Setup**: Launch your Windows Server 2019 VM
2. **Simulator Installation**: Download and install the Bevywise IoT Simulator
3. **Simulator Launch**: Navigate to the bin folder and run `runsimulator.bat`
4. **Interface Verification**: Confirm the simulator UI interface loads successfully

### Step 4: Virtual Network Creation and Device Management

1. **Network Creation**:
   - Click "Create Network" in the simulator interface
   - Name the network (no spaces allowed)
   - Replace the default broker IP with your identified IP address (e.g., 192.168.56.1)
   - Confirm the configuration and start the network

2. **Device Addition**:
   - Click the red dot to start the network
   - Click the plus sign and select "Blank Device"
   - Name the device and assign a unique device ID
   - Confirm successful device addition

### Step 5: MQTT Communication Testing

1. **Command Subscription**:
   - Select "Subscribe to Command" option
   - Configure topic: `HIGH_TEMP`
   - Set up monitoring for device communications

2. **Device Verification**:
   - Check if the device appears on the MQTTRoute dashboard
   - Verify active device status in the web interface

3. **Test Message Transmission**:
   - Topic: `HIGH_TEMP`
   - Message: `Message sent to TMP1`
   - Confirm successful transmission via the web UI

## Lab 3: Network Traffic Analysis and Protocol Dissection

### Step 1: Wireshark Configuration and Setup

1. **Launch Wireshark**: Start Wireshark on the Windows Server 2019 VM
2. **Interface Selection**: Select the Ethernet interface corresponding to your MQTT broker network (192.168.56.1)
3. **Filter Configuration**: 
   - Click the + to create a new filter
   - Apply MQTT protocol filter: `tcp port 1883`
   - Activate the filter for packet capture

### Step 2: Synchronized Packet Capture Process

**Capture Methodology**: Coordinate packet capture with MQTT command execution from Lab 2 to ensure comprehensive analysis of all communication phases.

**Packet Types to Analyze**:

1. **Connection Establishment**:
   - **MQTT CONNECT Packets**: Analyze client IDs, protocol versions (MQTT v3.1.1), and keep-alive timers
   - **CONNACK Packets**: Examine connection acknowledgment and return codes

2. **Message Publication**:
   - **MQTT PUBLISH Packets**: Examine topic structure (`HIGH_TEMP`) and payload content (`Message sent to TMP1`)
   - **PUBACK Packets**: Analyze publish acknowledgment for QoS 1 messages

3. **Subscription Management**:
   - **MQTT SUBSCRIBE Packets**: Review topic filter patterns and QoS level negotiation
   - **SUBACK Packets**: Examine subscription acknowledgment and granted QoS levels

### Step 3: Security Vulnerability Assessment

**Critical Findings**:

1. **Unencrypted Data Transmission**:
   - Complete visibility of MQTT message payloads in plaintext
   - Exposure of authentication credentials during connection establishment
   - Device fingerprinting through protocol analysis

2. **Protocol Security Weaknesses**:
   - Absence of TLS/SSL encryption on standard MQTT port 1883
   - Lack of built-in data integrity verification
   - Susceptibility to man-in-the-middle attacks

3. **Network Security Implications**:
   - Traffic interception and modification vulnerability
   - Complete message content visibility for network observers
   - Device enumeration through traffic analysis

## Technical Challenges and Resolution Strategies

### Common Issues and Solutions

#### Shodan Platform Accessibility
**Problem**: Intermittent server errors during searches
**Solution**: 
- Implement retry mechanism with delays
- Verify account credentials and upgrade service tier if necessary
- Schedule searches during off-peak hours

#### Virtual Machine Configuration
**Problem**: Continuous boot loops due to virtual floppy disk misconfiguration
**Solution**:
- Access VM settings and remove virtual floppy disk drive
- Reconfigure boot sequence to prioritize virtual hard drive
- Verify working configuration before proceeding

#### MQTT Broker Connectivity
**Problem**: "Broker is not running" error and device connectivity issues
**Solution**:
- Verify service status through command-line utilities
- Check network interface binding and IP address configuration
- Restart MQTTRoute service with proper configuration
- Validate port 1883 availability and accessibility

#### Windows Firewall Configuration
**Problem**: MQTT traffic blocked by Windows Defender Firewall
**Solution**:
1. Open Windows Defender Firewall with Advanced Security
2. Create new inbound rule:
   - Protocol: TCP
   - Port: 1883
   - Action: Allow the connection
   - Profile: Apply to Domain, Private, and Public networks
   - Name: MQTT_PORT
3. Create corresponding outbound rule with same parameters
4. Verify rule activation and test connectivity

## Security Assessment and Vulnerability Analysis

### Critical Security Vulnerabilities Identified

#### 1. Unencrypted MQTT Communications
**Risk Level**: High
- All message payloads transmitted in plaintext
- Authentication credentials exposed during connection
- Communication patterns reveal device behavior and system architecture

#### 2. Authentication and Authorization Weaknesses
**Risk Level**: High
- Default administrative credentials (admin/admin)
- Weak password policies susceptible to brute-force attacks
- Lack of multi-factor authentication mechanisms

#### 3. Information Disclosure Through Reconnaissance
**Risk Level**: Medium to High
- Device identification through Shodan exposure
- Network topology revelation through traffic analysis
- Geographic location disclosure for physical security assessment

### Recommended Security Implementation Strategies

#### 1. Encryption and Secure Communication
- **MQTT over TLS (MQTTS)**: Implement MQTT over TLS using port 8883
- **Certificate Management**: Establish PKI for device authentication
- **Strong Encryption**: Use industry-standard encryption algorithms

#### 2. Authentication and Access Control
- **Strong Password Policies**: Implement complex password requirements
- **Certificate-Based Authentication**: Deploy digital certificates for device identity
- **Role-Based Access Control**: Implement granular access permissions

#### 3. Network Security and Segmentation
- **Network Segmentation**: Isolate IoT devices from critical business systems
- **Firewall Configuration**: Implement restrictive firewall rules
- **Intrusion Detection**: Deploy network-based monitoring systems

#### 4. Monitoring and Incident Response
- **Comprehensive Logging**: Implement detailed audit logging
- **Real-Time Monitoring**: Deploy SIEM solutions for IoT environments
- **Incident Response Procedures**: Establish IoT-specific response protocols

## Learning Outcomes and Skill Development

### Technical Competencies Developed

1. **Network Security Analysis**: Advanced packet analysis and protocol dissection skills
2. **Reconnaissance Techniques**: Professional-level intelligence gathering methodologies
3. **Vulnerability Assessment**: Systematic approach to identifying IoT security weaknesses
4. **Problem-Solving**: Practical troubleshooting and technical issue resolution
5. **Risk Assessment**: Comprehensive understanding of IoT security risk evaluation

### Industry Readiness

The comprehensive nature of this laboratory exercise directly prepares students for professional cybersecurity roles, particularly those focused on:
- IoT and OT security assessment
- Industrial cybersecurity
- Critical infrastructure protection
- Penetration testing and vulnerability assessment

### Future Research and Development

This foundation enables advanced research in:
- AI-powered IoT security analytics
- Blockchain integration for device identity management
- Post-quantum cryptography for IoT environments
- Extended reality (XR) security visualization

## Conclusion

The IoT and OT Hacking laboratory exercise provides comprehensive hands-on experience in multiple critical areas of cybersecurity. Key achievements include:

- **Footprinting Proficiency**: Mastery of intelligence gathering tools and techniques
- **Traffic Analysis Expertise**: Advanced skills in network protocol analysis and packet inspection
- **Vulnerability Identification**: Systematic approach to identifying IoT security weaknesses
- **Attack Simulation**: Practical experience with realistic attack scenarios
- **Problem-Solving Skills**: Development of systematic troubleshooting methodologies
- **Security Awareness**: Deep understanding of IoT ecosystem security requirements

These skills strengthen the ability to secure IoT and OT environments against cyber threats and provide essential preparation for real-world cybersecurity challenges in the rapidly evolving landscape of connected devices and industrial systems.
