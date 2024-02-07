---
title: "Day 09: Exploring S3 Buckets 🚀 — 30 Days of AWS Series"
datePublished: Sat Jan 13 2024 13:09:59 GMT+0000 (Coordinated Universal Time)
cuid: clsbgpvre000d09jp2t1b3rvf
slug: day-09-exploring-s3-buckets-30-days-of-aws-series-fcb0a6eda362
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290559529/b7ec8c66-cf26-40c8-a021-5858f2323df6.png

---

### Introduction:

Welcome back to the 30 Days of AWS Series! Today marks Day 09, where we embark on a journey into the heart of Amazon Simple Storage Service (S3) buckets. As we delve into the intricacies of this fundamental AWS service, we’ll uncover the key concepts, explore practical exercises, and navigate through industry-level scenarios.

Amazon S3 is more than just a storage solution; it’s a cornerstone in the AWS ecosystem, offering unparalleled scalability, durability, and versatility. Whether you’re a seasoned cloud architect or just getting started with AWS, this exploration into S3 will provide valuable insights into its capabilities and how it can be harnessed for optimal results.

In this instalment, we’ll not only guide you through the steps of creating your own S3 bucket but also present a hands-on exercise to solidify your understanding. Additionally, we’ll address industry-level scenarios, offering solutions to real-world challenges that organizations face when leveraging S3 for their data storage needs.

Join us as we unravel the layers of Amazon S3, uncovering its features, best practices, and the role it plays in building robust and scalable cloud applications. Whether you’re here for the technical details or seeking practical insights for your business, Day 09 promises to be a journey through the cloud that you won’t want to miss.

So, buckle up and let’s dive into the fascinating world of Amazon S3 buckets!

#### What is S3?

Amazon S3 (Simple Storage Service ) is a

**Scalable**

**Highly Available**

**Secured**

**Cost Effective**

**Performance**

Cloud Storage service Provided by AWS.

It allows you to store and retrieve any amount of data from anywhere on the web.

#### What can you store in this S3 bucket?

S3 service allows you to create buckets in which you can store anything.

Let’s Discuss the Key Points of S3:

1.  **Scalability:** You can store and retrieve any amount of data without worrying about capacity constraints.
2.  **Performance:** S3 is designed to deliver high performance for data retrieval and storage operations.
3.  **Cost-effective:** S3 offers cost-effective storage options and pricing models based on your usage patterns.
4.  **Security:** S3 offers multiple security features such as encryption, access control, and audit logging.
5.  **Durability and availability:** S3 provides high durability and availability for your data.

### Key Concepts:

1.  **Buckets:**

*   In S3, data is stored in containers called buckets. A bucket is a top-level container for objects(Files) within S3.
*   Bucket names must be globally unique across all AWS.

**2\. Objects 📦:**

*   Objects are the basic units of storage in S3. These can be anything from documents and images to videos and application data.
*   Each object is assigned a unique key within a bucket.

**3\. Regions 🌐:**

*   S3 is globally distributed and operates in different geographical regions.
*   You can choose a region for your S3 bucket based on factors like latency and compliance.

Let’s Learn How to create a Bucket:

**Step:01**

*   Go to the AWS Management Console➡️ Search for S3➡️ Click on it

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290543087/0114eda7-77e4-4b1a-bae9-8c3f7be85cea.png)

*   You can see the S3 Interface
*   Now let’s create a bucket and host a static website.
*   Click on the Create Bucket
*   Now select the region on which you want to create and give a unique name to your s3 bucket because it is globally access from anywhere so there is no duplicate name that should be there.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290545015/631ae965-c21a-4986-bb89-1a887637c5e6.png)

*   In the object ownership select as default as of now

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290546567/ed8ee156-f932-4844-af7d-d9e7b00ece15.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290548260/b038c5d9-dca3-4f4f-9762-f6f831643119.png)

*   Enable Block all public access, this will block all access but we want to host our website so we want to disable this otherwise we cannot access our static website.
*   For the demo Disable the versioning

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290549743/f32c1608-0979-41d1-9560-25e44a25fda9.png)

*   In the default encryption select first option

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290551486/5b1fb390-575f-422a-af1d-6bb75f1dd0b1.png)

*   Click on the Create bucket

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290553202/e952ae87-cfd1-4723-9133-619b966bc9dd.png)

*   Congrats you created your first bucket for hosting static website.
*   Now we will upload our static website index.html file a simple todo application

<!DOCTYPE html\>  
<html lang\="en"\>  
<head\>  
    <meta charset\="UTF-8"\>  
    <meta name\="viewport" content\="width=device-width, initial-scale=1.0"\>  
    <style\> body {  
            font-family: Arial, sans-serif;  
            background-color: #f4f4f4;  
            margin: 0;  
            display: flex;  
            align-items: center;  
            justify-content: center;  
            height: 100vh;  
        }  
  
        .container {  
            text-align: center;  
            background-color: white;  
            padding: 20px;  
            border-radius: 8px;  
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);  
        }  
  
        ul {  
            list-style-type: none;  
            padding: 0;  
        }  
  
        li {  
            background-color: #dff0d8;  
            margin: 5px 0;  
            padding: 10px;  
            border-radius: 4px;  
            display: flex;  
            align-items: center;  
            justify-content: space-between;  
        }  
  
        button {  
            padding: 8px;  
            margin-top: 10px;  
            cursor: pointer;  
        } </style\>  
    <title\>Todo App</title\>  
</head\>  
<body\>  
    <div class\="container"\>  
        <h1\>Todo App</h1\>  
        <input type\="text" id\="todoInput" placeholder\="Add a new todo"\>  
        <button onclick\="addTodo()"\>Add Todo</button\>  
        <ul id\="todoList"\></ul\>  
    </div\>  
  
    <script\> function addTodo() {  
            const todoInput = document.getElementById("todoInput");  
            const todoList = document.getElementById("todoList");  
  
            if (todoInput.value.trim() !== "") {  
                const li = document.createElement("li");  
                li.textContent = todoInput.value;  
  
                const deleteButton = document.createElement("button");  
                deleteButton.textContent = "Delete";  
                deleteButton.onclick = function() {  
                    li.remove();  
                };  
  
                const updateButton = document.createElement("button");  
                updateButton.textContent = "Update";  
                updateButton.onclick = function() {  
                    const updatedText = prompt("Update todo:", li.textContent);  
                    if (updatedText !== null) {  
                        li.textContent = updatedText;  
                    }  
                };  
  
                li.appendChild(deleteButton);  
                li.appendChild(updateButton);  
  
                todoList.appendChild(li);  
  
                // Clear input  
                todoInput.value = "";  
            }  
        } </script\>  
</body\>  
</html\>

*   Click on the upload button

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290554648/51f6b3a2-4ca4-4297-800c-cfeda78d2870.png)

*   Add file and click on the upload button.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290556166/43de64d6-2a7b-4b53-a429-eafaf1e2b994.png)

*   Congrats you successfully host your static website:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290557793/c40ce254-0641-4100-842f-4e7830e03cac.png)

*   Congrats everyone for hosting your first static website using the S3 bucket.

Conclusion:

In conclusion, on Day 9 of our 30 Days of AWS series, we delved into the fundamental world of Amazon S3 (Simple Storage Service) and explored the myriad benefits it brings to the table. As a highly scalable and secure object storage service, S3 plays a pivotal role in the AWS ecosystem, offering unparalleled durability, availability, and scalability for storing and retrieving any amount of data.

We demystified the key features of S3, such as its versatile storage classes, data lifecycle management, and robust security features. The understanding gained today empowers us to make informed decisions when architecting storage solutions in the AWS cloud.

Taking our newly acquired S3 knowledge to practical use, we took a hands-on approach by hosting a static todo application directly on S3. This real-world application showcased the simplicity and efficiency of deploying a static website on the cloud, leveraging the scalability and performance capabilities that S3 provides.

As we continue our journey through the vast landscape of AWS services, the foundation laid today with S3 sets the stage for deeper explorations into the cloud infrastructure and services that AWS has to offer. Stay tuned for more insights, hands-on experiences, and practical applications as we progress through our 30 Days of AWS series. Happy cloud computing!

#### GitHub Repository: [https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-)