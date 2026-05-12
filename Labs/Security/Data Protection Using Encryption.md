# Data Protection Using Encryption

**Domain:** Security, Identity, & Compliance



**Key Concepts:** Cryptography, Symmetric Encryption, Key Management Service (KMS)

---

### ARCHITECTURAL SYNOPSIS
Implemented a comprehensive data protection workflow by leveraging **AWS Key Management Service (KMS)** to secure sensitive information on a cloud-hosted file server. The project focused on the lifecycle of data protection, ranging from the creation of administrative cryptographic keys to the programmatic execution of encryption and decryption tasks via the **AWS Encryption CLI**.

### ACHIEVEMENTS

#### 1. Cryptographic Key Engineering
* Provisioned a **Symmetric AWS KMS key** designed for fast and efficient data processing where the same key is utilized for both encryption and decryption.
* Configured granular **IAM administrative and usage permissions**, ensuring that only authorized roles (voclabs) could manage or invoke the key for cryptographic operations.
* Generated a unique **Amazon Resource Name (ARN)** for the key to serve as a secure identifier for CLI-based automation.

This confirms successful completion of the above steps:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d9943c9b-ce07-42c4-a438-dee1ef89517b" />


#### 2. Secure Environment Configuration
* Established secure communication between a remote **Amazon EC2 File Server** and AWS KMS by configuring transient AWS CLI credentials.
* Orchestrated the installation of the **AWS Encryption SDK CLI** using the Python package manager (pip) to enable advanced cryptographic features.
* Updated system pathing to ensure the encryption toolset remained accessible across the instance environment.

#### 3. Data Transformation and Security Best Practices
* Developed a standardized workflow for converting readable **plaintext** files into unreadable **ciphertext**, effectively hiding information from unauthorized users.
* Executed advanced encryption commands incorporating **encryption contexts** (e.g., purpose=test) and **commitment policies** to ensure high-security standards and data integrity.
* Validated command execution accuracy using system exit codes to confirm the successful generation of metadata and encrypted output files.

#### 4. Decryption and Integrity Validation
* Reverted ciphertext back into its original plaintext form by applying the symmetric key and matching cryptographic parameters.
* Verified the successful restoration of sensitive data, confirming that the decryption process accurately reproduced the initial information without corruption.

---

### TECH STACK AND COMPONENTS
* **Security & Encryption:** AWS Key Management Service (KMS), AWS Encryption SDK CLI
* **Compute:** Amazon EC2
* **Identity Management:** AWS IAM (Roles and Permissions)
* **Management Tools:** AWS Systems Manager Session Manager, AWS CLI

### OPERATIONAL VALUE
This project demonstrated a fundamental security principle: ensuring **data confidentiality** and **integrity** through automation. By utilizing managed keys and standardized encryption CLI tools, the architecture provides a scalable and secure method for protecting sensitive files at rest, reducing the risk of data exposure in cloud environments.
