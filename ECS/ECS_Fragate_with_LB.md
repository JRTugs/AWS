#  Elastic Container Service using Fargate

Setting up ECS using Fargate with loadbalancer and using public AWS ECR.

## Steps
1. Create Task Group
2. Create Load Balancer
3. Create Cluster
4. Create Task Definition
5. Create Service under newly create Cluster
6. Verify Service and Task are running
7. Verify website is accessible

## Pre-requisite
1. AWS ECR image
2. Task Role create in IAM with ecsTaskExecutionRole

## 1. Create Task Group
**I. On EC2 Window, Select Target Groups on the left pane > Click Create Target Group**

<img width="918" alt="image" src="https://github.com/user-attachments/assets/4b43d818-9607-4dbc-bbf4-7498f890b280">
 
**II. On Specify Group Details Window,  Fill in details below**

Select IP Addresses, Fill in Target Group Name

<img width="422" alt="image" src="https://github.com/user-attachments/assets/098adeaa-ef17-4348-90ee-a92440a57e0a">

Port of target image

<img width="412" alt="image" src="https://github.com/user-attachments/assets/b6fdfbcd-ccab-425a-bec8-2c595cea0f4a">

Select VPC and other details (optional) > Once Completed, Click Next

<img width="409" alt="image" src="https://github.com/user-attachments/assets/e4b221c4-f04a-49a2-8828-1ba066fa1503">

**II. On Register Targets > Click Create Target Groups**

<img width="830" alt="image" src="https://github.com/user-attachments/assets/460a94a1-10ee-4703-9e52-5a8c6271cb92">

## 2. Create Load Balancer
**I. On EC2 Window, Click Load Balancers on left pane > Click Create Load Balancer**

<img width="926" alt="image" src="https://github.com/user-attachments/assets/5398e1d6-2672-4f4e-89a0-bed186f2ef06">

**II. On Load Balancer Types Windows > Select Create under Application Load Balancer**

<img width="413" alt="image" src="https://github.com/user-attachments/assets/439d214e-af88-4682-9a48-e33384582432">

**III. On Create Application Load Balancer > Fill in details **

<img width="557" alt="image" src="https://github.com/user-attachments/assets/2e2f1286-4ab8-4294-9ce2-e95280ab06ad">

Select more than 2 Subnet

<img width="549" alt="image" src="https://github.com/user-attachments/assets/a0cd13b7-3411-4153-91f7-90b7550356a0">

Select Security Group

<img width="554" alt="image" src="https://github.com/user-attachments/assets/4588415d-8a0a-44d2-8579-6c1c46e280bf">

Select Image Port and Target  group newly created

<img width="562" alt="image" src="https://github.com/user-attachments/assets/fbc899cc-5205-48b7-8daa-2edbd53e4ee5">


Once completed, Click Create Load Balancer

<img width="556" alt="image" src="https://github.com/user-attachments/assets/e755269a-3dc6-42a5-aa6b-9935a5fbab09">

## 3. Create Cluster
**I. On AWS ECS Console, Click Cluster on left pane > Click Create Cluster**

<img width="919" alt="image" src="https://github.com/user-attachments/assets/9451014b-07c1-4075-873c-2f5f25af1b20">

**II. On Create Cluster Window, Fill in details > Once done, Click Create**
1. Fill in Cluster Name
2. Select AWS Fargate
3. Monitoring (Optional)

<img width="331" alt="image" src="https://github.com/user-attachments/assets/51724972-1bea-4204-ae2d-0f5cab6ea77d">

## 4. Create Task Definition
**I. On AWS ECS Window, Click Task Definitions on left pane > Click Create new task definition**

<img width="919" alt="image" src="https://github.com/user-attachments/assets/3100197c-e84b-4d05-96c3-983a5bc0b00f">

**II. On Create new task definition Window, Fill in details > Once done, Click Create**
1. Fill in Task Definition Family name
2. Select AWS Fargate
3. Select proper OS, Architecture and Network MOde
4. Select Task Role
5. Under Container, Fill in the Name and the paste the IMAGE URI coming from AWS ECR Image
6. Specify port mappings based on what port is being exposed by the image (in this image port 8080 is being used and exposed)
7. Fill in other details (Optional)

<img width="449" alt="image" src="https://github.com/user-attachments/assets/e718b5db-1e0b-4c35-85bf-4ec53aadc74f">

<img width="439" alt="image" src="https://github.com/user-attachments/assets/759b3c62-edef-4462-97cb-b93840c37748">

<img width="458" alt="image" src="https://github.com/user-attachments/assets/a1eb6ee4-8c86-4c40-957e-dfdf5d1d4d9b">

## 5. Create Service under newly create Cluster
**I. On AWS ECS Window, Click Cluster on left pane > Select the newly created Cluster**

<img width="362" alt="image" src="https://github.com/user-attachments/assets/e0ad14d0-285a-4834-b385-a73b9c2a102a">

**II. On Cluster window, Click Service > Click Create**

<img width="766" alt="image" src="https://github.com/user-attachments/assets/5a5a6668-9ffb-46dd-b4cc-9609db93c81a">

**III. On Create Window, Select details below**

Select Launch Type

<img width="550" alt="image" src="https://github.com/user-attachments/assets/6af2c036-bfa5-4add-be69-cdc7f121d0ea">

On Deployment Configuration, Select Service > Select the Task Definition newly created > Put Service Name > Desired Task should be minimum 2

<img width="547" alt="image" src="https://github.com/user-attachments/assets/c9389fc7-406f-4d60-bfaa-395eb6eb4e16">

On Load Balancing, Fill in details below

<img width="554" alt="image" src="https://github.com/user-attachments/assets/4d75ada6-12b0-4d3a-b5c0-727d9cb31343">

<img width="559" alt="image" src="https://github.com/user-attachments/assets/dbd64422-43cd-4563-99f1-366c1a26660e">

Once Completed, Click Create

<img width="562" alt="image" src="https://github.com/user-attachments/assets/4e2d7eb8-e908-43f3-a43c-1164906b4dda">

## 6. Verify Service and Task are running

Service running under cluster-helloworldapp

<img width="773" alt="image" src="https://github.com/user-attachments/assets/75ac7498-90ff-4c44-b7a2-16c0f4b1f2f7">

2 Tasks running under cluster-helloworldapp

<img width="772" alt="image" src="https://github.com/user-attachments/assets/45199ea7-b1c3-4f56-a1e5-db334b3b1bbd">

## 7. Verify website is accessible

Get DNS Name under Load Balancer

<img width="811" alt="image" src="https://github.com/user-attachments/assets/dc349bf5-bfc0-4520-93b3-e32192dc1444">

Paste it in browser and add port 8080

<img width="345" alt="image" src="https://github.com/user-attachments/assets/bb43242b-e92e-49e0-a0fe-96db3bf27c8e">





