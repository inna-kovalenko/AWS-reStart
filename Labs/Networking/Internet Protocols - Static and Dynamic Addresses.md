# Implementing Persistent Cloud Identity

## Synopsis
In this technical engagement, I served as an AWS Cloud Support Engineer for a Fortune 500 client experiencing configuration drift. The client’s architecture relied on a static entry point, but their EC2 instance changed its Public IP address every time it was restarted to save costs. I replicated this behavior, analyzed the difference between Dynamic and Static (Elastic) IP addresses, and implemented a permanent solution using Amazon Elastic IPs (EIP).

---

## Objectives & Key Tasks
* **Scenario Replication:** Launched a t3.micro Amazon Linux 2 instance to simulate the customer's "Public Instance" environment.

This step shows the Instance (test instance) was successfully created with all the necessary configurations: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6b7d1bd0-961f-4b12-8f8c-3ccfa7243e8f" />

Here it is visible the instance is running & has the following public & private IPv4 addresses:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b673e751-61eb-4418-bea3-bcde0285f475" />

* **Behavioral Analysis:** Monitored the lifecycle of Dynamic Public IPs by performing "Stop/Start" cycles and documenting the resulting IP changes.
* **Static IP Allocation:** Provisioned an Elastic IP (EIP) from the Amazon pool to create a persistent network identity.
* **Resource Association:** Successfully linked the EIP to the running EC2 instance to override the default dynamic behavior.
* **Validation:** Confirmed that the IP address remained unchanged across multiple power cycles, resolving the client's connectivity breakage.

---

## Technical Skills Demonstrated
* **EC2 Lifecycle Management:** Proficient in the transitions between Pending, Running, Stopping, and Stopped states.
* **Elastic IP (EIP) Administration:** Managed the allocation and association of persistent IPv4 addresses within a VPC.
* **Troubleshooting & Root Cause Analysis (RCA):** Identified that Standard Public IPs are pulled from a dynamic pool and are released back to AWS upon instance termination or stopping.
* **Cloud Cost Optimization:** Understood the business logic of stopping instances to reduce hourly compute costs while maintaining network stability.

---

## Key Findings & Solutions
* **The Dynamic Default:** By default, AWS assigns a dynamic public IP to instances in a public subnet. This IP is "leased" and changes whenever the instance is stopped.
* **The Static Solution:** An Elastic IP (EIP) is a reserved public IP address that stays with the AWS account, not the specific hardware.
* **Persistence Comparison:**
    * **Private IP:** Remains constant through the life of the instance (Internal stability).
    * **Standard Public IP:** Changes on every "Stop/Start" cycle (Dynamic).
    * **Elastic IP (EIP):** Remains constant even when the instance is stopped (Persistent).

---

## Business & Career Impact
* **Operational Continuity:** Prevented breaking changes in the client's architecture. In a real-world Salesforce or Workday integration, a changing IP would break firewall whitelists and API connections.
* **Consultancy Readiness:** Demonstrated the ability to advise clients on balancing cost-savings (stopping instances) with architectural reliability (using EIPs).
* **Professional Documentation:** Created a clear technical audit trail showing the transition from a failing dynamic state to a stable static state.
