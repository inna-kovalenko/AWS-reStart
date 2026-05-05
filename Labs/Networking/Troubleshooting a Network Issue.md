# Troubleshooting a Network Issue

This lab was a hands-on troubleshooting simulation. In this lab, I acted as an AWS Cloud Support Engineer to resolve connectivity issues for a customer's Apache web server by analyzing architecture diagrams and diagnosing misconfigured security components.

---

## Lab Objectives
After completing this lab, I demonstrated the ability to:
*   **Analyze customer architecture diagrams** to identify potential points of failure.
*   **Diagnose service-level issues** within a Linux environment using `systemctl`.
*   **Perform root cause analysis** on AWS networking components, including Security Groups and Network ACLs.
*   **Restore connectivity** to a web application by modifying infrastructure settings.

---

## Technical Scenario
A customer, AnaContractor, reported that her Apache server was unreachable via `ping` and web browser despite being created via the command line. I utilized a replica of her environment to isolate and fix the issue.

### Troubleshooting Checklist
To resolve the issue, I investigated the following VPC components:
*   **Subnets**: Verified route table associations.
*   **Route Tables**: Confirmed the presence of a route to the Internet Gateway (`0.0.0.0/0`).
*   **Internet Gateway**: Ensured the gateway was properly attached to the VPC.
*   **Security Groups & NACLs**: Inspected inbound and outbound rules for ICMP (Ping) and HTTP (Port 80) traffic.

---

## Task Summary

### 1. Service Initialization
Upon connecting to the instance via SSH, I discovered that the Apache service was inactive.
*   **Status Check**: Verified current state with `sudo systemctl status httpd.service`.
*   **Activation**: Successfully started the web server using `sudo systemctl start httpd.service`.

### 2. Network Diagnostics
Even with the service running, the web page failed to load in the browser, indicating a network-level blockage.
*   **Internet Connectivity Test**: Verified outbound access by pinging external sites (e.g., `amazon.com`).
*   **Security Group Analysis**: Evaluated the Security Group rules. In AWS, Security Groups act as a virtual firewall for instances, controlling inbound and outbound traffic.



### 3. Resolution: Port Configuration
The root cause was identified as a misconfiguration in the **Security Group**.
*   **The Fix**: Modified the inbound rules to allow **HTTP (Port 80)** traffic and **ICMP** (for ping requests).
*   **Verification**: Confirmed the fix by successfully loading the Apache Test Page using the instance's Public IP address.

---

## Key Takeaways
*   **Layered Security**: This lab highlighted the difference between service-level status (OS) and network-level access (AWS Infrastructure).
*   **Cloud Support Role**: Effective troubleshooting requires a systematic approach, moving from the internal instance state outward to VPC routing and security layers.
*   **Exam Readiness**: Understanding the "Inbound/Outbound" nature of Security Groups is a high-priority topic for the **AWS Cloud Practitioner** exam.
