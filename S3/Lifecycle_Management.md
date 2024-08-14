#  Lifecycle Management

Lifecycle Management of object in S3 Buckets to move objects to different storage classes based on lifecyle rule

Different Storage Classes
<img width="936" alt="image" src="https://github.com/user-attachments/assets/6ced5d1b-c7dd-47ee-86b4-1b476f413fa0">

## Steps
1. Create Lifecyle rule

## 1. Create Lifecyle rule
**I. On AWS S3 Window, Click Buckets on left pane > Select Bucket**

<img width="419" alt="image" src="https://github.com/user-attachments/assets/d1b4220a-00a5-49be-abb1-0830fcc689cc">

**II. On Select Bucket, Click Management > Click Create lifecycle rule**

<img width="787" alt="image" src="https://github.com/user-attachments/assets/7d176d52-1b9b-4cd1-a0d8-9fcbc30cfaea">

**III. On Create Lifecycle rule Window, Fill in details as desired**

Fill in Lifecycle rule name > Choose rule scope 

Apply to all objects in bucket is being used as rule scope and will mean that all object inside the bucket will follow the lifecyclye rule created
<img width="376" alt="image" src="https://github.com/user-attachments/assets/11ff74a0-bda6-4787-883f-6337ceae219d">

Choose Lifecycle rule actions as desired

<img width="369" alt="image" src="https://github.com/user-attachments/assets/b8ee6758-3be2-485f-8e01-55a68c4a4f1f">

Transition selected
S3 Standard > S3 Standard-IA (After 30 days) > Glacier (After 90 days)

<img width="365" alt="image" src="https://github.com/user-attachments/assets/8a62c3ab-6dfe-48c3-841d-3d9d17c398e8">

Review lifecycle rule > Click Create Rule

<img width="374" alt="image" src="https://github.com/user-attachments/assets/783f3d6a-19c5-4f2c-bc9e-5a093c69eee3">

**IV. Verify rule created**

<img width="894" alt="image" src="https://github.com/user-attachments/assets/6bb39123-254d-447d-9183-296de9ea0adc">

## Note
Creating lifecycle management dependes on data used regarding how frequent data is being used. Planning needs to be carefully reviewed to implement the best lifecycle rule

S3 Intelligent-Tiering can be selected in cases where data access has no specific patterns and will be automatically move to different storage classes. However, monitoring fee per object may incur charges.

