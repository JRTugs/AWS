#  Attaching new EBS Volume on EC2 Instance

## Steps
1. Create an EBS Volume
2. Attach EBS Volume to EC2 Instance
3. Verify new volume in EC2 instance via CLI
4. Create a Filesystem on the EBS Volume
5. Mount the EBS Volume
6. Add to FSTAB

## 1. Create an EBS Volume
**I. On AWS Console, Click Volume > Click Create Volume**

<img width="927" alt="image" src="https://github.com/user-attachments/assets/3b12ff3f-3aee-43d1-b803-ad101a161dff">

**II. On Create Volume, Fill in the details > Click Create Volume**

<img width="276" alt="image" src="https://github.com/user-attachments/assets/55b0ce9e-ec29-4e58-97de-ebb86d805dd1">

**III. Verify newly create volume**

<img width="824" alt="image" src="https://github.com/user-attachments/assets/dd1290cf-dccc-4281-83f6-f05af3e18abf">



## 2. Attach EBS Volume to EC2 Instance
**I. Select the new volume create > Click Action > Click Attach Volume**

<img width="794" alt="image" src="https://github.com/user-attachments/assets/78543693-799a-41dd-8302-ca175dfb8725">

**II. On Attach Volume window, Select the EC2 instance and Device Name assigned > CLick Attach Volume**

<img width="392" alt="image" src="https://github.com/user-attachments/assets/eb8dc6c7-1c4b-4a21-968e-3d1e2e8394d3">

**III. To verify, Go to EC2 instance > Click Storage**

<img width="832" alt="image" src="https://github.com/user-attachments/assets/1150dd0b-89d7-481a-bafa-b94f05eb4348">

## 3. Verify new volume in EC2 instance via CLI
**I. Connect via SSH > verify newly added volume using command below**
```bash
lsblk
```
```bash
fdisk -l
```

<img width="282" alt="image" src="https://github.com/user-attachments/assets/d985da9b-6dbc-47cf-885f-bf7ad71d34bc">

## 4. Create a Filesystem on the EBS Volume
**I. Create directory for mount point**
```bash
mkdir -p /mnt/new_volume
```

**II. format volume**
```bash
mkfs -t ext4 /dev/xvdb
```

**III. Verify new file system**
```bash
 file -s /dev/xvdb
```

## 5. Mount the EBS Volume
**I. Mount EBS Volume**
```bash
mount /dev/xvdb /mnt/new_volume
```

**II. Verify new volume mounted**
```bash
df -h
```

```bash
lsblk
```

## 6. Add to FSTAB
**I. Add volume in /etc/fstab**
```bash
/dev/xvdb   /mnt/new_volume   ext4   defaults,nofail   0   2
```




