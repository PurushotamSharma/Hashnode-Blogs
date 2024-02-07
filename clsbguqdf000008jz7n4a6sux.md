---
title: "Day 14: Unleashing the Deployment Dynamo — A Deep Dive into AWS CodeDeploy!🚀✨"
datePublished: Mon Jan 22 2024 07:37:00 GMT+0000 (Coordinated Universal Time)
cuid: clsbguqdf000008jz7n4a6sux
slug: day-14-unleashing-the-deployment-dynamo-a-deep-dive-into-aws-codedeploy-d96f5156ebad
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290785475/45b2f54f-3abc-40fb-8318-eaf1aaa94525.png

---

### Introduction:

Welcome to Day 14 of our exhilarating AWS 30 Days Challenge! Today, we’re embarking on a thrilling journey into the heart of AWS CodeDeploy, the deployment dynamo that transforms the way we launch applications into the cloud. 🌐💻

### What is CodeDeploy?

Code Deploy is a service from Amazon Web Services (AWS) that automates the deployment of code to servers. It makes it easy for developers to update their applications without having to manually manage the process.

Code Deploy works by creating a deployment group, which is a collection of servers that you want to deploy your code. You can then create a deployment configuration, which specifies how you want to deploy your code. For example, you can choose to deploy your code to all servers in the deployment group at once, or you can deploy it to a subset of servers and then gradually roll it out to the rest of the group.

Code Deploy also provides several features that make it easier to manage your deployments. For example, you can use Code Deploy to track the progress of your deployments, and you can roll back to a previous version of your code if there is a problem.

Overall, Code Deploy is a powerful tool that can help developers deploy their code more easily and efficiently.

In very simple Word code deploy is a service to deploy your code to the Servers.

### What is appspec.yaml file?

The Application Specification file (AppSpec file) is a YAML or JSON formatted file used by the code deploy service to manage deployment.

Later in this blog, we will discuss how to create the AppSpec.yaml file.

Before Jumping to the step-by-step guide let’s first discuss the Code Deploy Components:

1.  **Application:** An *application* is a name that uniquely identifies the application you want to deploy. CodeDeploy uses this name, which functions as a container, to ensure the correct combination of revision, deployment configuration, and deployment group are referenced during a deployment.
2.  **Compute Platform:** A *computing platform* is a platform on which CodeDeploy deploys an application. There are three computing platforms:

*   **EC2/On-Premises**: Describes instances of physical servers that can be Amazon EC2 cloud instances, on-premises servers, or both. Applications created using the EC2/On-Premises compute platform can be composed of executable files, configuration files, images, and more.
*   **AWS Lambda**: Used to deploy applications that consist of an updated version of a Lambda function. AWS Lambda manages the Lambda function in a serverless computing environment made up of a high-availability computing structure. All administration of the compute resources is performed by AWS Lambda
*   **Amazon ECS**: Used to deploy an Amazon ECS containerized application as a task set. CodeDeploy performs a blue/green deployment by installing an updated version of the application as a new replacement task set. CodeDeploy reroutes production traffic from the original application task set to the replacement task set. The original task set is terminated after a successful deployment.

3. **Deployment Configuration:** A *deployment configuration* is a set of deployment rules and deployment success and failure conditions used by CodeDeploy during a deployment. If your deployment uses the EC2/On-Premises compute platform, you can specify the minimum number of healthy instances for the deployment. If your deployment uses the AWS Lambda or the Amazon ECS compute platform, you can specify how traffic is routed to your updated Lambda function or ECS task set.

4\. **Deployment type:** A *deployment type* is a method used to make the latest application revision available on instances in a deployment group. There are two deployment types:

*   **In-place deployment**: The application on each instance in the deployment group is stopped, the latest application revision is installed, and the new version of the application is started and validated. You can use a load balancer so that each instance is deregistered during its deployment and then restored to service after the deployment is complete. Only deployments that use the EC2/On-Premises compute platform can use in-place deployments.
*   **Blue/green deployment**: The behaviour of your deployment depends on which compute platform you use

5. **Revision:** A revision is a version of your application.

6\. **Service Role :**

A *service role* is an IAM role that grants permissions to an AWS service so it can access AWS resources. The policies you attach to the service role determine which AWS resources the service can access and the actions it can perform with those resources. For CodeDeploy, a service role is used for the following:

*   To read either the tags applied to the instances or the Amazon EC2 Auto Scaling group names associated with the instances. This enables CodeDeploy to identify instances to which it can deploy applications.
*   To perform operations on instances, Amazon EC2 Auto Scaling groups, and Elastic Load Balancing load balancers.
*   Publish information to Amazon SNS topics so that notifications can be sent when specified deployment or instance events occur.
*   To retrieve information about CloudWatch alarms to set up alarm monitoring for deployments.

#### Step by Step guide for Deploying your code using AWS Service Code Deploy

### \- Deploy index.html file on EC2 machine using nginx..??

As we have seen in previous days blog day 12 and day 13.

We launched and configured some tasks of CodeCommit, CodeBuild, Builspec file and index.html so please refer to day 12 and day 13 for better understanding. Here is the link for Day 12 and Day 13.

Day:12 [**🚀 Day 12: AWS CodeCommit — Version Control in the Cloud**](https://medium.com/@purushotamsharma/day-12-aws-codecommit-version-control-in-the-cloud-6855351c2952?source=your_stories_page-------------------------------------)

Day:13 [**Unleashing CodeBuild Magic: A Deep Dive into AWS Development | 30 Days of AWS — Day 13" 🚀💻**](https://medium.com/@purushotamsharma/unleashing-codebuild-magic-a-deep-dive-into-aws-development-30-days-of-aws-day-13-9b1793bfc00e?source=your_stories_page-------------------------------------)

*   Create an Instance or Restart previously created in AWS.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290745103/0b49aa6c-562b-43ae-9491-664ceba48ee8.png)

*   We Build the code in the AWS CodeBuild section in the management section and the code is committed, Built and stored in the S3 bucket.
*   For today's deployment, we have to edit artifact configuration of the project as follows.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290747021/2111439d-0bf2-4a41-b18e-29a685c804ca.png)

*   Go to the Code Build and select your build project and click on the Edit button and select the Artifacts.
*   Select Artifacts packaging as zip and click on the update artifacts.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290748892/3fe8380e-72de-4b64-9926-066cd43be1f5.png)

*   Now let’s Navigate to the AWS code deploy
*   You will see this type of interface click on the Create Application.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290750745/c77a8afa-712e-4bf7-a8d7-a14915feaf99.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290752351/29df7740-aa9f-426e-8768-05638540b01f.png)

*   First, write the Application Name then select the EC2/On-premises and click on the Create application.
*   The application is created now. Now create a deployment group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290754316/e15011a2-4e45-4434-b289-0f57bfb07f71.png)

*   Before that, we need to give access to deployment to access the AWS resource for which we need to create a role in IAM. Provide all the necessary access as mentioned below.
*   Provide or attach these all policies

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290755911/2c6feb12-8959-4cf6-8713-b833fe96b287.png)

*   Now click on the create role
*   Go to the role and select that role you recently created
*   Now click on the trust policy
*   Now add this one.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290757407/38507e42-af83-4675-a5a9-047128631b08.png)

*   Now, Create a deployment group. Provide the deployment group name, and service role and enter the ARN id from the above role.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290759303/723f3d9d-4233-448a-bc86-e8d55e2385dc.png)

*   Deployment type select as In place

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290760987/ec88ba5c-a59d-4585-92ec-6c1d7410a35b.png)

*   In the environment configuration provide details regarding your ec2 instance

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290762840/5278ad02-3d41-43bd-bf20-5c2a7bd0d1a5.png)

*   In the Agent configuration select never and in the Deployment setting code deploy all at once

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290764531/7702e504-dc2d-4e50-b3f1-943f6297cb62.png)

*   Now click on the create deployment group.
*   Our deployment group was successfully created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290766237/0ca0552c-af81-4be8-8333-7fa2dc97a318.png)

*   We need to install the CodeDeploy agent on the server for which we need to write a script file with all the dependencies.

#!/bin/bash   
  
\# This script installs the CodeDeploy agent and its prerequisites on Ubuntu 22.04.   
  
\# Update package list  
sudo apt-get update   
  
\# Install Ruby and its dependencies  
sudo apt-get install ruby-full ruby-webrick wget -y   
  
\# Change to temporary directory  
cd /tmp   
  
\# Download the CodeDeploy agent package  
wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/releases/codedeploy-agent\_1.3.2-1902\_all.deb   
  
\# Create a directory to extract the package contents  
mkdir codedeploy-agent\_1.3.2-1902\_ubuntu22   
  
\# Extract the package contents  
dpkg-deb -R codedeploy-agent\_1.3.2-1902\_all.deb codedeploy-agent\_1.3.2-1902\_ubuntu22   
  
\# Update the package dependencies to use Ruby 3.0  
sed 's/Depends:.\*/Depends:ruby3.0/' -i ./codedeploy-agent\_1.3.2-1902\_ubuntu22/DEBIAN/control   
  
\# Repackage the updated package  
dpkg-deb -b codedeploy-agent\_1.3.2-1902\_ubuntu22/   
  
\# Install the updated package  
sudo dpkg -i codedeploy-agent\_1.3.2-1902\_ubuntu22.deb   
  
\# List all systemd units that contain "codedeploy" in their name  
systemctl list-units --type\=service | grep codedeploy   
  
\# Check the status of the CodeDeploy agent service  
sudo service codedeploy-agent status

*   Create install.sh, file and execute the shell script.
*   Our code deploy agent is running

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290768166/5cbba198-27d5-4481-b23a-419fff03826a.png)

*   Now we will add the appspec.yaml file to the repository and completed the deployment.
*   The app Spec file is required to create a bridge between the AWS CodeDeploy and the EC2 instance. Create the yaml file.
*   appspec. yaml

version: 0.0  
os: linux  
files:  
  \- source: /  
    destination: /var/www/html  
hooks:  
  AfterInstall:  
    \- location: scripts/install\_nginx.sh  
      timeout: 300  
      runas: root  
  ApplicationStart:  
    \- location: scripts/start\_nginx.sh  
      timeout: 300  
      runas: root

*   Create the dependency files as well for installing and starting nginx on the server.
*   install\_nginx.sh

#!/bin/bash  
  
sudo apt-get update && sudo apt-get install -y nginx

*   start\_nginx.sh

#!/bin/bash  
  
sudo systemctl start nginx  
sudo systemctl enable nginx

*   Make sure to change the buildspec.yaml file so that the CodeBuild will build the appspec.yml file and transfer the artifact to S3 bucket.

version: 0.2  
  
phases:  
  install:  
    commands:  
      \- echo Installing NGINX \- echo apt-get install NGINX  
      \- sudo apt-get update  
      \- sudo apt-get install nginx \-y  
  build:  
    commands:  
      \- echo Build started on date  
      \- cp index.html /var/www/html  
  post\_build:  
    commands:  
      \- echo Configuring NGINX  
artifacts:  
    files:  
      \- "\*\*/\*"

Here is all required files index.html, buildspec.yaml, appspec.yaml, install\_nginx.shand start\_nginx.sh.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290769732/11933ea1-8715-4877-a906-4751d1159925.png)

*   Now build the project.
*   Go to the AWS Code build and select Start build

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290771257/4427e28d-1eec-4857-9688-86fe151207e8.png)

*   Our build part all are successes

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290773167/b3d67d7c-438b-46f7-9ae9-8734303f0d5b.png)

*   Now create a deployment in the deployment group that we made previously.
*   But before that, we have to Create a role for giving access to EC2 instances with all the necessary permission policies

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290774929/13360d68-151f-424b-8e2e-23cf2a0e7660.png)

*   Now, navigate to the instance and modify the IAM role. Select the IAM role created above.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290776363/bfe60648-7b9e-49c5-ba78-4f32c2b592e5.png)

*   Now create a deployment in the deployment group that we made previously.
*   Click on the Create deployment

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290778404/0f6c5212-30c5-48c3-98bb-6030300dbcb4.png)

*   Revision type select as S3 and provide s3 uri and revision file type as .zip

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290779796/7cd7e886-43ff-4bc8-8d41-604b52bfa58e.png)

*   Now click on the Create deployment

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290781682/d360791c-b2fd-4cf1-a07a-b945be115493.png)

*   All the steps were successfully succeeded.
*   Congrats on your deployment.
*   Now check you instance id and access the web page using Public IP.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290783834/c4016a38-1467-4ba3-b486-9121654acb5c.png)

*   Finally we completed the service of AWS (code Deploy)

If you did not understand anything then write in the comment section.

My GitHub Profile:

[**PurushotamSharma - Overview**  
*Purusing MCA from Charusat University. PurushotamSharma has 39 repositories available. Follow their code on GitHub.*github.com](https://github.com/PurushotamSharma "https://github.com/PurushotamSharma")[](https://github.com/PurushotamSharma)

Github Repo for this Series:

[**GitHub - PurushotamSharma/30-Days-of-AWS-Adventure-**  
*Contribute to PurushotamSharma/30-Days-of-AWS-Adventure- development by creating an account on GitHub.*github.com](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure- "https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-")[](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)

Happy Learning:::

Stay tuned for the 15::