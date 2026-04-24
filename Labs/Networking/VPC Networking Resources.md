# Architecting Networking Resources in an Amazon VPC

## Project Overview
I served as a **Cloud Support Engineer** to resolve a critical connectivity issue for a startup client. The project involved building a secure, routable **Virtual Private Cloud (VPC)** from the ground up, transitioning the infrastructure from an isolated state to a fully functional network capable of internet communication.

## Technical Accomplishments
* **VPC & Subnet Design**: Provisioned a custom **VPC** using the `192.168.0.0/18` range and engineered a **Public Subnet** (`192.168.1.0/26`) to ensure precise IP address allocation.

Here this creation step is shown with the requirement from the customer (on the left) and the general recommendation from AWS to follow the flow of their menu items as the best practice, though the order could be different:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/049745c6-6af1-4a11-9f62-fb2106b85e09" />


* **Internet Gateways & Routing**: Deployed an **Internet Gateway (IGW)** and configured **Custom Route Tables** with a default route (`0.0.0.0/0`) to enable external traffic egress.
* **Layered Security Implementation**:
    * **Stateless Security**: Developed **Network Access Control Lists (NACLs)** at the subnet level to filter traffic using prioritized inbound and outbound rules.
    * **Stateful Security**: Configured **Security Groups** to act as a virtual firewall for the instance, specifically permitting **SSH (22)**, **HTTP (80)**, and **HTTPS (443)** traffic.
* **Validation & Testing**: Launched an **Amazon Linux EC2 instance**, established a secure **SSH connection**, and utilized the **ICMP protocol (ping)** to verify 0% packet loss and successful end-to-end connectivity.

Here is the illustration of successful completion of all the lab's steps as seen also from the AWS Management Console & using `ping` through the SSH connection:
<img width="1813" height="1008" alt="image" src="https://github.com/user-attachments/assets/d64db3ae-06d3-47df-800e-a9dbaa4a2481" />


## Skills Demonstrated
* **AWS Core Services**: VPC, Subnets, Internet Gateways, Route Tables, EC2.
* **Network Security**: Stateful vs. Stateless firewalls, Security Group rules, NACL logic.
* **Troubleshooting**: Diagnosing "no route to host" errors and resolving security layer blocks.
* **Linux Connectivity**: Remote management via SSH/PuTTY and network diagnostic tools.

## Key Outcomes
* **Problem Resolution**: Successfully architected a "routable" network, solving the client's inability to reach the internet.
* **Best Practices**: Applied a "top-down" deployment methodology (VPC → Subnet → Gateway → Route Table → Security) to ensure no architectural dependencies were missed.
* **Operational Readiness**: Demonstrated the ability to bridge cloud infrastructure with standard networking protocols used in global enterprise environments.
