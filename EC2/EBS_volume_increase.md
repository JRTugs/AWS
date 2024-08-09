#  Increasing EBS root volume on EC2 instance

## Steps
1. Take Snapshot of EBS Volume (Backup)
2. Increase EBS Volume size in AWS Console
3. Extend a Linux File system after resizing a volume

## 1. Take Snapshot of EBS Volume (Backup)
**I. Go to EC2 > Instances > Select EC2 instance > Select Storage > Click Volume ID**

<img width="793" alt="image" src="https://github.com/user-attachments/assets/4cab9a8f-56b0-4f73-a44f-3710db764abb">

**II. On Volume window > Select EBS Volume > Click Action > Click Create Snapshot**

<img width="756" alt="image" src="https://github.com/user-attachments/assets/538f2ada-1ada-406c-87bf-2ce1fd9ea35b">


**III. On Create snapshot window, Input Description > Create Snapshot**

<img width="413" alt="image" src="https://github.com/user-attachments/assets/58fd226d-25fa-4c5a-b8b6-f3d3ca9c341d">

**IV. Go to Snapshot tab on the left > Verify the new snapshot created**

<img width="924" alt="image" src="https://github.com/user-attachments/assets/18e0d705-3c56-4d65-aedc-b0edd1945348">



## 2. Increase EBS Volume size in AWS Console
**I. Go to EC2 > Instances > Select EC2 instance > Select Storage > Click Volume ID**

<img width="793" alt="image" src="https://github.com/user-attachments/assets/4cab9a8f-56b0-4f73-a44f-3710db764abb">

**II. On Volume window > Select EBS Volume > Click Action > Click Modify Volume**

<img width="781" alt="image" src="https://github.com/user-attachments/assets/83d4ee06-a7db-4907-aa2f-49069a54fe96">

**III. On Modify Volume window, Increase the Size (GiB) as desired > Click Modify > Review > Click Modify again**

<img width="419" alt="image" src="https://github.com/user-attachments/assets/c1aac3c4-b1f4-41c7-a826-578b88c40bc6">

**IV. Check Volume state if 100% completed**

<img width="809" alt="image" src="https://github.com/user-attachments/assets/d1dfea2b-0331-4789-a968-9b491efce151">

**V. Verify Size is increased**

<img width="500" alt="image" src="https://github.com/user-attachments/assets/beb7e047-2740-404b-afd8-485186330272">



## 3. Extend a Linux File system after resizing a volume
**I. Access the EC2 instance via CLI/SSH > Verify using command below**
```bash
df -h
```

<img width="222" alt="image" src="https://github.com/user-attachments/assets/3ec8c13d-0e3c-44a7-a65d-a0d309e23fb3">

```bash
lsblk
```

<img width="200" alt="image" src="https://github.com/user-attachments/assets/58f88f5f-b8b6-4379-8743-34a90f3b5879">

**II. Extend the partition**
```bash
growpart /dev/xvda 1
```

<img width="394" alt="image" src="https://github.com/user-attachments/assets/88c23d30-dd6d-46a7-9049-4eebbc4e4dd0">

**III. Extend Filesystem**
[XFS File system]
```bash
xfs_growfs -d /
```
[EXT4 File System]
```bash
resize2fs /dev/xvda1
```

**III. Verify disk extended**
```bash
df -h
```

```bash
lsblk
```














