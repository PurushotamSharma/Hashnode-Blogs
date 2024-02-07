---
title: "🚀 Navigating the Cloud: Day 10 of 30 Days of AWS Series — Mastering the AWS CLI 🌐💻"
datePublished: Tue Jan 16 2024 06:32:41 GMT+0000 (Coordinated Universal Time)
cuid: clsbgmb11000508l5a3ir6xj1
slug: navigating-the-cloud-day-10-of-30-days-of-aws-series-mastering-the-aws-cli-280746c1ff28
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290392667/c0d276d6-11f8-4267-9145-53be0df08f5f.png

---

### Introduction:

Greetings, cloud enthusiasts! 🌟 Welcome back to our 30 Days of AWS Series, where we embark on a comprehensive journey through the vast landscape of Amazon Web Services. On this ninth day, we’re diving into a crucial aspect of AWS that empowers users with command-line prowess — the AWS Command Line Interface (CLI). 💡

As we continue our exploration of AWS services and tools, the AWS CLI emerges as a key player, providing a streamlined and efficient way to interact with your cloud resources. 🛠️ Whether you’re a seasoned cloud professional or just starting your AWS adventure, understanding the ins and outs of the AWS CLI is essential for mastering the art of cloud management.

In today’s instalment, we’ll unravel the layers of AWS CLI, discovering its capabilities, syntax, and real-world applications. 💬 Buckle up as we navigate the command line, unleashing the power to control AWS resources with precision and ease. Let’s dive into the world of AWS CLI and uncover the command-line magic that awaits! 🎩✨

Are you ready to elevate your AWS game? Let’s embark on Day 10 and unravel the mysteries of the AWS CLI together! 🚀🔍

### What is AWS CLI?

The AWS Command Line Interface (AWS CLI) is an open-source tool from Amazon Web Service(AWS). You can use it to interact with AWS services using commands in your command shell.

**Prerequisite:**

An AWS Account

#### How to install and Configure AWS CLI

*   Go to the official website of AWS and install from there, [Click here to Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
*   Open the MSI installer file and configure it according to you and go to the CMD and check that AWS CLI is installed or not by using the command

aws \--version

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290389333/f07a26f2-4e72-4dc9-b8da-f6bb8b2fee12.png)

You will see this type of interface after the installation of AWS CLI.

After installing the AWS CLI you want to configure the AWS CLI.

For that write the command

aws configure

Before executing this command you need the Access Key and the Secret Key for to configure your CLI with your AWS account.

For that we first create the IAM role from there we will get the access key and secret key for the CLI configuration.

Let’s Create an IAM user with the Administration Access Policy.

*   Go to the AWS Management Console and Search for the IAM.
*   After that, click on the Users create the User and give the Administration Permission (If you want to know how to create the User then Check out my day 02 blog on IAM)
*   When you create you find the Access key and Secret key.
*   Now go to your CMD and run the command aws configure
*   Now paste the Access key ID and the secret key ID.
*   That’s all congrats on configuring your AWS CLI with your AWS account.
*   Now we will interact with our AWS account using CLI.
*   If you did not understand anything then comment I will reply to you as soon as possible.

Let’s GO

If you want to list down all your AWS S3 buckets then use this command

aws s3 ls

You will see this type of interface.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290390695/1a3fc4a5-a000-40e4-b1cd-bc237304b2fc.png)

If you want to launch EC2 instance using the CLI then

aws ec2 run-instances \--image-id ami-0abcdef1234567890 \--instance-type t2.micro \--key-name MyKeyPair

Here replace xxxxxxx with the Image id

For today we have completed the What is CLI and how to install and How it works and how to configure. If you want to dive deep in this then check out the official Documentation:

AWS CLI:[https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)

### My Github Profile: https://github.com/PurushotamSharma

### My 30 days AWS Series Repo: [https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/tree/main/Day10](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/tree/main/Day10)

Thanks for reading my blog, and if you like it then click on the like button and share it with your friends. Stay tuned for Day 11.

Happy Learning::: —