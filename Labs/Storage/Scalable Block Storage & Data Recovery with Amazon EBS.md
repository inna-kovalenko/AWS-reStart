# Scalable Block Storage & Data Recovery with Amazon EBS

## Lab Overview
I implemented a robust storage solution using **Amazon Elastic Block Store (EBS)**. This project focused on the full lifecycle of block storage: provisioning, mounting to Linux environments, ensuring data durability via snapshots, and executing a successful disaster recovery simulation.

## Key Achievements & Technical Milestones

### 1. Storage Provisioning & Network Alignment
* **Volume Lifecycle Management:** Provisioned a **General Purpose SSD (gp2)** volume, ensuring strict alignment with the EC2 instance's **Availability Zone** to enable low-latency block-level attachment.
* **Dynamic Hot-Plugging:** Successfully performed a "hot-attach" of a secondary volume to a running Linux instance without requiring a system reboot.

This shows completion of this task using AWS Management Console:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/68145a91-cab3-4c6d-9191-504959ca7fcf" />


### 2. Linux System Administration & Filesystem Mounting
* **Filesystem Engineering:** Formatted raw block storage into an **ext3** filesystem using `mkfs` and created logical mount points (`/mnt/data-store`).
* **Persistence Configuration:** Modified the system's filesystem table (`/etc/fstab`) to ensure persistent mounting across instance reboots, demonstrating high-availability best practices.
* **Disk Utility Auditing:** Utilized `df -h` and `lsblk` to monitor storage utilization and verify successful volume mapping.

### 3. Data Protection & Disaster Recovery (DR)
* **Point-in-Time Backups:** Executed an **Amazon EBS Snapshot** to capture a consistent state of the data volume and stored it durably in Amazon S3.
* **Recovery Simulation:** Successfully simulated a "Data Loss" event by deleting critical files, then performed a full restoration by:
    1. Creating a new EBS volume from the snapshot.
    2. Re-attaching and re-mounting the restored volume to a secondary mount point (`/mnt/data-store2`).
    3. Verifying 100% data integrity and recovery.

---
**Tech Stack:** Amazon EBS, Amazon EC2, Linux CLI, Bash Scripting, Amazon S3 (Snapshot storage).
