---
title: "Unleashing CodeBuild Magic: A Deep Dive into AWS Development | 30 Days of AWS — Day 13" 🚀💻"
datePublished: Thu Jan 18 2024 13:30:10 GMT+0000 (Coordinated Universal Time)
cuid: clsbgpf9m000t08jwfvgm4h6u
slug: unleashing-codebuild-magic-a-deep-dive-into-aws-development-30-days-of-aws-day-13-9b1793bfc00e
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290537660/fcc60cca-fc6b-4d30-b35b-43a66e11ce4a.png

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290506061/88823f60-7083-4731-98a7-37f7ade1224c.png)

### Introduction:

🚀 Welcome to Day 13 of our exhilarating 30 Days of AWS series! 🌐 Today, we’re strapping in for a deep dive into the heart of AWS development — the CodeBuild service. 🛠️ As we continue our journey through the cloud, we’ll unravel the mysteries behind this powerful tool and guide you on harnessing its potential. So, grab your virtual hard hats and join us on this exciting exploration of AWS CodeBuild! 💻✨

### What is Code Build?

AWS CodeBuild is a fully managed build service that compiles source code, runs tests, and produces software packages that are ready to deploy. With CodeBuild, you don’t need to worry about provisioning and managing your own build infrastructure. You simply provide your build project’s source code and build settings, and CodeBuild handles the rest.

For example, if you have a web application that you want to deploy, you can use CodeBuild to compile your source code, run unit tests, and produce a deployable package. You can also use CodeBuild to build Docker images, run static code analysis, and more. CodeBuild integrates with other AWS services like CodePipeline, so you can easily automate your entire software release process.

### What is the Buildspec file for Codebuild?

The Buildspec file is a configuration file used by AWS CodeBuild to define how to build and deploy your application or software project. It is written in YAML or JSON format and contains a series of build commands, environment variables, settings, and artefacts that CodeBuild will use during the build process.

Let’s Build the code step by step:

Step:1

*   Go to the AWS management Console and Navigate to the CodeBuild Service

*   You will see this type of Interface. Click on the Create Project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290507957/a2f6eb5a-25ff-4514-a976-7df07ac21853.png)

*   Write your project name here I give demo-build
*   Now the main part comes that what your source form your code will come and code build service builds that code.
*   Here I am selecting source as an AWS code Commit, if you do not know what is code commit then please visit my day 12 blog there I explained everything regarding the Code commit Service.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290509761/ee12732b-4197-4076-8695-b66eb9408d43.png)

*   After that select Repository for build code.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290511178/d173db07-ddab-4e45-895d-876648d752bd.png)

*   So now what is a Reference Tag: A reference tag is nothing but the identification of your code here I am selecting the branch tag.
*   In Environment Section we leave as it is

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290512463/341efbaf-3156-47fc-91f8-282d684d40f5.png)

*   Now In the operating System, we will select Ubuntu

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290513960/abdb9953-29fb-4c10-a0f0-7e152d5fa495.png)

*   Runtime as a standard and Image we were selecting Latest and service role as the New service role.
*   Now the main part comes in the picture:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290515513/28433b85-6364-40c7-9403-d51df027b0de.png)

*   Already we have discussed what is buildspec file.
*   So we will add the buildspec file in our code commit repo
*   Now in our repository, there are two files one is index.html and the second is buildspec.yml file

**index.html**

<html\>  
  <head\>  
    <title\>My Website</title\>  
  </head\>  
  <body\>  
    <h1\>Welcome to my website</h1\>  
    <p\>This is a simple website hosted on AWS CodeCommit.</p\>  
  </body\>  
</html\>

**buildspec.yml**

version: 0.2  
  
phases:  
  install:  
    commands:  
      \- echo Installing NGINX \- echo apt-get install NGINX  
      \- sudo apt-get update  
      \- sudo apt-get install nginx \-y  
   build:  
    commands:  
      \- echo Build started on date\`  
      \- cp index.html /var/www/html  
  post\_build:  
    commands:  
      \- echo Configuring NGINX  
artifacts:  
  files:  
    \-/var/www/html/index.html

*   Basically, we are hosting one index.html file on the nginx server.
*   If you want to learn how to write the buildspec file then you can visit to the AWS Code Build documentation
*   [https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html](https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html)
*   You can visit the above link.
*   For the demo purpose here we do not selecting artifacts to be generated

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290517030/6a2ffd50-544e-4a8e-a10c-ecaec16f46ce.png)

*   Now click on Create Build Project

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290518321/329a5e9b-6923-4169-a577-07af99671239.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290519549/d824e273-76bb-4e2f-8339-5a83da0a93a8.png)

*   Your Code Build Project Successfully Created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290520926/df9c6331-3c42-46da-ba14-005c54fc0b35.png)

*   Congrats on your first build success.
*   Now we will store the Artifacts:
*   For that Go to the code build and select your code build project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290522530/533fb57c-7049-4114-9973-f01d6c0bbf29.png)

*   Click On the edit option

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290524183/2c04c0dd-2468-4783-9925-87c18195071b.png)

*   And after that Click on Artifacts

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290525731/710f1693-960c-48a1-8023-b9c7974bf446.png)

*   Now we will select Artifact type as S3
*   Now we have to choose s3 bucket, but we do not created any bucket for code build let’s first create the Bucket first.
*   Go to the Management Console and Navigate to the S3 service.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290527527/4758dff6-913e-46b3-a73e-fb693e6d5f07.png)

*   Click on the Create Bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290528947/a99ce734-74e0-428f-bea7-4586e8f593ae.png)

*   Give the name to your bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290530364/293a0685-bbcb-47bd-b0b1-bd3982aedc4b.png)

*   Click on the Create Bucket.
*   Navigate to the project build, click on edit and select artefact. Provide all the details and create artifact.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290531870/9647baa2-047c-4a1f-ae8a-10dc4ae68ac2.png)

*   We successfully Upload the artefacts to the S3 bucket.
*   Let’s see
*   Go to the S3 bucket and check the bucket that you recently created for the artefacts.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290533324/1fc74923-d326-4ef6-9755-e465028159f5.png)

*   We successfully got the Artifacts.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290534788/facafd5c-ed50-446c-af2b-8758c19a6dc7.png)

*   Now click on the open button you will see your index file that is live now on the NGINX server.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290536240/440b849b-6e15-46d3-9c18-3e9a555fb224.png)

### That’s All from my side in today’s blog

If you like this blog then give one like and give one star

If you have any dought in this particular blog then let me know in the comment section.

#### GitHub Profile:

[**PurushotamSharma - Overview**  
*Purusing MCA from Charusat University. PurushotamSharma has 35 repositories available. Follow their code on GitHub.*github.com](https://github.com/PurushotamSharma "https://github.com/PurushotamSharma")[](https://github.com/PurushotamSharma)

#### Github Repo for this AWS Series:

[**GitHub - PurushotamSharma/30-Days-of-AWS-Adventure-**  
*Contribute to PurushotamSharma/30-Days-of-AWS-Adventure- development by creating an account on GitHub.*github.com](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure- "https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-")[](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)

Happy Learning :::