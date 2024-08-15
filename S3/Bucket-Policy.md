#  Bucket Policy

Setting up bucket policy on S3 bucket

## Steps
1. Disable Block Public Access on S3 Bucket
2. Create Bucket Policy using Policy generator
3. Verify Object can be accessed publicly

## 1. Disable Block Public Access on S3 Bucket
**I. On Amazon S3 Window, Click Buckets on left pane > Select Bucket**

<img width="383" alt="image" src="https://github.com/user-attachments/assets/27ec13af-f081-4157-851e-f2f2cfabb2d9">

**II. On Bucket Window, Click Permissions > Click Edit on Block Public Access**

<img width="760" alt="image" src="https://github.com/user-attachments/assets/f77fa730-3ca3-4071-9b9f-e42921220ca8">

**III. On Edit Block Public Access, Uncheck Block all public access > Click Save Changes > Confirm changes**

<img width="414" alt="image" src="https://github.com/user-attachments/assets/e49cedb1-4ba2-4a85-8df1-8667f0128ef4">

**IV. Verify "Block all public access" is off**

<img width="766" alt="image" src="https://github.com/user-attachments/assets/06ae646f-c545-4347-83bb-477a45931ac8">

## 2. Create Bucket Policy using Policy generator
**I. On Bucket Window, Click Edit under Bucket Policy**

<img width="770" alt="image" src="https://github.com/user-attachments/assets/e1e5e197-88cb-4dde-a466-1889edb91df9">

**II. On Edit Bucket Policy, Click Policy Generator**

<img width="768" alt="image" src="https://github.com/user-attachments/assets/206a7acb-a4e9-49ab-bea2-db11962f50cd">

**III. On AWS Policy Generator, Select details as desired**

Step 1: Select Type of Policy for "S3 Bucket Policy"

<img width="628" alt="image" src="https://github.com/user-attachments/assets/9154801c-dd50-4155-9408-fe212114af35">

Step 2: Add Statement
Effect: Allow / Deny Access
Principal: You can specify any of the following principals in a policy:

- AWS account and root user
- IAM roles
- Role sessions
- IAM users
- Federated user sessions
- AWS services
- All principals

  For Settings below, All principal is configured to allow all user to access the bucket
Actions: Specify what actions
Amazon Resource Name (ARN): ARN of bucket

Click Add Statement
<img width="617" alt="image" src="https://github.com/user-attachments/assets/5308d155-087b-48cb-bae5-6b57e768061b">

Step 3: Generate Poliy

<img width="643" alt="image" src="https://github.com/user-attachments/assets/ab5d411e-ba4a-4428-b9bc-244cf5104233">

**IV. Copy the Policy JSON Document from the Policy Generator**

<img width="409" alt="image" src="https://github.com/user-attachments/assets/edc1e1df-3f79-489b-998c-5c94967db3f3">

**V. Paste the Policy generated in the Bucket Policy > Once done, Click Save Changes**

<img width="800" alt="image" src="https://github.com/user-attachments/assets/5cfb7d9d-a351-490d-9c80-11b587afd6c2">

## 3. Verify Object can be accessed publicly
**I. Get Object URL from Object Overview**

<img width="784" alt="image" src="https://github.com/user-attachments/assets/bb180002-562e-4df2-9856-2d805e833356">

**II. Open Object URL on browser**

<img width="763" alt="image" src="https://github.com/user-attachments/assets/2191c8dd-c006-4c82-88b8-b47aae222d90">







