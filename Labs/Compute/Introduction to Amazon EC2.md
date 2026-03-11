<b>Introduction to Amazon EC2</b>

<img width="1114" height="904" alt="image" src="https://github.com/user-attachments/assets/5686f271-39b6-48f5-b63c-6556541f8ecc" />
Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers, allowing organizations to deploy virtual machines within minutes and scale infrastructure according to demand. Through this lab I practiced the essential tasks required to operate and maintain cloud-based servers.

## Objectives

The goal of this lab was to understand how cloud infrastructure can be deployed and managed in a secure and scalable way.

By completing this lab, I practiced how to:

<ul>
<li>Launch a virtual server using <b>Amazon EC2</b></li>
<li>Configure <b>termination protection</b> to prevent accidental deletion</li>
<li>Monitor system performance using <b>Amazon CloudWatch</b></li>
<li>Modify <b>security group rules</b> to allow web traffic (HTTP)</li>
<li>Resize an EC2 instance to adjust compute capacity</li>
<li>Test termination protection controls</li>
<li>Safely terminate the instance after testing</li>
</ul>

## Lab Part 1
Sample tasks & solutions:

<img width="957" height="498" alt="image" src="https://github.com/user-attachments/assets/f2ba2bb0-e97a-4a7b-9d70-381c284b8df2" />

<img width="957" height="499" alt="image" src="https://github.com/user-attachments/assets/11600ed4-fae9-402d-869e-01da5f9ad238" />

## Lab Summary 1 – EC2 Instance Deployment

Completed the deployment and initial configuration of a web server using **Amazon EC2**.

<ul>
<li>Launched an EC2 instance named <b>Web Server</b></li>
<li>Selected <b>Amazon Linux 2023 AMI</b> and <b>t3.micro</b> instance type</li>
<li>Configured networking within a dedicated <b>VPC</b> and created a custom <b>security group</b></li>
<li>Improved security by removing SSH inbound access</li>
<li>Configured default <b>Amazon EBS</b> storage (8 GiB root volume)</li>
<li>Enabled <b>termination protection</b> to prevent accidental deletion</li>
<li>Deployed a web server automatically using a <b>User Data startup script</b></li>
<li>Installed and started an <b>Apache HTTP server</b> on instance launch</li>
<li>Verified instance status and system health checks in the EC2 console</li>
</ul>

## Lab Part 2

<img width="956" height="503" alt="image" src="https://github.com/user-attachments/assets/b78c8b42-394d-4fcd-9004-16d4ba247bd8" />

## Lab Summary – Monitoring and Web Server Access

Completed monitoring and network configuration tasks for the deployed EC2 instance.

<ul>
<li>Verified instance health using <b>Status Checks</b> (System and Instance reachability)</li>
<li>Reviewed performance metrics using <b>Amazon CloudWatch</b> monitoring</li>
<li>Captured an instance console screenshot for troubleshooting visibility</li>
<li>Retrieved the <b>Public IPv4 address</b> of the EC2 instance</li>
<li>Identified blocked HTTP access due to security group configuration</li>
<li>Updated the <b>security group inbound rules</b> to allow HTTP traffic (port 80)</li>
<li>Successfully accessed the deployed web server through a browser</li>
<li>Verified the web server response message: <b>"Hello From Your Web Server!"</b></li>
</ul>
