---
title: "Day 17 Task: Docker Project for DevOps Engineers."
datePublished: Wed Jun 21 2023 08:43:58 GMT+0000 (Coordinated Universal Time)
cuid: clj5gwnmu000509im5ip81xdu
slug: day-17-task-docker-project-for-devops-engineers
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1687337026120/b66d2662-4b6b-4014-b5dc-671fee90413d.png
tags: programming-blogs, docker, devops, dockerfile, trainwithshubham

---

Hello everyone, Welcome to the day 17 DevOps challenge and I hope you all are doing great.Let's discuss today's agenda:

### Agenda:

**What is Dockerfile?**

**One project using Dockerfile.**

Let's Start...

## What is Dockerfile?

Docker is a tool that makes it easy to run applications in containers. Containers are like small packages that hold everything an application needs to run. To create these containers, developers use something called a Dockerfile.

A Dockerfile is like a set of instructions for making a container. It tells Docker what base image to use, what commands to run, and what files to include. Let's understand by one example:

For example, if you were making a container for a website, the Dockerfile might tell Docker to use an official web server image, copy the files for your website into the container, and start the web server when the container starts.

### Task:

**Create a Dockerfile for a simple web application**

So we will create one Dockerfile of the nodejs application.

If you want that application visit my Github account or click on [Github](https://github.com/PurushotamSharma/node-todo-cicd).

So, first, we will clone our project into the instance of Ubuntu that we have launched **parallel** if you don't know how to launch any instance or server you may take the help of my previous blog where I give all the steps of launching a Server or Instance using EC2.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682313774716/3a805b9f-63be-4340-a9a0-57ba697b7c93.png align="center")

So we cloned our project using the command **git clone**

Now we made the Dockerfile using the command **vim Dockerfile before making the Dockerfile we want to transfer in our project directory using the command cd &lt;directory name&gt;**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682314120120/b8110cf3-bb8d-4d54-82cf-f1a1fe4e5758.png align="center")

Now we will write the code in the Dockerfile to create our image.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682314167272/e0aee4a7-49e2-4993-b56a-e5337ec2971d.png align="center")

**Here we use the following commands in the Dockerfile.**

⇝**FROM** The FORM command is used for importing the base image for our project and it must be executed on the top of the Docker file,

⇝**WORKDIR** The WORKDIR command is used to give our working directory to our project.

⇝**CPOY** The COPY command is used for copying the data from source to destination.

⇝**RUN** The Run command is used for images to run

⇝**Expose** The expose command is used for the expose the port.

⇝**CMD** The CMD command is used for run the Inside the container files.

Now we will build the image using the Dockerfile.

for that use the command below

```powershell
docker build . -t node-todo-app 
```

Now our image is ready, from image we will run the container for that use the below command

```powershell
docker run -d -p 8000:8000 node-todo-app:latest
```

Sorry We had not edit the inbounded rule so please add the inbounded rule on port 8000 then only your application will run

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683959371989/eb4f0d1a-d526-4564-bce9-ce2f29131146.png align="center")

Congrats🍾🍾🍾 Our web application run....

## Thanks for reading!!!

## Happy Learning Keep Growing!!!