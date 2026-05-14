# Python Scripting & Linux Automation

## 1. Environment Deployment
*   **Provisioning**: Initialized an AWS EC2 instance named **Linux Host** within the lab environment.
*   **Infrastructure Mapping**: Documented the **Public IP address** and credentials to facilitate secure remote access.

## 2. Secure Connectivity
*   **Authentication**: Configured SSH access using a RSA key pair (in my case - `.ppk`).
*   **Remote Access**: Established a secure shell session to the **ec2-user** via the instance's public endpoint.

## 3. Python Development & Automation
*   **Script Engineering**: Developed a Python 3 script to algorithmically identify all **prime numbers between 1 and 250**.

Here is the script:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/79168e06-d110-4534-ad76-95b999755122" />

*   **Data Persistence**: Engineered the script to execute two primary functions:
    *   Outputted results directly to the terminal console for real-time verification.
    *   Automated the creation of a `results.txt` file to store the processed data.

This confirms both files (`results.txt`, `solution.py`) were successfully created & saved:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9ce7c4d8-ff4a-4908-b054-06be1eb03eab" />


## 4. Execution & Quality Assurance
*   **Deployment**: Executed the script using the `python3` interpreter on the Linux Host.
*   **Validation**: Verified the integrity of the `results.txt` output and confirmed the absolute file path for documentation.

The screenshot shows execution of the script & content of `results.txt` using `cat` to see the prime numbers inside the file without opening an editor:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7b5dec5f-08a4-424e-9fed-bdf3413133d3" />

