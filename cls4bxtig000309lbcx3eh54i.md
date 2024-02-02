---
title: "Day 20 of 30 Days of AWS Series: Dive into the World of AWS ECS 🚀"
datePublished: Fri Feb 02 2024 07:34:29 GMT+0000 (Coordinated Universal Time)
cuid: cls4bxtig000309lbcx3eh54i
slug: day-20-of-30-days-of-aws-series-dive-into-the-world-of-aws-ecs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706706445129/16554ba4-f2a4-4eb1-aa02-336c19b9f43a.png
tags: cloud, aws, devops, containers, trainwithshubham

---

## ✍Introduction:

Are you ready to explore the containerized world with Amazon ECS? In today's edition of our 30 Days of AWS series, we'll unravel the mysteries of ECS, its fundamentals, and why it might be your go-to container orchestration tool. 🛠️

## ✍**What is AWS ECS?**

Amazon Elastic Container Service (ECS) is a fully managed container orchestration service that allows you to run the Docker container at scale. It eliminates the need to manage your own container orchestration infrastructure and provides a highly scalable, reliable, and secure environment for deploying and managing your applications.

## ✍**Why Choose ECS Over Other Container Orchestration Tools?**

Before diving deep into ECS, let's compare it with some popular alternatives like Kubernetes and Docker Swarm.

* ### Comparison with Kubernetes:
    

Kubernetes is undoubtedly a powerful container orchestration tool with a vast ecosystem, but it comes with a steeper learning curve. ECS, on the other hand, offers a more straightforward setup and is tightly integrated with other AWS services, making it a preferred choice for AWS-centric environments.

* ### Comparison with Docker Swarm:
    

Docker Swarm is relatively easy to set up and is suitable for small to medium-scale deployments. However, as your application grows, ECS outshines Docker Swarm in terms of scalability, reliability, and seamless integration with AWS features like IAM roles and CloudWatch.

## ✍ECS Components:

To understand ECS better, let's explore its core components:

1. ***Clusters:*** A cluster is an essential part of ECS, offering a logical grouping of EC2 instances or Fargate tasks that allows you to run your containers with confidence and ease. It is the foundation of your deployment, ensuring that your services are deployed effectively and efficiently. With a cluster at your disposal, you can rest assured that your ECS environment is in good hands.
    
2. ***Task Definitions:*** Task Definitions define how your container should run, including the docker image to use, CPU and memory requirements, networking and more. It is like a blueprint for your containers.
    
3. ***Tasks:*** A task represents a single running instance of a task definition within a cluster. It could be a single container or multiple related containers that need to work together.
    
4. ***Services:*** Services help you to maintain a specified number of running tasks simultaneously ensuring high availability and load balancing for your applications.
    
    dc
    

## ✍Pros of Using AWS ECS

* **Fully Managed Service**: AWS handles the underlying infrastructure, making it easier for you to focus on deploying and managing applications.
    
* **Seamless Integration**: ECS seamlessly integrates with other AWS services like IAM, CloudWatch, Load Balancers, and more.
    
* **Scalability**: With support for Auto Scaling, ECS can automatically adjust the number of tasks based on demand.
    
* **Cost-Effective**: You pay only for the AWS resources you use, and you can take advantage of cost optimization features.
    

## ✍Cons of Using AWS ECS

* **AWS-Centric**: If you have a multi-cloud strategy or already invested heavily in another cloud provider, ECS's tight integration with AWS might be a limitation.
    
* **Learning Curve for Advanced Features**: While basic usage is easy, utilizing more advanced features might require a deeper understanding.
    
* **Limited Flexibility**: Although ECS can run non-Docker workloads with EC2 launch types, it is primarily optimized for Docker containers.
    

## ✍Installation and Configuration

Let's get our hands dirty and set up AWS ECS step-by-step.

* ### Prerequisites:
    
    \-- An AWS account with appropriate IAM permissions.
    
    \-- The AWS CLI and ECS CLI are installed on your local machine
    

### ✍Installing ECS CLI in Windows:

* Open Windows PowerShell and enter the following commands.
    
* ###### **<mark>Note</mark>**
    
    <mark>If you encounter permission issues, ensure that you have administrator access on Windows and you are running PowerShell as an administrator.</mark>
    

```plaintext
New-Item -Path 'C:\Program Files\Amazon\ECSCLI' -ItemType Directory
Invoke-WebRequest -OutFile 'C:\Program Files\Amazon\ECSCLI\ecs-cli.exe' https://amazon-ecs-cli.s3.amazonaws.com/ecs-cli-windows-amd64-latest.exe
```

* Apply to execute permissions to the binary.
    
* Edit the environment variables and add `C:\Program Files\Amazon\ECSCLI` to the `PATH` variable field, separated from existing entries by using a semicolon. For example:
    
    ```plaintext
    setx path "%path%;C:\Program Files\Amazon\ECSCLI"
    ```
    
    * Restart PowerShell so the changes go into effect.
        
    * Verify that the CLI is working properly.
        

```plaintext
ecs-cli --version
```

### ✍Setting Up ECS CLI:

ECS CLI is a command-line tool that simplifies the process of creating and managing ECS resources.

```plaintext
$ ecs-cli configure --region <region> --access-key <access-key> --secret-key <secret-key> --cluster <cluster-name>
```

### ✍Configuring AWS Credentials:

Ensure you have the necessary AWS credentials configured using `aws configure` the command.

In this demo, we will Create the Cluster using AWS Management Console.

### ✍Steps for creating the ECS Cluster:

* Go to the AWS Management Console and Navigate to the ECS Service
    
* Click on the Create Cluster
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706793346871/16ed1561-8da7-4abe-953e-d5bfd11324ba.png align="center")
    
    Name the Cluster
    
* In the Infrastructure select the AWS Fargate this is serverless
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706793467707/08ce25ce-ea05-4d2a-aa0d-ea1976a113b7.png align="center")
    
    Now Click on the Crate button.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706793700172/7790ee33-4c70-44a4-bed0-7d0ca058c833.png align="center")
    
    Our Cluster was created successfully.
    
* Now we will create one docker image and push it to the ECR(Elastic Container Registry).
    
* Dockerfile you will get in my Github repo of 30 Days of AWS Series.
    
* [Github repo](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/tree/main/Day20)
    
* Now We have the Dockerfile now we will build the dockerfile to create the docker image.
    
* use this command to build the image.
    
* ```plaintext
    docker build -t <name tag>:latest .
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706857104704/d812d4c0-5b64-4e05-af0d-b10bcbb6935d.png align="center")
    
    \-
    
* Our build is successful now we will push this image to the ECR.
    
* use this command to push
    
* ```plaintext
    docker push <name of your image> 
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706857512134/997ab631-714a-4ce2-ae81-8641bc6b7034.png align="center")
    
    \-
    
* Now we have our container image on ECR and Now we can use ECS.
    
* If you want to understand more about ECR then please check my previous blog where I explained ECR in detail.
    
* Now we need a task definition for ECS.
    
* Go to the AWS management console and navigate to the ECS Service there is the left panel you will see one option task Definition click on that.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706857721892/0bfb2ea9-0e46-4927-bfea-8487047c8210.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706857746298/5b519aa0-c39c-4b3a-9e00-3548f81233a5.png align="center")
    
    Now we will create the task definition.
    
* Click on the Create new task definition.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706858022097/c0e20b2c-f289-4401-b0fc-9d527e37227c.png align="center")
    
    Give the task definition name and select launch type as AWS Fargate.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706858057754/9796cfab-cc2f-4431-a086-d3df78520131.png align="center")
    
    Now we have to give the container name and repo URL and port
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706858390639/3fa1fe80-19da-4d08-aa7d-1deac762d011.png align="center")
    
    Now click on the Create button.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706858571294/a3e15f4e-f65b-40b4-b371-53c7fa9c9e3e.png align="center")
    
    After this when your task definition is active then click on Deploy&gt;run task.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706858650990/f1e4cd52-e6c7-413d-8203-2f4d2e95561a.png align="center")
    
    Now Click on the Create button.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706859011606/401fa695-bd14-4131-ae97-f9407b357755.png align="center")
    
    It will take some time to run.
    
* After successfully completing this project then delete it because AWS charge you for ECS service.
    

Thanks for reading this blog.

## ✍Conclusion

In conclusion, AWS ECS offers a robust and user-friendly platform for deploying and managing containerized applications. We covered the fundamentals of ECS, compared it with its alternatives, discussed its pros and cons, and walked through the installation, configuration, and deployment of a sample application.

Happy Learning:))