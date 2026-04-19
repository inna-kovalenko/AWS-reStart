# Resolving Global Connectivity Issues

## Synopsis
In this technical simulation, I acted as a **Cloud Support Engineer** for a Fortune 500 client. I resolved a critical networking disparity between two identical EC2 instances. By applying the **OSI Model** and investigating **IPv4 addressing**, I identified why one instance could access the internet while the other remained isolated, eventually providing a strategic solution to ensure consistent connectivity.

---

## Objectives & Key Tasks
* **Infrastructure Audit:** Analyzed a VPC (10.0.0.0/16) to compare configuration settings between Instance A and Instance B.
* **Connectivity Testing:** Utilized **PuTTY (Windows)** and **SSH** to attempt remote access and verify path reachability.
* **Public vs. Private IP Analysis:** Determined the functional limitations of Private IP addresses in a cloud environment.
* **Architecture Advisory:** Evaluated the risks of using Public IP ranges for internal network CIDRs.

---

## Technical Skills Demonstrated
* **Remote Server Management:** **SSH** and **PPK key management** using PuTTY for Windows.
* **Layer 3 Networking:** **IPv4 stacks**, CIDR blocks, internal and external routing (distinction).
* **The OSI Troubleshooting Framework:** applied a "Bottom-Up" troubleshooting methodology to isolate issues at the Network (Layer 3) and Session (Layer 5) levels.
* **Cloud Governance:** validated adherence to **RFC 1918** standards to prevent IP overlap and routing conflicts.

---

## Key Findings & Solutions
* **The Root Cause:** 
Instance A lacked a **Public IP address**. While secure, it cannot be reached from the public internet without a NAT gateway or a Public IP assignment.
* **Connectivity Solution:** 
Instance B succeeded because it possessed a Public IP, allowing the Internet Gateway to route traffic to and from the external web.
* **Risk Mitigation:** 
I advised against using a Public CIDR (like 12.0.0.0/16) for internal VPCs. Doing so would lead to "IP Overlap," causing the internal network to accidentally block legitimate websites that own those public addresses.

---

## Business & Career Impact
* **Strategic Problem Solving:** 
Successfully translated complex network logs into actionable business advice for a stakeholder.
* **CRM/HCM Security Applications:** 
This troubleshooting logic is vital for managing, for example, **Salesforce** or **Workday** integrations, ensuring that employee data (Health/HR records) remains private while necessary cloud services stay connected.
* **Technical Communication:** 
Demonstrated the ability to guide non-technical administrators through high-stakes infrastructure changes.
