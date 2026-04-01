## Lab Overview – Configuring a VPC

This lab focuses on designing and configuring a secure virtual network using **Amazon Virtual Private Cloud (VPC)**.

Amazon VPC allows you to create an isolated network within AWS where you can control IP addressing, subnets, routing, and secure access to resources. 

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/53031def-4777-4a7e-8c72-83b5b5144048" />

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

<img width="1844" height="948" alt="image" src="https://github.com/user-attachments/assets/e09debdb-fa01-41f9-8098-edc9c0b0c08d" />

<img width="1851" height="996" alt="image" src="https://github.com/user-attachments/assets/a37d1e15-6874-4180-ba79-e86ebaadfb23" />

<img width="1856" height="950" alt="image" src="https://github.com/user-attachments/assets/4de06980-d5bc-4db0-859c-dd2753d234e3" />

<img width="1850" height="865" alt="image" src="https://github.com/user-attachments/assets/b3659103-60bd-4ebb-b949-0313361cf6b1" />

<img width="1826" height="819" alt="image" src="https://github.com/user-attachments/assets/9e47fdd8-f933-4a7b-9ab7-ef3498f2fc51" />

<img width="1840" height="888" alt="image" src="https://github.com/user-attachments/assets/76bd2104-3615-4516-a7c6-064468c29f39" />

<img width="1854" height="820" alt="image" src="https://github.com/user-attachments/assets/5f71095c-d2bf-4f28-9a77-487f80913a07" />

<img width="1827" height="825" alt="image" src="https://github.com/user-attachments/assets/fbb68d48-bb7a-4ce0-a4f8-4d0e17c6b3aa" />

<img width="1845" height="887" alt="image" src="https://github.com/user-attachments/assets/6833640e-3ebd-4c16-9d72-a50230b8ecd2" />

<img width="1832" height="821" alt="image" src="https://github.com/user-attachments/assets/ff25a43b-86e3-4aa9-94f3-c568e412e9f3" />

<img width="1842" height="786" alt="image" src="https://github.com/user-attachments/assets/d034039f-5119-439c-bcb9-f213ef517bc6" />

<img width="1859" height="916" alt="image" src="https://github.com/user-attachments/assets/e32a99aa-8495-44cb-bf6e-39e22ded06ed" />

<img width="1840" height="825" alt="image" src="https://github.com/user-attachments/assets/40f0b570-8ea2-4f5c-9a8e-1e75459726b7" />

<img width="1847" height="835" alt="Screenshot 2026-04-01 170401" src="https://github.com/user-attachments/assets/c25efb6e-aadc-4e08-ba5b-bd3e71a6c622" />

<img width="1847" height="848" alt="image" src="https://github.com/user-attachments/assets/11754f19-2e28-4a0a-b318-682ff30668c7" />

<img width="1847" height="840" alt="image" src="https://github.com/user-attachments/assets/a8844bc6-4792-4f4a-8ba0-df95040ea1ae" />

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
