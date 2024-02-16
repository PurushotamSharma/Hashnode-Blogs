---
title: "Day 24 of 30 Days of AWS: Mastering AWS Config Service! 🚀"
seoTitle: "AWS Config"
datePublished: Fri Feb 16 2024 18:51:22 GMT+0000 (Coordinated Universal Time)
cuid: clsp0a85h000609jmdxhydeaj
slug: day-24-of-30-days-of-aws-mastering-aws-config-service
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708109414276/18117a56-8574-475a-b3dc-71943cc7417e.png
tags: cloud, aws, technology, community, devops, technical-writing-1, awscommunity, trainwithshubham

---

## ✍️ Introduction:

Hey there, fellow cloud enthusiasts! Welcome back to our exciting journey through the world of AWS. Today, on day 24 of our 30 Days of AWS series, we're diving deep into the AWS Config Service, a vital tool for maintaining control and visibility over your AWS environment. 🛡️

### ✍️Understanding AWS Config Service:

AWS Config Service empowers you to monitor, audit, and assess your AWS resource configurations with ease. Let's break down its key components and functionalities:

### ➤ Configuration Recorder:

The configuration recorder is the backbone of AWS Config. It continuously tracks changes to your AWS resources and records their configurations. You can specify which AWS resources you want to monitor, ensuring you have visibility into the aspects of your infrastructure that matter most to you.

### ➤ Rules:

AWS Config allows you to define rules that evaluate your resource configurations against desired configurations. You can choose from a wide range of predefined rules covering best practices and compliance standards or create custom rules tailored to your specific requirements. These rules help you ensure that your AWS resources adhere to organizational policies, security standards, and regulatory requirements.

### ➤ Compliance Dashboard:

The compliance dashboard provides a centralized view of your AWS resources' compliance status. It highlights any resources that are non-compliant with your defined rules, making it easy for you to identify and address configuration drifts or violations promptly.

### ➤ Delivery Channel:

The delivery channel specifies where AWS Config sends configuration snapshots and change notifications. You can configure it to deliver configuration history snapshots to an Amazon S3 bucket, send notifications via Amazon SNS topics, or stream configuration changes to an AWS Config stream for real-time processing.

## ✍️Let's Get Started:

Now that we have a basic understanding of AWS Config Service, let's walk through the steps to set it up and perform a hands-on demo:

#### 1\. Enable AWS Config:

* Head to the AWS Management Console.
    
* Navigate to the AWS Config service.
    
* Click on "Get Started Now" or "Set up AWS Config."
    
* Follow the prompts to enable AWS Config.
    

#### 2\. Configuration Recorder Setup:

* Configure a recorder to capture configurations.
    
* Select the AWS resources you want to monitor.
    
* Specify the recording frequency and AWS Key Management Service (KMS) key if encryption is desired.
    

#### 3\. Rule Configuration:

* Set up rules to evaluate resource configurations.
    
* Choose from predefined rules or create custom ones.
    
* Define the scope of the rules and configure their triggers and remediation actions as needed.
    

#### 4\. Delivery Channel Configuration:

* Set up a delivery channel to define where AWS Config sends configuration snapshots and change notifications.
    
* Choose options like Amazon S3, Amazon SNS, or AWS Config streams for delivery.
    
* Configure delivery frequency and encryption settings if required.
    

### ✍️Hands-on Demo: Tracking Resource Changes

Let's put our knowledge into action with a practical demo:

**Scenario:**

Alright, imagine this: We're about to embark on a journey where we'll set up two instances and keep a close eye on them, ensuring they're in line with our compliance standards. But wait, what exactly do we mean by compliant and non-compliant? Let me demystify that for you! 🕵️‍♂️

Picture this: If our instance's Monitoring Option is toggled on, it's a thumbs-up from Compliance Central! That means it's compliant, meeting all our monitoring requirements. 🎉 However, if that option is left unchecked, it's a red flag, signaling non-compliance. 😬

But here's where it gets exciting: We're not babysitting these instances manually. Oh no! We've got a Lambda function up our sleeves that's going to handle all of this for us, automatically sorting instances into their rightful categories. How cool is that? 😎

So, are you ready for this adventure? Let's dive in and make compliance monitoring a breeze! 🌟

### ➦ Launch an EC2 Instance:

➜ Navigate to the EC2 Dashboard.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708087263132/7fd821aa-c689-4dff-ae14-f8def93b1a9e.png align="center")

➜Launch a new instance with your preferred settings.

➜ I am launching the 2 Ubuntu Flavour EC2 Instance.

➜ Click on the Launch Instance

➜ Now fill in the name and Select the AMI according to you.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708086313492/99363eb0-04de-4f32-9883-c68137451929.png align="left")

➜ Scroll down select the key pair and hit on the launch instance.

➜ Now we have 2 instance names Config-Service-1 and Config-Service-2

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708086595667/f8c1762b-6566-4f28-bc87-9fead8fad22a.png align="left")

### ➦ Creating the Lambda function:

➜ Here's the plan: We're going to craft a Lambda function that's like our very own detective, always on the lookout for any changes in our EC2 instances. 🕵️‍♀️ Whenever an instance is created, deleted, modified, or updated, *bam!* our Lambda function will spring into action, triggered automatically like clockwork.

➜ But wait, there's more! 🚨 We're not just stopping at detecting changes; we're taking it up a notch with the help of AWS Config Service. This powerful service will provide us with all the juicy details we need to determine whether each instance is compliant or non-compliant with our standards.

➜ Imagine it: Our Lambda detective receives a signal, swoops in to investigate, and with the magic of AWS Config, it swiftly categorizes the instance as either compliant 🌟 or non-compliant 😬. All of this happening seamlessly in the background, keeping our infrastructure in check without us lifting a finger!

➜ **Here I am giving the Lambda function code:**

```plaintext
import boto3
import json

def lambda_handler(event, context):

    # Get the specific EC2 instance.
    ec2_client = boto3.client('ec2')
    
    # Assume compliant by default
    compliance_status = "COMPLIANT"  
    
    # Extract the configuration item from the invokingEvent
    config = json.loads(event['invokingEvent'])
    
    configuration_item = config["configurationItem"]
    
    # Extract the instanceId
    instance_id = configuration_item['configuration']['instanceId']
    
    # Get complete Instance details
    instance = ec2_client.describe_instances(InstanceIds=[instance_id])['Reservations'][0]['Instances'][0]
    
    # Check if the specific EC2 instance has Cloud Trail logging enabled.
    
    if not instance['Monitoring']['State'] == "enabled":
        compliance_status = "NON_COMPLIANT"

    evaluation = {
        'ComplianceResourceType': 'AWS::EC2::Instance',
        'ComplianceResourceId': instance_id,
        'ComplianceType': compliance_status,
        'Annotation': 'Detailed monitoring is not enabled.',
        'OrderingTimestamp': config['notificationCreationTime']
    }
    
    config_client = boto3.client('config')
    
    response = config_client.put_evaluations(
        Evaluations=[evaluation],
        ResultToken=event['resultToken']
    )  
    
    return response
```

➜ This is our Lambda function code.

➜ Now we will Navigate to the AWS Lambda service

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708087834226/e8aa1f4a-b1bb-4263-9a44-ad93c28dbd04.png align="center")

➜ Click on the Create Function.

➜ Configure this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708087917301/f67da840-e70f-4cd9-ad1e-fe6540312442.png align="center")

➜ Give the function name Runtime.

➜ Go to the Configuration section and select the permission

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708088035599/32257dcc-f922-42f8-9bb7-c9b0eda84fee.png align="center")

➜Click on the Role name you will redirect to the IAM role page

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708088290713/e160bedc-5dcd-444f-886b-a53d013f2b06.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708088307182/2816f26c-ff35-4a9c-9bd6-78d5153e0d34.png align="center")

➜ Now Click on the Add Permission

➜ Give these four permissions to this

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708088423270/e25306f3-127d-453b-ade4-498a130b2790.png align="center")

➜ Now come back to the function and change the default time of lambda function execution from 3s to 10s

➜ In the Lambda Function all the things are done now we will proceed to the AWS Config Service.

### ➦ Configuring the AWS Cofig Service:

➜ First Navigate to the AWS Config Service.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708104878691/e0e02dd2-30e3-44bb-939e-8b22a93baeaf.png align="center")

➜ You will see this type of interface now click on the Get Started.

➜ Now in the Setting Section

* Recording Strategy &gt;Specific Resource Type
    
* Resource Type &gt; EC2 instance
    
* In the Frequency &gt; Continuous
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105296176/f96cf543-e673-4ca1-814b-58663c3dbda1.png align="center")

➜ Now to have to create the bucket for storing the data.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105280372/9361c824-fc3d-4e3d-aaaa-89834355f576.png align="center")

➜ Here we also configure the SNS for the Notification when anything happened like update create or delete.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105401021/70b5e8b7-4e04-40e7-b0c8-5ab71cac1fe9.png align="center")

➜ Now hit on the Next Button.

➜ Now click on the Rules and ADD rule

➜Now Select the Rule type as Custom Lambda Rule and hit to next.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105543115/911377a7-a776-4eaf-8bdd-bfbf52801c60.png align="center")

  
➜ In the Details section you have to provide the name and arn of the Lambda function

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105689303/d8f45cef-47fc-4522-aea5-29037dde02ff.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105705733/21e5c3b0-8c61-48aa-a05c-055ed22b1833.png align="center")

➜ In the Scope of changes select the Ec2 Instance

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105756000/7bc8f081-5a70-41ab-8016-6a1e918eeee5.png align="center")

➜ Now Hit to Next Button and Review and Save.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708105834913/2ad653f5-f84f-40f0-8964-e9ced89d0408.png align="center")

➜ Our Rule is created successfully.

➜ Now we will enable the Monitoring of the One Ec2 Instance.

➜ Now go the AWS Management Console and Navigate to your running two instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708108858120/6a04bc4f-3b74-4b22-b0f5-86d82bf3cac8.png align="center")

➜ Now in the Monitoring Section Click on Manage detailed monitoring and Enable it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708108901950/06a1e98b-a644-421c-ae37-c422d6dcaccb.png align="center")

➜ Now one instance is in compliant and one in non-compliant.

➜ Now we go to the AWS Config that they provide.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708109009360/8dd39a93-79c8-4adc-b718-e068bbc8ee9c.png align="center")

➜ Here we can see that one is compliant and one is Not compliant

➜ Now we enable the monitoring of the Second Instance, they we see what result the AWS config Provides.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708109162367/c8bde137-0189-4d35-8e4b-f77c80fbb909.png align="center")

➜ Now both instances are in the compliant state.

➜ That is all from my side. If you have any confusion then let me know in the comment section.

## ✍️Conclusion:

Fantastic job, AWS Explorer! 🎉 You've unlocked the power of AWS Config Service and learned how to wield it to maintain control, compliance, and security within your AWS environment.

As we near the end of our 30 Days of AWS journey, remember that AWS Config is your ally in the quest for cloud excellence. Keep exploring its features, experiment with different rules, and tailor it to suit your organization's unique requirements.

With AWS Config Service in your arsenal, you're well-equipped to navigate the complexities of cloud management and drive success in your AWS endeavours.

Stay tuned for more AWS adventures as we continue our journey through the cloud cosmos. Until then, happy configuring, and may your AWS environment always be compliant and secure! ☁️🔍

Stay curious, stay cloud-savvy, and keep rocking those AWS skills! 💪🚀