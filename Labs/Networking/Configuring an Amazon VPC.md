## Lab Overview – Configuring a VPC

This lab focuses on designing and configuring a secure virtual network using **Amazon Virtual Private Cloud (VPC)**.

Amazon VPC allows you to create an isolated network within AWS where you can control IP addressing, subnets, routing, and secure access to resources. 

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/53031def-4777-4a7e-8c72-83b5b5144048" />

<img width="1844" height="948" alt="image" src="https://github.com/user-attachments/assets/e09debdb-fa01-41f9-8098-edc9c0b0c08d" />

---

## What I Did

In this lab, I built a structured and secure cloud network and configured access between public and private resources.

<ul>
<li>Created a <b>VPC</b> with both <b>public and private subnets</b></li>
<li>Configured an <b>Internet Gateway</b> for external access</li>
<li>Set up a <b>NAT Gateway</b> to enable outbound internet access for private subnet resources</li>
<li>Configured <b>route tables</b> to manage local and internet-bound traffic</li>
<li>Launched a <b>bastion host (EC2 instance)</b> in the public subnet</li>
<li>Used the bastion host to securely connect to an instance in the private subnet</li>
</ul>

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f01ff984-1626-4aea-9f68-5338d76b5208" />

---

## Skills Demonstrated

<ul>
<li>VPC architecture design (public vs private subnets)</li>
<li>Network security and controlled access</li>
<li>Routing configuration using Internet Gateway and NAT Gateway</li>
<li>Secure remote access using a bastion host</li>
<li>Understanding layered cloud network design</li>
</ul>

---

## Outcome

By completing this lab, I gained hands-on experience in building a secure and scalable network architecture in AWS, including controlled access to private resources. This is a key skill for cloud engineering and cloud security roles.
