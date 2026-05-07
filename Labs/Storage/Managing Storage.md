# Automated EBS Data Protection and S3 Hybrid Synchronization

## Lab Overview
I implemented an automated data lifecycle management strategy across AWS storage services. This project involved utilizing the AWS CLI and Python scripting to orchestrate EBS volume snapshots, alongside implementing a hybrid synchronization and recovery workflow using Amazon S3 Versioning.

Here is the architecture of this solution:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0f6af50c-d222-4321-b0ac-66ae5ab1fa07" />

## Key Achievements & Technical Milestones

The first two steps of creating & attaching a bucket from AWS Management Console are documented below:

<b>1</b>
<img width="925" height="483" alt="Screenshot 2026-05-07 191039" src="https://github.com/user-attachments/assets/5e486302-ab28-4d2a-b69f-47ec501af6af" />

<b>2</b>
<img width="924" height="458" alt="Screenshot 2026-05-07 191623" src="https://github.com/user-attachments/assets/363ab395-d38e-4c14-9828-3dbf2660c147" />


### 1. Automated Snapshot Orchestration
* **CLI-Driven Backups:** Utilized the AWS CLI to programmatically identify EBS Volume IDs and execute point-in-time snapshots of the "Processor" instance.

An example of working with commands as above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ef71818e-c211-40bd-b520-986811112205" />

* **Cron-Based Scheduling:** Configured a Linux `cron` scheduler to automate high-frequency snapshots, ensuring a granular Recovery Point Objective (RPO).

Here it is visible these snapshot got created as expected:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1ad8c9c5-27fc-431f-8803-39a921cfe3d1" />

* **Snapshot Lifecycle Management:** Deployed a Python script (`snapshotter_v2.py`) to automatically prune outdated backups, maintaining a strict retention policy of the two most recent snapshots to optimize storage costs.

Demonstration of the work in progress as per the previous step:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3ca0a1cf-7484-431e-8fc4-b8ccb1ef6715" />


### 2. S3 Hybrid Synchronization & Data Integrity
* **S3 Sync Deployment:** Orchestrated a secure data transfer from local EBS directories to an Amazon S3 bucket using the `aws s3 sync` command.
* **One-Way Synchronization:** Implemented the `--delete` flag to mirror local file deletions within the S3 bucket, maintaining high-fidelity synchronization between block and object storage.

### 3. Advanced Disaster Recovery (DR)
* **S3 Versioning Implementation:** Activated bucket-level versioning to protect against accidental deletions and data corruption.
* **Object Restoration Workflow:** Executed a complex recovery procedure using `s3api list-object-versions` and `get-object` to identify and retrieve specific file versions via their `VersionId`, successfully bypassing "Delete Markers."

### 4. Infrastructure Security & Governance
* **Least Privilege Access:** Managed cross-service permissions by attaching targeted IAM instance profiles to EC2 resources, enabling secure API calls to EBS and S3 without hardcoded credentials.
* **Remote Administration:** Conducted all administrative tasks via a dedicated "Command Host" utilizing EC2 Instance Connect for secure, browser-based shell access.

This confirms successful completion of challenge steps 2-4 above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9c24fc8c-2056-4b38-be08-35b20d29000d" />

---
**Tech Stack:** AWS CLI, Amazon EBS (Snapshots), Amazon S3 (Versioning, Sync), Linux (Cron, Python), IAM.
