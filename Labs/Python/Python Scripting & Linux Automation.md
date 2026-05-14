# Python Scripting & Linux Automation

## 1. Environment Deployment
*   **Provisioning**: Initialized an AWS EC2 instance named **Linux Host** within the lab environment.
*   **Infrastructure Mapping**: Documented the **Public IP address** and credentials to facilitate secure remote access.

## 2. Secure Connectivity
*   **Authentication**: Configured SSH access using a RSA key pair (`.pem` or `.ppk`).
*   **Permission Management**: Applied `chmod 400` to the private key file to satisfy Linux security requirements for remote tunneling.
*   **Remote Access**: Established a secure shell session to the **ec2-user** via the instance's public endpoint.

## 3. Python Development & Automation
*   **Script Engineering**: Developed a Python 3 script to algorithmically identify all **prime numbers between 1 and 250**.
*   **Data Persistence**: Engineered the script to execute two primary functions:
    *   Outputted results directly to the terminal console for real-time verification.
    *   Automated the creation of a `results.txt` file to store the processed data.

## 4. Execution & Quality Assurance
*   **Deployment**: Executed the script using the `python3` interpreter on the Linux Host.
*   **Validation**: Verified the integrity of the `results.txt` output and confirmed the absolute file path for documentation.
