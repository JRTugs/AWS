#  Uploading Docker Hub image to Elastic Container Registry (ECR)

## Steps
1. Pull docker image from DockerHub
2. Create and ECR Repository
3. Push docker image to ECR Repository
4. Verify Image in ECR Console

## Pre-requisite
1. AWS CLI installed
2. Docker installed
3. AWS IAM user with Access key to be used as credentials to connect to AWS Cloud

## 1. Pull docker image from DockerHub
**I. Pull image from Docker Hub**
```bash
docker pull jodo0131/helloworld
```

<img width="326" alt="image" src="https://github.com/user-attachments/assets/ad515f97-027a-4d07-ab35-4c1bcdac40da">

**II. Verify Docker images**
```bash
docker images -a
```

<img width="344" alt="image" src="https://github.com/user-attachments/assets/ce7f844d-9565-475f-b184-e918b7d21622">

## 2. Create and ECR Repository
**On AWS Console**
1. Search ECR in the search field
   
<img width="307" alt="image" src="https://github.com/user-attachments/assets/2b1b63af-83cf-4898-930b-fed3e2ec9dbe">

2. Click Repositories under Public Registry > Click Create Repository

<img width="914" alt="image" src="https://github.com/user-attachments/assets/1fc48697-29f4-49fc-8b6d-0421190355ae">

3. Under General Settings, Select Public > Fill in the Repository Name > Fill in other fields (Optional) > Once done, Click Create Repository

<img width="404" alt="image" src="https://github.com/user-attachments/assets/f4500730-fe55-40b6-a397-a0a1546dccc7">

<img width="367" alt="image" src="https://github.com/user-attachments/assets/b63700f3-6fb8-495f-afa4-92c74c7ef45e">

4. Verify Repository created

<img width="653" alt="image" src="https://github.com/user-attachments/assets/94cb5053-4296-4271-89ac-a789296454b6">

**On AWS CLI**
```bash
aws ecr-public create-repository --repository-name helloworldappp
```

<img width="350" alt="image" src="https://github.com/user-attachments/assets/74a72168-2692-48a5-b32c-3e117cc942ce">

Note: Need AWS credentials setup to connect to AWS Cloud
If run via AWS CLI no need for credential but if run on other servers then need AWS CLI credentials setup
1. Create IAM user
2. Assign proper group access
3. Once IAM user is created, create Access key token
4. run aws configure and key in the Access Key Token


## 3. Push docker image to ECR Repository
**I. On AWS ECR Console, Select repository > Click View push commands**

<img width="794" alt="image" src="https://github.com/user-attachments/assets/a64964a6-2547-4db2-b085-e1214be539b8">

**II. Copy command from "Retrieve an authentication token and authenticate your Docker client to your registry" and execute it in AWS CLI**

<img width="365" alt="image" src="https://github.com/user-attachments/assets/a09be3cb-f948-48b9-bf76-31b4f7746b90">
Command below is from Push command number #1
```bash
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/z7a5a7a0
```

<img width="570" alt="image" src="https://github.com/user-attachments/assets/a7d24d5c-f683-442b-9fbf-0bc1c7072c54">

**III. Tag docker image**
Command below is from Push command number #3
```bash
docker tag jodo0131/helloworld:latest public.ecr.aws/z7a5a7a0/helloworldapp:latest
```
Note: Need to use the docker images repository name as source image. To check run docker image

<img width="405" alt="image" src="https://github.com/user-attachments/assets/5611f467-2689-44d1-9c08-93b5484017e2">

**IV. Push Docker image to ECR Repository**
Command below is from Push command number #4
```bash
docker push public.ecr.aws/z7a5a7a0/helloworldapp:latest
```

<img width="451" alt="image" src="https://github.com/user-attachments/assets/49e04e08-bcd0-4a05-8878-c3fba6fc1612">

**V. Verify in AWS ECR Console**

<img width="718" alt="image" src="https://github.com/user-attachments/assets/b675f089-b417-4f54-8eb1-efa9b9020191">












