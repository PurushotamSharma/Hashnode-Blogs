---
title: "🚀 Day 12: AWS CodeCommit — Version Control in the Cloud"
datePublished: Thu Jan 18 2024 11:02:14 GMT+0000 (Coordinated Universal Time)
cuid: clsbglue0000408l5cuqh4fl6
slug: day-12-aws-codecommit-version-control-in-the-cloud-6855351c2952
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290370894/927f8391-2a0e-497f-8e31-ed1ce4031830.png

---

### Introduction:

🎉 Welcome to Day 12 of our 30 Days of AWS series! Today, we’re delving into the exciting world of AWS CodeCommit. We’ll explore how it works and uncover key concepts that will help you make the most of this powerful tool. So, grab your virtual hard hat and let’s dive into the fascinating realm of AWS CodeCommit! 🚀💻

So when we talk about the Code Commit, the first question that comes to mind is that

#### What is an AWS code Commit?

AWS CodeCommit is a version control service that enables you to securely store and manage assets, including source code, in the cloud. It works seamlessly with Git, providing a fully managed and highly scalable repository hosting service. CodeCommit eliminates the need for you to operate your version control system, allowing you to focus on writing code and collaborating with your team.

### Key Features:

1.  **Secure and Scalable Repositories:**

*   CodeCommit repositories are hosted in a secure and highly scalable environment.
*   Encryption in transit and at rest ensures the security of your source code.

**2\. Integration with AWS Services:**

*   Easily integrate CodeCommit with other AWS services like AWS CodeBuild, AWS CodePipeline, and AWS CodeDeploy to automate your continuous integration and continuous deployment (CI/CD) workflows.

**3\. Collaboration:**

*   Multiple team members can collaborate on a project by cloning the repository and pushing changes.
*   Granular access controls allow you to manage permissions for different users.

**4\. Branching and Merging:**

*   CodeCommit supports branching and merging, facilitating parallel development and easy collaboration on different features.

**5\. Notifications:**

*   Set up notifications to receive alerts on events such as push, and pull requests, or repository activities.

### 🚀 Getting Started with AWS CodeCommit

1.  **Create a Repository:**

*   Open the AWS Management Console and navigate to CodeCommit.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290362410/ce9d0e30-afb4-4185-ac9d-cacbba50a993.png)

*   Click on “Create repository” and follow the prompts to set up your repository

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290364219/9020e322-ec31-4789-a732-826d371faf2c.png)

*   Name your repository and add the Description.
*   After clicking on the create button you will see this type of interface.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290366034/a5ce5944-4626-495d-968b-a2374d8eff05.png)

*   Click on the Clone URL and select HTTPS

**2\. Clone the Repository:**

*   Use the Git clone command to create a local copy of your CodeCommit repository on your development machine.

git clone https://git-codecommit.\[region\].amazonaws.com/v1/repos/\[repository-name\]

*   Here we use visual studio code for cloning the code.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290367422/995fbadb-0002-4bfc-9ddb-f9cdded5d244.png)

*   Now we will add one file and push the changes.
*   Here I created one index.html file and add basic HTML boiler plate

<!DOCTYPE html\>  
<html lang\="en"\>  
<head\>  
    <meta charset\="UTF-8"\>  
    <meta name\="viewport" content\="width=device-width, initial-scale=1.0"\>  
    <title\>Demo of Code Commit</title\>  
</head\>  
<body\>  
      
</body\>  
</html\>

**3\. Add and Commit Changes:**

Make changes to your code, stage them using git add, and commit them using git commit.

First we will add the index.html file and after that commit the changes.

git add index.html 

git commit \-m "First Commit"

We have our insex.html file here

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290368850/4bcf3987-385f-4f6c-a648-74360f5695af.png)

Congrats!! You successfully created the repo using the AWS service code commit.

If you have any doubts then let me know in the comment section.

If you like this blog then give like and start.

#### Github Profile :

[https://github.com/PurushotamSharma](https://github.com/PurushotamSharma)

#### Github Repo for this series:

[**30-Days-of-AWS-Adventure-/Day12 at main · PurushotamSharma/30-Days-of-AWS-Adventure-**  
*Contribute to PurushotamSharma/30-Days-of-AWS-Adventure- development by creating an account on GitHub.*github.com](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/tree/main/Day12 "https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/tree/main/Day12")[](https://github.com/PurushotamSharma/30-Days-of-AWS-Adventure-/tree/main/Day12)

Stay tuned for the day 13

Happy Learning