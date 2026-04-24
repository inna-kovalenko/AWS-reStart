# Designing and Scaling Virtual Networks

## Synopsis
In this technical engagement, I acted as a Cloud Support Engineer for a startup owner requiring a custom-built networking environment. I designed a Virtual Private Cloud (VPC) from scratch, ensuring the architecture met specific scale requirements for over 15,000 private IP addresses while adhering to RFC 1918 standards. This lab demonstrated the ability to translate business growth needs into a scalable cloud network topology.

---

## Objectives & Key Tasks
* **Architectural Planning:** Evaluated customer requirements for a large-scale private network (15,000+ IPs) and a public-facing operations subnet (50+ IPs).
* **VPC Construction:** Utilized the AWS Create VPC function to deploy a "VPC with a Single Public Subnet" configuration.
* **IP Address Allocation:** Calculated and assigned appropriate CIDR blocks using 192.168.0.0/18 to accommodate the requested capacity.
* **Subnet Segmentation:** Defined a specific range for the Public Subnet to ensure operational needs were met without wasting address space.

Here is the confirmation of the steps above completed - the screenshot shows how the customer's requirements translated to the correct CIDR bock choice (I configured VPC at 192.168.0.0/18 (16,384 IPs) and Public Subnet at  192.168.0.0/26 (64 IPs) to fulfill the client's request for 15,000 network addresses and 50+ subnet hosts):




---

## Technical Skills Demonstrated
* **CIDR Notation & Subnetting:** Calculated network boundaries to provide 16,384 addresses (via /18) to meet the 15,000-IP threshold.
* **RFC 1918 Compliance:** Validated and implemented private addressing using the 192.168.x.x range to ensure internal security.
* **AWS Networking Core:** Hands-on experience with VPC Wizards, Subnet creation, and Internet Gateway (IGW) logic.
* **Requirement Analysis:** Successfully balanced large-scale internal needs with small-scale public access requirements.

---

## Key Findings & Solutions
* **Scalability:** To meet the 15,000 IP requirement, a /18 mask (192.168.0.0/18) was used, providing 16,384 addresses—the smallest standard block that satisfies the request.
* **Public Access:** A /26 mask (192.168.1.0/26) was assigned to the Public Subnet, providing 64 addresses, which safely covers the customer's 50-IP requirement.
* **Isolation Strategy:** Confirmed that private IP addresses remain unreachable from the internet, protecting the "Seattle Headquarters" resources while allowing "Operations" to face the web.

---

## Business & Career Impact
* **Cloud Infrastructure Design:** Demonstrated the ability to build the foundation for an entire startup's digital presence.
* **Resource Management:** Applied precision in IP allocation, preventing "IP exhaustion" during future company expansions.
* **Strategic Consulting:** Effectively guided a "Startup Owner" through technical complexities, bridgeing the gap between business vision and cloud execution.
