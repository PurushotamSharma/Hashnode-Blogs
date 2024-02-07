---
title: "Day 11: AWS CloudFormation Demystified! 🌐💻"
datePublished: Wed Jan 17 2024 12:18:04 GMT+0000 (Coordinated Universal Time)
cuid: clsbgm529000d09id4csbbjwq
slug: day-11-aws-cloudformation-demystified-42f0c281006f
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290384467/56d523db-759b-402d-8327-c1f8c61c6fc0.png

---

### Introduction:

🚀 Greetings, Cloud Enthusiasts! Day 11 of our 30-Day AWS Series is here, and today’s adventure takes us deep into the realm of AWS infrastructure with a focus on CloudFormation templates! 💻✨ Ready to unlock the secrets of Infrastructure as Code (IaC)? 🛠️

💡 Join us as we navigate through the CloudFormation landscape, unravelling the intricacies of template creation and deployment. 🌐🚧 Get set for a hands-on experience as we demystify the language that shapes your AWS environment! 📝🚀 Let’s sculpt cloud architectures with precision and finesse! Are you ready?

Let’s First Understand

### What is IaC?

IaC stands for Infrastructure as Code, which is a practice in software engineering that involves managing and provisioning computing infrastructure through machine-readable definition files such as JSON or YAML, rather than physical hardware configuration or interactive configuration tools. This approach allows for the automation of infrastructure deployment and management, enabling consistency, scalability, and efficiency in software development and IT operations. IaC is commonly used in DevOps and cloud computing environments to streamline the deployment and management of infrastructure resources.

### What is CloudFormation?

AWS CloudFormation is a service that helps you model and set up your AWS resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS.

You create a template that describes all the AWS resources that you want (like Amazon EC2 instances or Amazon RDS DB instances), and CloudFormation takes care of provisioning and configuring those resources for you. You don’t need to individually create and configure AWS resources and figure out what’s dependent on what; CloudFormation handles that.

#### What is the difference between CloudFormation and Command Line Interface?

CloudFormation is used for automating the infrastructure and automating the resources.

The Command Line Interface is used for quick actions.

#### Step by Step guide for Cloud Formation:

**Step: 01**

*   Go to the AWS management console
*   Search for the Cloud Formation and Click on it.
*   In the cloud formation, you want to create the stack first.
*   Let’s Create

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290375869/4fa5ca2d-bef2-476a-984a-05ce11d10dad.png)

*   Click on the Create Stack
*   Here you will see this type of interface

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290377872/4343e2ed-b08b-46c2-899e-bc98df4d218e.png)

*   Here you will get the three options for creating a stack

1.  **Template is Ready:**

A template is a JSON or YAML format file that contains configuration information about the AWS resources you want to include in the stack.

In the first option means that you have a template ready in your local or the s3 bucket or the GitHub.

**2\. Use a Sample Template:**

It means that you were creating a template first and you want to start with the basic example template.

**3\. Create a template in the Designer:**

It is a very interesting option to create the template, you just need to drag down the icons AWS automatically create the YAML or JSON format template file let’s see the 3 options:

Click on the third option(Create a template in the Designer)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290379680/e0d7616d-bcea-4e7c-afb8-189c584cb6d5.png)

You will see this type of interface after clicking on the third option.

Now you want to drag and drop.

Let's try to use the S3 bucket resource, now in the resource type see the S3 and drag down.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290381322/6f00e76e-5d0e-4194-b16a-40eafac7229e.png)

I only drag down the s3 bucket, it automatically writes the template file.

Resources:  
  Bucket:  
    Type: 'AWS::S3::Bucket'  
    Properties: {}

Now you want to add properties and that’s all.

Let’s Understand how to create a template file from scratch. without using this:

First, you want to know that the resources section is mandatory in the yaml file.

First, you need to see the documentation of the Cloud formation. AWS provided a template file for all the resources you just need to do changes according to your and use it.

Let’s try to create an S3 bucket using the Cloud Formation.

Here you find everything: [https://docs.aws.amazon.com/cloudformation/](https://docs.aws.amazon.com/cloudformation/)

Here you find all the resources template files:[https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)

Here is the Bucket template example

Resources:  
  Purushotam:  
    Type: 'AWS::S3::Bucket'  
    Properties: {}

Let’s Understand this example:

*   Here I created the very basic and simple s3 bucket using the template file. For the demo

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290382897/6852f6bc-02dd-4e83-a905-517850997d0e.png)

*   You can see that our template created the s3 bucket.
*   Try this from your side if you have any question then write down in the comment section.

### Github Profile:

[**PurushotamSharma - Overview**  
*Purusing MCA from Charusat University. PurushotamSharma has 35 repositories available. Follow their code on GitHub.*github.com](https://github.com/PurushotamSharma "https://github.com/PurushotamSharma")[](https://github.com/PurushotamSharma)

### Github Repo For 30 days of AWS Series:

[https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/edit/main/Day11/README.md](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/edit/main/Day12/README.md)

If you like this then don’t forget to give start.

Stay tuned for the Day 12…

Happy Learning