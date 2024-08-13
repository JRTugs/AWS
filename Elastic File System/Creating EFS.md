#  Elastic File System

Setting up Elastic File System 

## Steps
1. Create Security Group
2. Create EFS
3. Mount EFS on EC2 instance
4. Add mount in /etc/fstab to mount automatically after reboot

## Pre-requisite
1. EC2 instance
2. VPC
3. Security Group

## 1. Create Security Group
**I. On VPC Window, Click Security Groups on left pane > Click Create Security Group**

<img width="925" alt="image" src="https://github.com/user-attachments/assets/a67798b8-9c88-4747-8b48-a2ab9d6cd532">

**II. On Create Security Group Window, Fill in the details below**

Fill in Security Group name, Description and VPC

<img width="377" alt="image" src="https://github.com/user-attachments/assets/168115c9-90e2-4dc8-9334-18d5b6d322a3">

Add Inboud rules for VPC Access

<img width="911" alt="image" src="https://github.com/user-attachments/assets/b5e5e7ff-79a2-4744-81a4-62df507ce2df">

Once done, Click Create Security Group

<img width="911" alt="image" src="https://github.com/user-attachments/assets/8061883e-6f7b-4342-9c94-4d997c1768b9">

## 2. Create EFS
**I. On Elastic File System Window, Click File System on left pane > Click Create File System**

<img width="915" alt="image" src="https://github.com/user-attachments/assets/2acd22c9-63eb-4259-9fa1-40c92283b3dc">

**II. On Create File System Window, Fill in Name and VPC. Once done, Click Create**

<img width="293" alt="image" src="https://github.com/user-attachments/assets/42f5db13-e492-4b26-899d-eb44bca5396e">

**III. Go back to File Systems and Select the new file system created to modify network**

<img width="779" alt="image" src="https://github.com/user-attachments/assets/5f9d0ebd-6fae-4689-9dca-e0c6b8b3a208">

**IV. Inside File System created, Select Network and Click Manage**

<img width="814" alt="image" src="https://github.com/user-attachments/assets/b1650615-15ac-4af5-8b95-61175e57aafb">

**V. Add EFS security group on each Availability Zones > Click Save**

<img width="837" alt="image" src="https://github.com/user-attachments/assets/20377e3b-8eef-43b5-a98a-ffbe8f0510de">

## 3. Mount EFS on EC2 instance
**I. Create directory**
```bash
mkdir /root/efs
```

**II. Get mount command from EFS Console Window**

Click Attach

<img width="842" alt="image" src="https://github.com/user-attachments/assets/e1b28f2f-0900-4639-93b6-ebc9a320072e">

Copy mount command (update the path as it should be)

<img width="563" alt="image" src="https://github.com/user-attachments/assets/052ea618-b083-4c61-b616-6d81bd46bf70">

Verify if NFS is mounted and create a testfile

<img width="224" alt="image" src="https://github.com/user-attachments/assets/dc183bfb-3ce5-41d9-853b-443961056c40">

## 4. Add mount in /etc/fstab to mount automatically after reboot
**I. vi /etc/fstab and add following details below**

[fs-XXXXXXXX].efs.[REGION].amazonaws.com:/ /path/to/mount/dir nfs4 nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 0 0

```bash
fs-0c62b69c98459ea1e.efs.us-east-1.amazonaws.com:/ /root/efs nfs4 nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 0 0
```

**II. Test reboot the system if possible and check if filesystem is mounted**

```bash
reboot
```












