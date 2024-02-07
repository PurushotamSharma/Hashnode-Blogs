---
title: "Day 18 Exploring the AWS Cloud Front #30daysofaws"
datePublished: Sat Jan 27 2024 11:52:46 GMT+0000 (Coordinated Universal Time)
cuid: clsbgnc4j001d08jx98tc0inn
slug: day-18-exploring-the-aws-cloud-front-30daysofaws-8f0781922a5e
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290440582/84341fb8-0673-4dae-8ee2-0a47ad2775ea.png

---

### Introduction:

🚀 Welcome to Day 18 of our exhilarating 30 Days of AWS series! Today, we’re about to embark on an exciting journey into the cloud, as we delve deep into the AWS CloudFront service. 🌐✨ Get ready to unravel the magic behind Content Delivery Networks (CDN) and discover how CloudFront plays a pivotal role in delivering content at lightning speed around the globe! 🚀

💡 Buckle up as we explore key points, uncover features, and demystify the mechanisms that make AWS CloudFront a game-changer in the world of cloud computing. Let’s make your applications faster, more secure, and seamlessly distributed worldwide! 🌍🔐 #AWS #CloudFront #CDNExploration #30DaysOfAWS 🚀

### Agenda:

*   Introduction
*   What is CDN

### **What is CDN?**

CDN stands for the Content Delivery Network. A CDN is a network of interconnected servers that speed up webpage loading for data-heavy applications.

Now there is the question in your mind why do we need the CDN??

**Why?**

Let’s understand by one scenario- Imagine you have a website with lots of content like images, videos, and documents and you host in Mumbai,

Now one user from Europe is accessing your website then he gets high latency in accessing your content because your server is deployed in the Mumbai region and Europe is away from Mumbai so it takes time to load data to reduce the latency we use the CDN.

In short, CDN is used for Reducing the Latency.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290417396/431ae285-22d8-45e5-b0e5-df33a7b34765.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290419026/c4e83391-43f7-4239-86cf-817b8fb1c665.png)

Here is one Image from this you can understand.

**How does it work?**

A CDN is like a network of servers spread across various locations worldwide. These servers store a copy of your website content when a user requests your website the content is delivered from the server's closet to the users, making it super fast! It is like having a local store for your website content everywhere in the world.

### AWS Cloud Front:

*   Cloud Front is a global service.
*   Amazon Cloud Front is a web service that speeds up the distribution of your static and dynamic web content, such as HTML CSS js and image files to users.
*   Cloud Front delivers your content through a worldwide network of data centres called Edge Location.
*   When you request content served with CloudFront, you are automatically routed to the edge location that provides the lowest latency, ensuring that your content is delivered with optimal performance.
*   If the content is already in the Edge location with the lowest latency, Cloud Front delivers it immediately.
*   This dramatically reduces the number of networks that your user’s request must pass through which improves performance.
*   if not Cloud Front retrieves it from an Amazon S3 bucket or an HTTP/ Web Server that you have identified as the source for the definitive version of your content.
*   Cloud Front also keeps persistent connections with origin Servers so files are fetched from the origins as quickly as possible.

### Ways to Access Cloud Front:

1.  AWS Management Console
2.  AWS SDK’s
3.  Cloud Front API
4.  AWS Command Line Interface

#### Edge Location:

*   Edge locations are not tied to availability zones.
*   CloudFront utilizes a global network of servers known as “Edge Locations” to cache and distribute content closer to the end-users, thereby reducing latency and improving overall performance.
*   These are the points of presence strategically located around the world. They serve as caching servers that store copies of your content. When a user requests content, CloudFront delivers it from the nearest edge location, optimizing speed and reducing latency.
*   Amazon Cloud Front has 216 points of presence (205 Edge locations and 11 Regional Edge Cache ) in 84 cities across 42 countries.

#### **Regional Edge Cache:**

Regional Edge Cache refers to a type of content delivery network (CDN) architecture that stores cached content at the edge of the network, closer to end users, to improve content delivery performance. It involves deploying cache servers in various regions around the world, allowing for faster content delivery to users within those regions.

#### How AWS Cloud Front Works:

Let this be understood by one example:

Suppose you deployed one website to the Mumbai server and it is properly working after some days one client from the UK accessing that website and that client gets high latency while accessing.

So what we will do we will use the AWS cloud front service

First, we deployed our website using the AWS Cloud front, Cloud front has 205 edge locations across the world, now if a person accesses the website then it goes first to the nearest edge location and provides the response and it stores this content in it for 24 hours. After that in 24 hours there is no request for that content then it automatically deletes from the Egde location and transfers to the Regional Edge Cache.

Let’s Do practical for this one:

*   Go to the AWS Management console and Navigate to Cloud Front Service
*   Before that let’s build one S3 bucket because we need one source for accessing the content.
*   Navigate to the S3 bucket and Create one Bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290420510/3b6a26e9-c09f-49fb-ad73-d0df920d812b.png)

*   Here you will see this type of interface now click on the Create Bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290422365/541e5bbc-2478-4ad9-8ad8-2986ec62b20b.png)

*   Here give the name of your bucket.
*   Last but not least click on the bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290423906/a6ba4e4c-3d61-42ac-9360-7090740cc111.png)

*   Congrats our first step is completed.
*   Now Click on that bucket and upload one picture or any HTML file for accessing
*   Note: Remember that file name.
*   Here I am uploading one image for access.
*   Click on the upload button,click on the add file and upload it.
*   Now Navigate to the Cloud front service.
*   Click on the Create a Cloud Front Distribution.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290425392/fd038412-6590-4c0e-81e5-7dfde972091a.png)

*   In the origin domain select your S3 bucket that you recently created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290426748/ae2d5fb5-92e5-48be-b05c-0e5bb5be73bf.png)

*   Now select the Origin Access Control Settting

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290428313/c62b76bf-90cf-471e-b648-5d970017243d.png)

*   Click on the Create Control Setting.
*   Click on the Create

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290429779/2ed08b2f-ef58-44ec-90dd-57ccdcd5ccd9.png)

*   Leave other as deagult
*   Click on the Create Distribution

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290431648/ef784f35-a9d5-4bc0-87f8-603c4693d6d2.png)

*   Now You will see this type of interface.
*   Copy policy and click on the Go to S3 bucke permission to update policy

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290432996/efcfba44-0243-44cb-b7f8-1ecab400914c.png)

*   In the bucket policy paste the policy that you copyied.
*   And save changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290434390/ec7fa260-07d6-40fc-a73a-80530c21f3f3.png)

*   Here you can see our Cloud Front Status is in Deploying wait for some seconds.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290435857/82eb0e43-af78-47ee-b387-57a78a5ede92.png)

*   Now copy the distribution domain and paste to the web browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290437065/4cd7a613-692e-498e-9082-037f2a492a19.png)

*   After pasting your domain name write your file name that you upload to the S3 bucket.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290438777/90d8f228-ae7b-40f1-a0a2-a98376c693ba.png)

*   You can access your file.
*   That all from my side.

Thanks for reading this blog.It help you then share with your friends.

Happy Learning:))

#### Github Profile:

[**PurushotamSharma - Overview**  
*Purusing MCA from Charusat University. PurushotamSharma has 39 repositories available. Follow their code on GitHub.*github.com](https://github.com/PurushotamSharma "https://github.com/PurushotamSharma")[](https://github.com/PurushotamSharma)

#### Github Repo for 30 Days of AWS

[https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)