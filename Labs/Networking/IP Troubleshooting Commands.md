# Internet Protocol Troubleshooting Commands

This lab focused on network diagnostic tools. The lab demonstrated how to connect to AWS resources via SSH and utilize core networking commands to identify and resolve connectivity issues across different layers of the OSI model.

Here is an example of how the troubleshooting commands flow with the Open Systems Interconnection (OSI) model:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/05d5d425-b734-48c5-8094-83ed13ae5923" />


---

## Lab Objectives
After completing this lab, the following competencies were developed:
*   **Practiced troubleshooting commands** within a live Linux environment.
*   **Identified customer scenarios** where specific networking tools provide critical diagnostic data.
*   **Mapped networking commands** to their corresponding layers in the OSI model.

---

## Technical Scenario
As a network administrator, I utilized an Amazon Linux EC2 instance to simulate real-world troubleshooting scenarios. The lab focused on identifying latency, packet loss, and port-level connectivity issues.



---

## Troubleshooting Command Summary

### Layer 3: Network Layer (Connectivity & Path)
*   **`ping`**: Used to test basic IP-level connectivity and reachability to a specific target (e.g., `ping 8.8.8.8 -c 5`). It is essential for verifying security group rules and ICMP permissions.
*   **`traceroute`**: Used to identify the path a packet takes and locate where latency or packet loss occurs (e.g., `traceroute 8.8.8.8`). Three asterisks (***) indicate a failed hop in the network path.

The screenshot shows completion of the above steps checking the if there are issues with the Network Layer:
<img width="890" height="486" alt="image" src="https://github.com/user-attachments/assets/7358e3cd-0ce9-4040-8d6c-77186d078d3a" />


### Layer 4: Transport Layer (Ports & Connections)
*   **`netstat`**: Used to identify which ports are listening or established on a host (e.g., `netstat -tp`). This is a critical tool for security scans and narrowing down local networking issues.
*   **`telnet`**: Used to confirm if a specific TCP port is open or blocked by a firewall (e.g., `telnet www.google.com 80`). 
    *   **Connection Refused**: Indicates a firewall or security group is likely blocking the port.
    *   **Connection Timed Out**: Suggests a total lack of network route or connectivity.

### Layer 7: Application Layer (Data Transfer)
*   **`curl`**: Used to transfer data and test application-level responses (e.g., `curl -vLo /dev/null https://aws.com`). 
*   **Verbose Mode (`-v`)**: Essential for seeing HTTP headers and identifying if a server returns a `200 OK` status, confirming the application is running successfully.

---

## Key Takeaways for Career Path
*   **Consultancy**: These commands are vital for ensuring that **CRM (Salesforce)** or **HCM (Workday)** integrations can communicate through corporate firewalls.
*   **AWS re/Start**: Mastery of these Linux-based tools is a core requirement for the **AWS Cloud Practitioner** and **Solutions Architect** exams.
