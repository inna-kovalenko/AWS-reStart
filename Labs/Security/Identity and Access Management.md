# Identity and Access Management (IAM) Foundations

## Lab Overview
I implemented a robust access control framework using **AWS Identity and Access Management (IAM)** to manage identity lifecycle and resource security. This project focused on enforcing the **Principle of Least Privilege** by configuring custom password policies, managing user groups, and auditing JSON-based permission structures for diverse technical roles.

This demonstrates the breakdown of the task with the diagram AIM infrastructure:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/251be133-84e3-48d1-815d-2a70e4e20baf" />


## Key Achievements & Technical Milestones

### 1. Governance & Password Policy Enforcement
*   Strengthened account-level security by implementing a **Custom Password Policy** with a 10-character minimum.
*   Mandated high-complexity requirements including uppercase, lowercase, numbers, and non-alphanumeric symbols.
*   Configured security hygiene standards by enabling **Password Expiration** (90 days) and **Preventing Password Reuse**.

### 2. IAM Architecture & User Management
*   Organized pre-created IAM identities into functional **User Groups** (`S3-Support`, `EC2-Support`, and `EC2-Admin`) to streamline administrative overhead.
*   Mapped specialized staff to their respective groups, enabling automated inheritance of required security credentials and permissions.
*   Audited IAM users to ensure no direct permissions were attached to individual accounts, adhering to group-based management best practices.

### 3. Policy Analysis & Permission Scoping
*   Inspected **AWS Managed Policies** (e.g., `AmazonS3ReadOnlyAccess`) to define granular read-only access for support staff.
*   Analyzed **Customer Inline Policies** to grant advanced operational rights, such as allowing an administrator to start and stop EC2 instances.
*   Deciphered JSON policy structures to evaluate the interaction between **Effect**, **Action**, and **Resource** elements.

### 4. Security Validation & Testing
*   Conducted multi-user validation using the **IAM Sign-in URL** and Private browser sessions to simulate real-world access scenarios.
*   Verified the **Principle of Least Privilege** by confirming:
    *   **User-1 (S3 Support):** Confirmed access to S3 buckets while maintaining "Access Denied" for EC2 services.
    *   **User-2 (EC2 Support):** Verified the ability to view EC2 instances while being restricted from destructive actions (Stop/Terminate).
    *   **User-3 (EC2 Admin):** Successfully validated administrative rights to modify instance states as permitted by the specific inline policy.

---
**Tech Stack:** AWS IAM (Users, Groups, Roles, Policies), Security Governance, JSON Policy Design.
