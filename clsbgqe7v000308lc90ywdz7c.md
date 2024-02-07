---
title: "Day 07: 🛡️ Building a Secure VPC with Public and Private Subnets in AWS Production Environment"
datePublished: Thu Jan 11 2024 14:08:30 GMT+0000 (Coordinated Universal Time)
cuid: clsbgqe7v000308lc90ywdz7c
slug: day-07-efb88f-building-a-secure-vpc-with-public-and-private-subnets-in-aws-production-environment-f327067eeb74
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290583282/0f714e92-d83b-4edb-b23c-f697a2c27be1.png

---

### Introduction:

🚀 Welcome to day 07 of the AWS 30-day AWS series! In today’s blog post, we’ll be diving into the implementation of a project called **VPC with public and private subnets in a production environment**. This project is a crucial step in understanding how to architect secure and scalable infrastructure on AWS.

🌐 We’ll explore the concept of Virtual Private Clouds (VPCs) and learn how to create a VPC with both public and private subnets. By the end of this post, you’ll have a solid understanding of how to design and configure network architectures that provide a secure environment for your applications while ensuring accessibility and scalability.

So, let’s roll up our sleeves and delve into the world of VPCs, subnets, and network architecture in AWS. Get ready to elevate your cloud infrastructure skills and take a step closer to becoming an AWS architect! 🛠️

#### 🌟 Introducing: “Day 06 of 30 Days AWS Series: Building a Resilient VPC for Production Environments” 🌟

In this blog, we’ll guide you through the creation of a robust VPC designed for production-level server deployment. Discover how to enhance resiliency by deploying servers across two Availability Zones (AZs) using Auto Scaling groups and Application Load Balancers. We’ll also show you how to bolster security by housing servers within private subnets, with requests routed through load balancers. Plus, learn how to enable internet connectivity for servers using NAT gateways strategically deployed across both AZs for maximum resiliency.

**Key Highlights:**

*   VPC featuring public and private subnets across two AZs
*   Each public subnet hosts a NAT gateway and a load balancer node
*   Servers in private subnets managed by Auto Scaling groups, receiving traffic from load balancers
*   Internet connectivity for servers facilitated by NAT gateways
*   Get ready to dive into the world of VPC architecture and deployment in AWS, and take your production environment to the next level!

So let’s see our Project Architecture:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290564098/12f1079a-6449-4fd7-a806-68ec07457cca.png)

Let’s build this by doing practical:

***Step:1***

First, we have to create one VPC for our Project :

*   Go to the AWS Management Console ➡️VPC➡️ Create VPC
*   In the Resource to create select the VPC and More
*   Give your name or tag to your VPC

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290565941/f376505e-2113-4c50-9cdc-e87aa8ef4966.png)

*   The interface for now looks like this, let’s jump to the next.
*   Number of AZ we need 2 according to our diagram
*   Number of public subnets:2
*   Number of Private subnets:2
*   NAT Gateway: We need 1 per AZ
*   Here we have not learned the S3 in our series so for this project we disable the VPC endpoints.
*   Now Click on the Create VPC.

***Step:02***

Now we have to create the Auto Scaling Group:

*   Go to the Management Console➡️ EC2➡️ In the Side navigation at last you can see the option Aws Auto Scaling Group➡️ Create Group
*   Name your Auto Scaling Group
*   For creating the Auto Scaling Group we need the template, let’s create the template first
*   Click on the Create a Launch Template
*   Now name your template
*   Write a Little description about your template:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290567756/de2712ac-f18a-4304-9a24-b40bac0ed138.png)

*   Now move forward, here you have to select the AMI(Amazon Machine Image) I am selecting the Ubuntu you can choose according to you.
*   We will be deploying the simple HTTP server so t2.micro ( free-tier) is also sufficient
*   Now, Select the Instance type as a t2.micro
*   Select the key pair
*   In the network Setting, create a new security group and name it according to you
*   In the VPC section select the VPC that you created above.
*   Edit the inbound rule
*   In this project, I want to deploy the application on port 8000 so I added port 8000 in the inbound rule, I want to SSH so I added port 22 as well as

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290569684/c34e6129-3a22-46f9-80de-8a7f49d16aeb.png)

*   You can according to your requirement.
*   Now click on the Create launch template.

***Step:03***

Come Back to the Auto Scaling Group

*   Name the Auto Scaling group and use the template that you create.
*   Now click on the next
*   In the load balancing we will be using the default one (No load Balancer)
*   And other things let be the default
*   Now click on Next
*   In the configure group size and scaling
*   The desired Capacity is equal to 2 and minimum capacity is 1 and the maximum is 4.
*   Now review and click to create
*   Now wait for a couple of seconds and congrats you successfully created the Auto Scaling Group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290571379/22cf91ca-db24-492e-962a-adbbf48e6a17.png)

*   Here you can see our both instances are created

Now the main part comes, without the public IP how do we access the Ec2 instances???

#### {Any Guess?, Yes then write in the comment section}

Now the Bastion Host comes into the picture.

#### What is Bastion Host or Jump Box?

A bastion host is like the guardian of your private network in the cloud! 🛡️ It’s a specially configured instance that acts as a secure gateway for accessing your private resources from outside the network. Just like a fortress with a single drawbridge, the bastion host provides a controlled entry point, allowing authorized users to securely connect to your private servers and databases. With its strong defences, it ensures that only trusted individuals can access your sensitive resources, adding an extra layer of protection to your cloud infrastructure. 🏰💻

***Step:04***

Here we will create a bastion server from that server we can access our private Ec2 instances.

Let’s Start:

*   AWS Management Console➡️ EC2➡️ Launch Instance
*   Name the server
*   Select the Image, Here I am selecting Ubuntu(free-tier)
*   The instance type is t2.micro
*   Select the key pair
*   In the Network Setting Click on the edit button and select the VPC that we created in Step 1
*   If the private ec2 instances and bastion host are in different VPC then we can not connect, so keep in mind whenever you want to create the bastion host for accessing the private instances make sure you are creating the bastion server in the same VPC.
*   Launch Instances.

For accessing our private instances using the Bastion host we need the pem file in the Bastion server so we need to copy the pem file that is stored in our local. So let’s do it

For copying the file

scp -i C:\\Users\\sharm\\Downloads\\Purushotam\_New\_Key.pem C:\\Users\\sharm\\Downloads\\Purushotam\_New\_Key.pem ubuntu@13.126.38.0:/home/ubuntu

Use the above code replace it with your path and copy that

After copying access to your bastion host see if you find your PEM file or not if not then re-copy that.

After successfully finding the pem file access your private server using the below command

ssh -i Purushotam\_New\_Key.pem ubuntu@10.0.139.97

Now create one index.html file that we will deploy

Now we will deploy the server using HTTP

python3 \-m http.server 8000

run this command on the private instance that you want to deploy.

***Step:05***

Last and the final Step attaching the Load balancers:

*   Go to the AWS Management Console ➡️ Search for the Load Balancer➡️ Click to Create Load balancer
*   Name your balancer
*   Select Scheme as an internet facing (default)
*   Ip address type is ipv4
*   In the Network Mapping select your VPC that we create in Step 01
*   Like this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290573105/6a509a01-f7e9-4662-bd8a-e50304d8fea2.png)

*   Select both AZs in the mapping and make sure you select the subnet that is in the public
*   If you select private then AWS gives you an error.
*   In the Security Group Select your VPC or Security
*   Now in the Listeners and routing you want to create a target group so let’s go create the target group:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290574682/2bd5b1c7-9a0a-4ac8-9548-4726b11ad6ee.png)

*   Provide the target group name
*   In the port allow 8000 because our application is deployed on the port 8000
*   Protocol is HTTP
*   IP address type IP4
*   Select the VPC that we created in step 01
*   Protocol version http1

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290576519/650e9e53-feac-45d4-a642-5535b2211bde.png)

*   Now click on the next button

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290578389/a0e1bf96-eccf-4f1f-bd69-2ccbd2852ba1.png)

*   Checkmark both instances click on the include in pending now and hit on the create target group.
*   It takes a couple of seconds
*   Now back to our load balancer section and select the target group you have created above
*   And now click on the Create

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290579942/91932c14-94db-40d8-a5ed-ec957c6e8ee1.png)

*   It takes a couple of seconds to provision.
*   Now go to the Instance in which you hosted or deployed your HTTP and in security ➡️ inbound rule and add the port 80
*   Wait for a couple of seconds and you can see your deploy HTTP server live.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290581560/adf0530a-0458-40dd-bbb6-d10a59e84312.png)

*   Congratulations you completed the most demanding project.

### Github Profile :

[**PurushotamSharma - Overview**  
*Purusing MCA from Charusat University. PurushotamSharma has 35 repositories available. Follow their code on GitHub.*github.com](https://github.com/PurushotamSharma "https://github.com/PurushotamSharma")[](https://github.com/PurushotamSharma)

### Github AWS Series Repo:

[**GitHub - PurushotamSharma/30-Days-of-AWS-Adventure-**  
*Contribute to PurushotamSharma/30-Days-of-AWS-Adventure- development by creating an account on GitHub.*github.com](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure- "https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-")[](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)

Thanks for reading…