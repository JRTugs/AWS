#  S3 Bucket Cross Region Replication

Replicate object on S3 Bucket between different regions.

## Steps
1. Create S3 Bucket on different region
2. Setup Replication rules on source S3 Bucket
3. Upload objects in source bucket and check destination bucket

## 1. Create S3 Bucket on different region
**I. On AWS Console, Click Region on top right > Select desired Region**

<img width="197" alt="image" src="https://github.com/user-attachments/assets/f4be4fab-9a82-48fe-aea4-cffc5ea26f9b">

**II. On Amazon S3 Bucket, Create new Bucket**
Note: Bucket Versioning should be enable for Cross Region Replication

**III. Verify new bucket**

<img width="417" alt="image" src="https://github.com/user-attachments/assets/f6c392d7-0be3-43f5-974b-2efc3102dc50">

## 2. Setup Replication rules on source S3 Bucket
**I. On Amazon S3 Window, Select the source S3 Bucket**

<img width="778" alt="image" src="https://github.com/user-attachments/assets/76b9b382-8a46-4ee3-be0b-6062e9dd2fa1">

**II. On Bucket Window, Click Management > Click Replication Rule**

<img width="817" alt="image" src="https://github.com/user-attachments/assets/be82fbd9-33bd-4c42-b893-ca4e1ef5e9ca">

**III. On Create Replication Rule Window, Fill in details**

Fill in Replication name

<img width="334" alt="image" src="https://github.com/user-attachments/assets/695ae08a-3951-4868-b2b3-0aade2f29da6">

Setup Source and Destination bucket

<img width="332" alt="image" src="https://github.com/user-attachments/assets/0e3be6f0-c246-4b63-9278-71ee85eb3839">

On IAM Role, Select create new role or select existing IAM roles if present

<img width="339" alt="image" src="https://github.com/user-attachments/assets/98751a0b-6997-4377-bccc-4564a9936fb7">

Once completed, Click Save

<img width="325" alt="image" src="https://github.com/user-attachments/assets/da2a768e-d392-468d-8e61-0dbf1e26d473">

## 3. Upload objects in source bucket and check destination bucket
**I. Upload new object on source bucket**

<img width="502" alt="image" src="https://github.com/user-attachments/assets/403030d9-1d0f-4e67-a977-b9619c6c2111">

**II. Verify in Destination Bucket**

<img width="504" alt="image" src="https://github.com/user-attachments/assets/1a60fda9-16a6-482a-872e-cdf889462f7b">






