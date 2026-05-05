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
A customer, a contractor working with AWS, reported that her Apache server was unreachable via `ping` and web browser despite being created via the command line. I utilized a replica of her environment to isolate and fix the issue.

This shows the customer's AWS architecture:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/368aa976-22a6-41d5-96b3-c30701ebcc82" />


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

This screenshot documents completion of the steps above:
<img width="947" height="502" alt="image" src="https://github.com/user-attachments/assets/d35aa019-f1be-4d08-b603-1cf0869ec3d9" />


### 2. Network Diagnostics
Even with the service running, the web page failed to load in the browser, indicating a network-level blockage.
*   **Internet Connectivity Test**: Verified outbound access by pinging external sites (e.g., `amazon.com`).
*   **Security Group Analysis**: Evaluated the Security Group rules. In AWS, Security Groups act as a virtual firewall for instances, controlling inbound and outbound traffic.


Here it is visible I modified the corresponding Security Group's inbound rules:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8d1a70d3-5807-4abd-bff4-24977160fa48" />

### 3. Resolution: Port Configuration
The root cause was identified as a misconfiguration in the **Security Group**.
*   **The Fix**: Modified the inbound rules to allow **HTTP (Port 80)** traffic and **ICMP** (for ping requests).
*   **Verification**: Confirmed the fix by successfully loading the Apache Test Page using the instance's Public IP address.

This shows connection got successfully established after the changes made to the Security Group:
<img width="930" height="502" alt="image" src="https://github.com/user-attachments/assets/b49752ba-cc66-43ed-b38f-f99d09303e76" />

---

## Key Takeaways
*   **Layered Security**: This lab highlighted the difference between service-level status (OS) and network-level access (AWS Infrastructure).
*   **Cloud Support Role**: Effective troubleshooting requires a systematic approach, moving from the internal instance state outward to VPC routing and security layers.
*   **Exam Readiness**: Understanding the "Inbound/Outbound" nature of Security Groups is a high-priority topic for the **AWS Cloud Practitioner** exam.
