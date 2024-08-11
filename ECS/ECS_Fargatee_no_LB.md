#  Elastic Container Service using Fargate

Setting up ECS using Fargate with no loadbalancer and using public AWS ECR.

## Steps
1. Create Cluster
2. Create Task Definition
3. Create Task under newly create Cluster
4. Verify Task is running
5. Verify website is accessible

## Pre-requisite
1. AWS ECR image
2. Task Role create in IAM with ecsTaskExecutionRole

## 1. Create Cluster
**I. On AWS ECS Console, Click Cluster on left pane > Click Create Cluster**

<img width="919" alt="image" src="https://github.com/user-attachments/assets/9451014b-07c1-4075-873c-2f5f25af1b20">

**II. On Create Cluster Window, Fill in details > Once done, Click Create**
1. Fill in Cluster Name
2. Select AWS Fargate
3. Monitoring (Optional)

<img width="331" alt="image" src="https://github.com/user-attachments/assets/51724972-1bea-4204-ae2d-0f5cab6ea77d">

**III. Verify new cluster created**

<img width="806" alt="image" src="https://github.com/user-attachments/assets/cf0a3148-c236-4e64-8f83-8f5ca539cffa">

## 2. Create Task Definition
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

## 3. Create Task under newly create Cluster
**I. On AWS ECS Window, Click Cluster on left pane > Select the newly created Cluster**

<img width="362" alt="image" src="https://github.com/user-attachments/assets/e0ad14d0-285a-4834-b385-a73b9c2a102a">

**II. On Cluster Window, Click Task > Click Run New Task**

<img width="815" alt="image" src="https://github.com/user-attachments/assets/7a532ce2-1f94-4ae6-ab28-3ebf73ccfbbc">

**III. On Create New Task Window, Fill in details > Once done, Click  Create**
1. Select Launch Type
2. Under Deployment Configuration, Select Task > Select newly created task definition and version > Select desired number of task to launch
3. Select Task group if created

<img width="446" alt="image" src="https://github.com/user-attachments/assets/7ae3430b-c5d2-4f4f-8280-d7e9b6f64030">

<img width="415" alt="image" src="https://github.com/user-attachments/assets/c39073dc-3b44-4d82-b236-40ae7c707f07">

## 4. Verify Task is running

<img width="830" alt="image" src="https://github.com/user-attachments/assets/dbc744a9-b945-4dd3-a904-ffbcde83a85a">


## 5. Verify website is accessible
**I. To get Publick IP from Task create, click Task created**

<img width="823" alt="image" src="https://github.com/user-attachments/assets/d5bc4af2-a1bb-4b5a-a311-ba5ef61e494a">

**II. Get the Public IP address**

<img width="826" alt="image" src="https://github.com/user-attachments/assets/689b30d2-44e2-4c32-be79-03538be7b944">

**III. Verify Website is accessible**

<img width="232" alt="image" src="https://github.com/user-attachments/assets/35270aab-fece-4b92-86e6-2ab926482cf6">




