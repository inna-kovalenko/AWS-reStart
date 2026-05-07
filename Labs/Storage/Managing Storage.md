# Automated EBS Data Protection and S3 Hybrid Synchronization

## Lab Overview
I implemented an automated data lifecycle management strategy across AWS storage services. This project involved utilizing the AWS CLI and Python scripting to orchestrate EBS volume snapshots, alongside implementing a hybrid synchronization and recovery workflow using Amazon S3 Versioning.

Here is the architecture of this solution:
<img width="717" height="425" alt="image" src="https://github.com/user-attachments/assets/084a698e-bf92-4541-bd08-b4e4b0d89d99" />


## Key Achievements & Technical Milestones

### 1. Automated Snapshot Orchestration
* **CLI-Driven Backups:** Utilized the AWS CLI to programmatically identify EBS Volume IDs and execute point-in-time snapshots of the "Processor" instance.
* **Cron-Based Scheduling:** Configured a Linux `cron` scheduler to automate high-frequency snapshots, ensuring a granular Recovery Point Objective (RPO).
* **Snapshot Lifecycle Management:** Deployed a Python script (`snapshotter_v2.py`) to automatically prune outdated backups, maintaining a strict retention policy of the two most recent snapshots to optimize storage costs.

### 2. S3 Hybrid Synchronization & Data Integrity
* **S3 Sync Deployment:** Orchestrated a secure data transfer from local EBS directories to an Amazon S3 bucket using the `aws s3 sync` command.
* **One-Way Synchronization:** Implemented the `--delete` flag to mirror local file deletions within the S3 bucket, maintaining high-fidelity synchronization between block and object storage.

### 3. Advanced Disaster Recovery (DR)
* **S3 Versioning Implementation:** Activated bucket-level versioning to protect against accidental deletions and data corruption.
* **Object Restoration Workflow:** Executed a complex recovery procedure using `s3api list-object-versions` and `get-object` to identify and retrieve specific file versions via their `VersionId`, successfully bypassing "Delete Markers."

### 4. Infrastructure Security & Governance
* **Least Privilege Access:** Managed cross-service permissions by attaching targeted IAM instance profiles to EC2 resources, enabling secure API calls to EBS and S3 without hardcoded credentials.
* **Remote Administration:** Conducted all administrative tasks via a dedicated "Command Host" utilizing EC2 Instance Connect for secure, browser-based shell access.

---
**Tech Stack:** AWS CLI, Amazon EBS (Snapshots), Amazon S3 (Versioning, Sync), Linux (Cron, Python), IAM.
