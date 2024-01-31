---
title: "Day 19: Dive into AWS ECR (Elastic Container Registry) 🚀"
datePublished: Wed Jan 31 2024 08:37:01 GMT+0000 (Coordinated Universal Time)
cuid: cls1jaj4n000509jyg4k02fid
slug: day-19-dive-into-aws-ecr-elastic-container-registry
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706521230686/e5a319af-713e-45b6-93ac-9692f2a2fa6d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1706690203538/57aeaae5-efee-48d5-a2a4-590c78954450.png
tags: cloud, aws, community, devops, trainwithshubham

---

### Introduction:

Welcome back to the 30 Days of AWS series! Today, we’re going to explore the fascinating world of AWS Elastic Container Registry (ECR). 🐳

### What is ECR(Elastic Container Registry)?

AWS ECR is a fully managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images. It seamlessly integrates with Amazon ECS (Elastic Container Service) and provides a secure, scalable, and reliable solution for container image storage.

### Key Features 🌟

1. **Secure & Private:**
    

* ECR offers encryption at rest, and images are stored in private repositories by default, ensuring the security of your container images.
    
* ECR allows you to create private container registries, ensuring that your images are accessible only to authorized users and services.
    

**2\. Integrated with IAM:**

* Leverage AWS Identity and Access Management (IAM) for fine-grained access control to your container images.
    
* ECR integrates smoothly with AWS services like ECS and EKS, simplifying the deployment process.
    

**3\. Scalable:**

* ECR is designed to scale with your containerized applications, ensuring high availability and low-latency image retrieval.
    
* As a managed service, ECR automatically scales to meet the demands of your container image storage.
    

**4\. Lifecycle Policies:**

* Easily manage image versions and reduce storage costs by defining lifecycle policies for your container images.
    
* Availability: ECR guarantees high availability, reducing the risk of image unavailability during critical times.
    

**5\. Availability:**

* ECR guarantees high availability, reducing the risk of image unavailability during critical times.
    

### Getting Started with ECR 🛠️

#### Creating an ECR Repository

1. Go to the AWS Management Console and navigate to the Amazon ECR service.
    

![](https://cdn-images-1.medium.com/max/1000/1*pH4kr9QP1Fd9Wxt2u96aBg.png align="left")

2\. Click on “Create repository” to create a new repository.

![](https://cdn-images-1.medium.com/max/1000/1*FufkqjaE01wkGcvR43X2qA.png align="left")

* Select the Visibility of your Repo, here i am creating for the demo so i am selecting as a private.
    

3\. Enter a unique name for your repository and click “Create repository.”

![](https://cdn-images-1.medium.com/max/1000/1*pDFy8kJ4pBZzdTLkKv4g-Q.png align="left")

#### Installing AWS CLI

To interact with ECR from your local machine, you’ll need to have the AWS Command Line Interface (CLI) installed. Follow the instructions in the [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html) to install it.

**Configuring AWS CLI**

After installing the AWS CLI, open a terminal and run the following command to configure your CLI with your AWS credentials:

```plaintext
aws configure
```

Enter your AWS Access Key ID, Secret Access Key, default region, and preferred output format when prompted.

### Pushing Docker Images to ECR

* I have one project of Todo in react for that project we create the docker image and push it to ECR.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706686006084/4a8ac97a-1f8f-4c33-ac58-5c2d338d43bb.png align="center")
    
    This is interface of my todo application.
    
* Here first we create the Dockerfile
    

```plaintext
# Use an official Node.js runtime as a base image
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the React app
RUN npm run build

# Expose port 3000
EXPOSE 3000

# Set the environment variable to production
ENV NODE_ENV=production

# Command to run the application
CMD ["npm", "start"]
```

* So this is our Dockerfile , now we will build this docker file.
    
    ```plaintext
    docker build -t <your-image-name> .
    ```
    

```plaintext
docker run -p 3000:3000 <your-image-name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706687179350/91907f6c-cac9-4560-b5f1-b665a47e2a91.png align="center")

Our Image is Creating from the Dockerfile.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706687384601/2def0ad0-f857-4269-acf1-5325d499455e.png align="center")

Our Image is created successfully.

Now we create the repo in the ECR using the AWS CLI

```plaintext
aws ecr create-repository --repository-name <repo_name> --region <region_name>
```

Use this command to create the repo to your ECR from local

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706687645756/036764d9-50c0-4cd7-b806-0ec4de449ac8.png align="center")

So here we created the repo now we will push the image

**Remember:**

1. You won't see any images under repository. Because we haven't pushed any image yet.
    
2. Note down `URI` of your repo. We'll have to use it soon.
    

Every piece has been individually created so far. It's time to join each and every piece and complete the puzzle.

For Docker to push the image to ECR, first we have to authenticate our Docker credentials with AWS. We use the `get-login-password` command that retrieves and displays an authentication token using the *GetAuthorizationToken* API that we can use to authenticate to an Amazon ECR registry.

```plaintext
aws ecr get-login-password --region <region_name>
```

Use the same `region_name` that you used while creating a repo. Store the encrypted token somewhere for a moment.

Take a deep breath now. We need two things I told you to save somewhere. The first is the token I just mentioned and second is the repository URI from the previous step.

Did you get that? Lessgooo!

```plaintext
aws ecr --region <region> | docker login -u AWS -p <encrypted_token> <repo_uri>
```

Needless to say, put the same region where your repository exists.

We are querying the ECR API provided by AWS CLI. Later we are pipelining Docker login.

* `-u AWS`: Default user provided by AWS.
    
* `-p <encrypted_token>`: Password we retrieved in the last step.
    
* `repo_uri`: URI of our repository.
    

If the login is successful, **Login Succeeded** will be shown in the terminal.

### **How to Tag a Local Docker Image**

This command tags a local Docker image with the ECR Repo.

```plaintext
docker tag <source_image_tag> <target_ecr_repo_uri>
```

* `source_image_tag`: The name you gave for the `docker build` command. If you are following along, it is `image name`
    
* `target_ecr_repo_uri`: ECR Repository URI.
    

### **How to Push the Docker Image to ECR**

The final step – the last piece of the puzzle!

The following command pushes the local Docker file to the remote ECR repository. Depending on the image size, it will take some time to finish.

```bash
docker push <ecr-repo-uri>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706688483189/826812db-d904-4129-9ef8-761582eed39e.png align="center")

Hurray! We have made it 🎉

Let's alos check on AWS as well

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706688518328/8fa3edda-2434-41ba-b6af-d322c887d90a.png align="center")

You can see the uploaded image in the AWS console. Go to ECR, click on repositories, and open ECR repo we uploaded a few minutes back. Copy `Image URI` if you want to use it further.

## **Wrapping Up**

In this article, we covered how to deploy a Docker image on AWS ECS. You can use this Docker container resting inside ECR to host your application on the server. It could be AWS EC2 or anything else.

Docker and AWS are widely used to develop large scale applications. Having an idea how these things work together should help you build large scale applications in the future.

Having said that, I hope this article has helped you in your work, studies or learnings. If it did, you might also find my other articles helpful.

## Github Profile

[https://github.com/PurushotamSharma](https://github.com/PurushotamSharma)

## Github repo for AWS Series

[https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)