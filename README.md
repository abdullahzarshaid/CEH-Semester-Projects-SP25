# CEH-Semester-Projects-SP25
CEH v12 Lab Submissions for CY201 - Spring 2025 (Instructor: Abdullah Bin Zarshaid)
# Cloud Security Labs - AWS Exploitation and Security Assessment

## Project Overview
This repository contains documentation and resources for a series of cloud security labs focusing on AWS services. The labs demonstrate common security vulnerabilities in cloud environments, specifically targeting S3 buckets and IAM privilege escalation vectors.

## Authors
- Rubab Ali Qureshi (2023614)
- Sofia Faisal (2023519)
- Yashfa Fatima (2023762)

## Course
CY201 - Cyber Security Principles and Concepts

## Lab Environment
- **Attacker OS:** Kali Linux / Parrot Security OS
- **Target:** AWS Cloud Infrastructure (Free Tier Account)
- **Virtualization Tool:** VirtualBox
- **Network Settings:** NAT connection

## Labs Included

### Lab 1: S3 Bucket Enumeration
Demonstrates multiple techniques for discovering publicly accessible AWS S3 buckets using various enumeration tools:
- LazyS3: For generating and testing common bucket name permutations
- S3Scanner: For detailed bucket accessibility and permission analysis
- Custom AWS CLI scripts: For automated bucket enumeration with comprehensive testing

### Lab 2: S3 Bucket Exploitation
Shows how attackers can exploit misconfigured S3 buckets to:
- Access sensitive data without proper authentication
- Upload malicious files to compromised buckets
- Modify or delete existing bucket contents

### Lab 3: AWS Privilege Escalation
Demonstrates a complete privilege escalation attack chain in AWS environments:
- Initial access with limited permissions
- Reconnaissance of IAM users and policies
- Creation of unauthorized administrator accounts
- Attaching administrative policies to compromised accounts
- Creating persistence mechanisms via access keys
- Disabling legitimate administrator access

## Tools Used
- **AWS CLI v2**: Command-line interface for AWS services
- **LazyS3**: S3 bucket enumeration through permutation techniques
- **S3Scanner**: Detailed S3 bucket access permission analysis
- **Git**: Version control for project submission
- **Python & Ruby**: For running various enumeration scripts

## Common Errors & Solutions
1. **Permission Denied During LazyS3 Installation**: 
   - Solution: Use sudo to run the installation with elevated privileges

2. **AWS CLI Configuration Issues**:
   - Solution: Explicitly set the region during AWS CLI configuration

3. **S3Scanner Installation Dependencies**:
   - Solution: Create a Python virtual environment to isolate dependencies

4. **Access Denied During Privilege Escalation**:
   - Solution: Identify available permissions and work within those boundaries to expand access

5. **Environment Setup Issues with Parrot OS**:
   - Solution: Switch to Kali Linux for improved compatibility

## Security Recommendations

Based on the findings from these labs, we recommend the following security measures:

1. **S3 Bucket Security**:
   - Disable public access settings at the account level
   - Use bucket policies that enforce encryption and restrict access
   - Enable bucket logging and versioning
   - Regularly audit bucket permissions

2. **IAM Security**:
   - Implement the principle of least privilege for all IAM entities
   - Use IAM Access Analyzer to identify unintended access
   - Enable multi-factor authentication for all users
   - Regularly rotate access keys and review permissions
   - Use IAM roles instead of long-term access keys when possible

3. **General AWS Security**:
   - Enable CloudTrail for comprehensive logging
   - Set up alerts for suspicious activity
   - Regularly conduct security assessments
   - Follow AWS security best practices guidelines

## Educational Purpose
These labs are designed for educational purposes only. The techniques demonstrated should only be used in environments where you have explicit permission to test security controls.

## Further Learning
For those interested in cloud security, we recommend exploring:
- AWS Security Best Practices documentation
- Cloud Security Alliance guidelines
- OWASP Cloud Security resources
- CEH Cloud Security modules
