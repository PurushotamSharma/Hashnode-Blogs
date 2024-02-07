---
title: "Mastering AWS Day 16: Unleashing the Power of CloudWatch 🚀 — Dive Deep, Explore Key Features, and…"
datePublished: Wed Jan 24 2024 07:11:22 GMT+0000 (Coordinated Universal Time)
cuid: clsbgnxf9000g09idgj4of0ow
slug: mastering-aws-day-16-unleashing-the-power-of-cloudwatch-dive-deep-explore-key-features-and-1478e48fe140
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290468179/ca150d6f-3f38-4cf1-b6ac-d7112a909c0c.png

---

### Introduction:

🚀 Welcome to Day 16 of our exhilarating 30 Days of AWS series! Today, we’re delving into the fascinating world of CloudWatch — your go-to tool for monitoring and managing AWS resources. 🌐 In this blog, we’ll demystify CloudWatch, unravelling its inner workings, highlighting key features, and embarking on a hands-on project for a deeper understanding. 💡 Get ready to level up your AWS expertise as we explore CloudWatch’s nuances and tackle a practical project that promises to elevate your monitoring game! Let’s dive in and make the most of this CloudWatch adventure! 🛠️🔍 #AWS #CloudWatch #HandsOnProject #LearnWithUs

### What is AWS CloudWatch?

AWS CloudWatch is a powerful monitoring and observability service provided by Amazon Web Services. It enables you to gain insights into the performance, health, and operational aspects of your AWS resources and applications. CloudWatch collects and tracks metrics, collects and monitors log files, and sets alarms to alert you on certain conditions.

### Advantages of AWS CloudWatch:

**Comprehensive Monitoring:** CloudWatch allows you to monitor various AWS resources such as EC2 instances, RDS databases, Lambda functions, and more. You get a unified view of your entire AWS infrastructure.

**Real-Time Metrics:** It provides real-time monitoring of metrics, allowing you to respond quickly to any issues or anomalies that might arise.

**Automated Actions:** With CloudWatch Alarms, you can set up automated actions like triggering an Auto Scaling group to scale in or out based on certain conditions.

**Log Insights:** CloudWatch Insights lets you analyze and search log data from various AWS services, making it easier to troubleshoot problems and identify trends.

**Dashboards and Visualization:** Create custom dashboards to visualize your application and infrastructure metrics in one place, making it easier to understand the overall health of your system.

### Practical Use Cases of AWS CloudWatch:

**Auto Scaling:** CloudWatch can trigger Auto Scaling actions based on defined thresholds. For example, you can automatically scale in or out based on CPU utilization or request counts.

**Resource Monitoring**: Monitor EC2 instances, RDS databases, DynamoDB tables, and other AWS resources to gain insights into their performance and health.

**Application Insights:** Track application-specific metrics to monitor the performance of your applications and identify potential bottlenecks.

**Log Analysis:** Use CloudWatch Logs Insights to analyze log data, identify patterns, and troubleshoot issues in real time.

**Billing and Cost Monitoring:** CloudWatch can help you monitor your AWS billing and usage patterns, enabling you to optimize costs.

Let’s Jump on the Practical Part:

*   Go to the AWS Management Console and navigate to the AWS CloudWatch Service.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290445197/738ab0cc-e0af-48e6-ae37-e8b8dc921449.png)

*   You will see an interface like the above image.
*   First, we create the EC2 instance and after that, we will create the alarm for the CPU utilization.
*   First, navigate to the EC2 service and create one instance.
*   Give the instance name and select the AMI
*   Here I am selecting the AMI as Ubuntu

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290446909/185cfc06-abb8-4a85-b406-0c3584bd3ebd.png)

*   Select the instance type and create the key

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290449004/cf120e27-02c5-4453-a8ff-e9a8af3fe157.png)

*   Now click on the Launch Instance.
*   Now we will create the alarm for the CPU utilization.
*   Click on the Create Alarm

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290450762/aba4eb05-47e1-4be2-b91e-23f52025915a.png)

*   Now there is a section for selecting the Metric

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290452139/fdf28490-a79c-4522-9b73-aab2cc9bd050.png)

*   Before selecting the metrics make sure that your instance is running.
*   After that click on the select metric

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290453486/36a5670d-5d42-4eb7-9e24-7bbf258a5d8f.png)

*   Here select the EC2 section

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290455034/2efb5158-e62c-461e-8db7-ac2b3f4b9e96.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290456186/701dc6ae-ec4e-4b0e-90c0-5cd9d91ceaf1.png)

*   Select Per-Instance Metrics
*   Here select the metrics that contain the CPU utilization ‘
*   Click on the select metric

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290457371/6b1a613f-10e1-48ba-93b7-755d9de64640.png)

*   We will be creating the alarm for the CPU utilization is up from 50%

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290458784/e74561de-4f62-493e-b76d-08eeb12f6fd4.png)

*   In the threshold option write 50 and click on the next button

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290460268/346b839d-4938-4edd-b2cf-2c08f2100b0d.png)

*   Here we will create one SNS Topic( Simple Notification service ) and assign one email id for the notification.
*   Select the In alarm option then Select the Create new topic

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290461726/bcdd75aa-4e15-4302-bfab-21a5bc530a56.png)

*   Give the topic name and provide the email id where you want to get a notification.
*   Click on the Create topic
*   At the last click on the next
*   Now write the alarm name and description according to you
*   Now click on the next
*   Review and create an alarm.
*   Now Go to the email id that you provide

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290462997/5be261ef-72e1-4de7-9c55-5bb0055acb81.png)

*   Here you will get one email for the confirmation of the notification click on that email and conform it.
*   Now we will run one .py file from that our CPU utilization will be up from 50%
*   cpu\_spike.py here is the file code you can copy and paste to your instance.

import time  
  
def simulate\_cpu\_spike(duration=30, cpu\_percent=80):  
    print(f"Simulating CPU spike at {cpu\_percent}%...")  
    start\_time = time.time()  
  
    \# Calculate the number of iterations needed to achieve the desired CPU utilization  
    target\_percent = cpu\_percent / 100  
    total\_iterations = int(target\_percent \* 5\_000\_000)  \# Adjust the number as needed  
  
    \# Perform simple arithmetic operations to spike CPU utilization  
    for \_ in range(total\_iterations):  
        result = 0  
        for i in range(1, 1001):  
            result += i  
  
    \# Wait for the rest of the time interval  
    elapsed\_time = time.time() - start\_time  
    remaining\_time = max(0, duration - elapsed\_time)  
    time.sleep(remaining\_time)  
  
    print("CPU spike simulation completed.")  
  
if \_\_name\_\_ == '\_\_main\_\_':  
    \# Simulate a CPU spike for 30 seconds with 80% CPU utilization  
    simulate\_cpu\_spike(duration=30, cpu\_percent=80)

*   run this .py file in your ec2 instance using the command
*   python3 cpu\_spike.py
*   After running your .py file your CPU utilization is up from 50 % and you will get the notification.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290464310/c1ba52af-30b4-422b-a2b9-0199ed34e535.png)

*   Our CPU utilization is up from 50% let’s check our email .

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290466174/bed0e2fa-ef68-45d0-9fe5-dac2c9270157.png)

*   Great Congrats on this practical you successfully Created an alarm and also got the notification.
*   Stay tuned for the day 17
*   Happy Learning:))4