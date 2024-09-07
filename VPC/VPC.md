# Creating Virtual Private Cloud

## Steps
1. Create VPC
2. Create Subnets
3. Create Internet Gateways
4. Create NAT Gateways
5. Create Routing Table

## 1. Create VPC
**I. On VPC Console, Click Your VPC > Click Create VPC**

<img width="929" alt="image" src="https://github.com/user-attachments/assets/93af2280-100b-4d45-9156-2032a05ec48c">

**II. On Create VPC Window, Fill the the details > Click Create VPC**

<img width="338" alt="image" src="https://github.com/user-attachments/assets/c202e6f5-32b1-46e2-9b53-ea2887a0a80d">

**III. Verify newly created VPC**

<img width="848" alt="image" src="https://github.com/user-attachments/assets/20f036ce-38c0-4c9f-9280-18f75eda9b09">

## 2. Create Subnets
**I. On VPC Console, Click Subnets > Click Create Subnets**

<img width="937" alt="image" src="https://github.com/user-attachments/assets/e1f6c130-d05c-4834-a8fe-9f42adc0f0dc">

**II. On Create Subnet Window, Select the VPC and Create desired subnets under the IPv4 CIBR block. Once Completed, Click Create Subnet**

<img width="330" alt="image" src="https://github.com/user-attachments/assets/5889e183-57b5-471b-8fd5-d20b844c1653">

Subnet 1

<img width="326" alt="image" src="https://github.com/user-attachments/assets/d0dc6361-32fc-4422-9dd4-afc1e792c864">

Subnet 2

<img width="326" alt="image" src="https://github.com/user-attachments/assets/845e3d72-e07b-428d-b065-4fd4198163ac">

Public Subnet 1

<img width="287" alt="image" src="https://github.com/user-attachments/assets/97558bba-6a6a-406d-8cd1-5b66dc9a4744">

Public Subnet 2

<img width="321" alt="image" src="https://github.com/user-attachments/assets/3ec959dc-c5e1-473f-96e3-a3a57076f06d">

```bash
Note: You may create as many subnets under the CIDR Block
```

**III. Verify subnet created**

<img width="839" alt="image" src="https://github.com/user-attachments/assets/64856ef0-e647-420a-9318-1e7eb660d957">


## 3. Create Internet Gateways

**I. On VPC Console, Click Internet Gateways > Click Create Internet Gateway**

<img width="932" alt="image" src="https://github.com/user-attachments/assets/e93da349-aeb3-4e32-9491-ea48986c8303">

**II. On Create Internet Gateway window, Fill in details and Click Create Internet Gateway**

<img width="344" alt="image" src="https://github.com/user-attachments/assets/d4cfb480-75df-4d0b-83b8-ad1e1910c024">

**III. Attach newly create internet gateway to VPC**

<img width="836" alt="image" src="https://github.com/user-attachments/assets/ee98c03a-6f1e-4fd8-bd41-2312cb256395">

<img width="334" alt="image" src="https://github.com/user-attachments/assets/461ef875-3524-4df7-a0bd-1128ad2dfaa1">

**IV. Verify Internet Gateway is attached**

<img width="838" alt="image" src="https://github.com/user-attachments/assets/89a77a6f-9670-4845-a5e0-b14d66941a81">

## 4. Create NAT Gateways
**I. On VPC Console, Click NAT Gateways > Click Create NAT Gateways**

<img width="932" alt="image" src="https://github.com/user-attachments/assets/bfbbc57a-b7aa-4def-86a1-328d30a2d6b0">

**II. On Create NAT Gateway window, Fill in details**

<img width="338" alt="image" src="https://github.com/user-attachments/assets/1c664989-c0ea-4343-afea-92987f00f16b">

```bash
Note: Create NAT Gateway for each public subnet on each availability zone
```

**III. Verify NAT Gateway created**

<img width="839" alt="image" src="https://github.com/user-attachments/assets/5c749b6c-3a99-4d06-8255-bd72c3cce49b">

## 4. Create Routing Table

After creation of VPC, there will be a main default route table created for the CIDR Block. For the purpose of this project, Main(Default) route table will be used for private subnet and will create a new public route table for the public subnets

**I. On VPC Console, Click Route tables > Click Create Route Tables**

<img width="935" alt="image" src="https://github.com/user-attachments/assets/c513a619-fbc8-45e5-8620-8e2aa4d438fe">

**II. On Create route table window, fill in details and correct VPC and click Create Route table**

<img width="346" alt="image" src="https://github.com/user-attachments/assets/241ba047-1050-4646-b2d4-b32732cec21a">

**III. On Public route table, Click Subnet Associtaion > Click Edit Subnet Associtaion**

<img width="838" alt="image" src="https://github.com/user-attachments/assets/49b94ee9-5b57-4829-80de-e4c094567297">

**IV. On Edit Subnet Associations, Select Public Subnet and click Save Associations**

<img width="936" alt="image" src="https://github.com/user-attachments/assets/fe684335-508b-46c9-a2cc-dc64d307ac9f">

**V. Verify association**

<img width="839" alt="image" src="https://github.com/user-attachments/assets/7b8a4958-96c0-4569-bcc9-d46aabaf1955">

**VI. Edit Main Route table to add NAT GW as internet access**

Edit Route table

<img width="850" alt="image" src="https://github.com/user-attachments/assets/d203d278-8250-4403-adb4-34b30d7996be">

Add NAT Gateway for internet access

<img width="933" alt="image" src="https://github.com/user-attachments/assets/92eaebd9-802c-4714-8b21-44b3e7611dce">

**VII. Edit Public Route table and add internet gateway as internet access**

<img width="937" alt="image" src="https://github.com/user-attachments/assets/e269faa1-2c92-495c-862c-a2428c5161e1">

Diagram of VPC

Private Subnet in Main route table using NAT gateway for internet access

<img width="590" alt="image" src="https://github.com/user-attachments/assets/a68fbebc-ced9-4511-bd68-c10167fe4ee1">

Public Subnet in PublicRT route table using Internet gateway for internet access

<img width="590" alt="image" src="https://github.com/user-attachments/assets/7a124121-1b2d-4156-b69b-d65e48ef9f68">



