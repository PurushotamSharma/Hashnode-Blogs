---
title: "Day 15: AWS CodePipeline Deep Dive 🚀"
datePublished: Mon Jan 22 2024 11:20:35 GMT+0000 (Coordinated Universal Time)
cuid: clsbgomvu000j09idd3g3esof
slug: day-15-aws-codepipeline-deep-dive-8cb6623028b3
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290501079/7f2d0486-045e-4aee-90fa-f51b22366984.png

---

### Introduction:

Hey, cloud enthusiasts! Welcome back to the adventure-packed journey of the “30 Days of AWS” series. 🌐💻 Today, we’re strapping in for a thrilling ride into the heart of modern software delivery — it’s Day 15, and we’re diving headfirst into the enchanting world of AWS CodePipeline! 🤖🛠️

Buckle up your virtual seatbelts because, in this instalment, we’re not just talking pipelines; we’re unleashing the magic of continuous delivery with AWS CodePipeline! 🌈✨ If you’ve ever wondered how the wizards of DevOps seamlessly weave code from development to deployment, stick around, because we’re about to unveil the secrets! 🧙‍♂️🚀

Whether you’re a seasoned cloud sorcerer or a curious coder on a quest for knowledge, this blog is your map to mastering CodePipeline sorcery. 🗺️🔍 Are you ready to automate, deploy, and conquer the challenges of modern software development? Then let’s embark on this exhilarating journey together! 🚀🔥

Grab your wands (or keyboards) and join us as we unravel the enchantment of AWS CodePipeline in today’s magical blog post! 📜💫 Let the continuous delivery adventure begin! 🌐🚀

### What is AWS Code Pipeline?

AWS CodePipeline is a continuous delivery service that enables you to model, visualize, and automate the steps required to release your software. With AWS CodePipeline, you model the full release process for building your code, deploying to pre-production environments, testing your application and releasing it to production. AWS CodePipeline then builds, tests, and deploys your application according to the defined workflow every time there is a code change. You can integrate partner tools and your own custom tools into any stage of the release process to form an end-to-end continuous delivery solution.

### Why should I use AWS CodePipeline?

By automating your build, test, and release processes, AWS CodePipeline enables you to increase the speed and quality of your software updates by running all new changes through a consistent set of quality checks.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290473058/05506668-007f-4ebe-a575-2702f024f887.png)

This is a workflow of our today’s blog.

Let’s Get started:

In our previous blog we had created the 4 steps:

*   AWS Code Commit
*   AWS Code Build
*   AWS Cloud Artifact
*   AWS Code Deploy

If you have not seen these blogs then please see these blogs for better understanding.

[**🚀 Day 12: AWS CodeCommit — Version Control in the Cloud**  
*Introduction:*purushotamsharma.medium.com](https://purushotamsharma.medium.com/day-12-aws-codecommit-version-control-in-the-cloud-6855351c2952 "https://purushotamsharma.medium.com/day-12-aws-codecommit-version-control-in-the-cloud-6855351c2952")[](https://purushotamsharma.medium.com/day-12-aws-codecommit-version-control-in-the-cloud-6855351c2952)

[**Unleashing CodeBuild Magic: A Deep Dive into AWS Development | 30 Days of AWS — Day 13" 🚀💻**  
*Introduction:*purushotamsharma.medium.com](https://purushotamsharma.medium.com/unleashing-codebuild-magic-a-deep-dive-into-aws-development-30-days-of-aws-day-13-9b1793bfc00e "https://purushotamsharma.medium.com/unleashing-codebuild-magic-a-deep-dive-into-aws-development-30-days-of-aws-day-13-9b1793bfc00e")[](https://purushotamsharma.medium.com/unleashing-codebuild-magic-a-deep-dive-into-aws-development-30-days-of-aws-day-13-9b1793bfc00e)

[**Day 14: Unleashing the Deployment Dynamo — A Deep Dive into AWS CodeDeploy!🚀✨**  
*Introduction:*purushotamsharma.medium.com](https://purushotamsharma.medium.com/day-14-unleashing-the-deployment-dynamo-a-deep-dive-into-aws-codedeploy-d96f5156ebad "https://purushotamsharma.medium.com/day-14-unleashing-the-deployment-dynamo-a-deep-dive-into-aws-codedeploy-d96f5156ebad")[](https://purushotamsharma.medium.com/day-14-unleashing-the-deployment-dynamo-a-deep-dive-into-aws-codedeploy-d96f5156ebad)

Today we will be creating the Piepline and automating this workflow.

Let’s go:

*   First of all, go to the AWS Management Console and navigate to the AWS Code pipeline service.
*   You will see this type of user interface:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290475636/65d997c4-b343-4fed-b13d-1e6c74f45db4.png)

*   Now click on the Create Pipeline.
*   Now write the pipeline name and after that select v2 as the pipeline type.
*   Select New Service role.
*   Now click on the next.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290477733/80be171f-ab0b-4b87-b3e2-2eea17824a16.png)

*   Now, add the source

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290479164/f222203c-b482-443b-8f5e-ff7b554dc042.png)

*   If you are following my blog then select AWS code commit
*   Now Write the repo name
*   Select Branch

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290480906/3cb7be03-85c1-4b3f-a2e9-9f3e53c70710.png)

*   Click on the next.
*   In the build provide select the AWS code build as a build provider.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290482656/f4170be3-8830-42fe-9e32-56b155d1848d.png)

*   Now select the Project name and select the single build as the build type.
*   Now select the deploy provider

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290484372/210d9721-412a-4cf6-af8c-fa4eb75da3eb.png)

Se

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290485924/f0686128-3f92-4ce8-b5bb-bf9143bed57c.png)

*   Now select your application name and deployment group.
*   On this is last but not least step review and click on the Create Pipeline.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290487199/c579ed19-31cd-4b86-80e7-026ced2b3f01.png)

*   Our Pipeline is successfully created, Congratulation everyone…

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290488473/474da175-9fee-46ba-be40-9bbe9fab8e3b.png)

*   Our source has successfully succeeded.
*   Build also created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290489864/0d9ddae7-4dd6-46b9-93cd-34fedb0fc9fe.png)

*   Congratulation our deploy process is also completed…

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290491311/f290b0bd-05f0-4008-9645-437878460112.png)

*   Now let's see this project by accessing the public IP.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290492841/d38a4fd7-52f7-4050-a4bb-9f05a1c8c075.png)

*   Successfully deploy the project using the ci cd pipeline.
*   Let’s check whether this pipeline is working or not
*   If we change the code then the pipeline automatically should trigger
*   Go to the AWS code commit and add a new file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290494534/1a5496b0-33c8-4ee5-b14d-0bcd3b762538.png)

*   Click on the Add file and click on the Create file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290496184/44d7d48f-5f22-43d8-bd59-c27df61fb70e.png)

*   Click on the commit changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290497804/70437c1e-d561-421f-84b0-efb107c815cf.png)

*   After clicking on the commit changes the pipeline automatically starts re-building.’

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290499231/b9a7b18f-193f-4aa7-8cc0-c05c8e8b8af4.png)

That’s all from my side in today’s blog.

If you like the blog then share it with your friends.

Happy Learning:))

### My Github Profile:

[**PurushotamSharma - Overview**  
*Purusing MCA from Charusat University. PurushotamSharma has 39 repositories available. Follow their code on GitHub.*github.com](https://github.com/PurushotamSharma "https://github.com/PurushotamSharma")[](https://github.com/PurushotamSharma)

### Github Repo for AWS series:

[**GitHub - PurushotamSharma/30-Days-of-AWS-Adventure-**  
*Contribute to PurushotamSharma/30-Days-of-AWS-Adventure- development by creating an account on GitHub.*github.com](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure- "https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-")[](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)

Stay tuned for day 16.