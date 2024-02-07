---
title: "IAM Basics☁#90DaysofDevOps"
datePublished: Fri Feb 10 2023 13:50:50 GMT+0000 (Coordinated Universal Time)
cuid: clsbgmqmi001c08jxanfqftvq
slug: iam-basics-90daysofdevops-bcd1c43d1a8b
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290412793/5f09f421-9a4b-48ff-a127-7f1ea8fa8af4.png

---

Hello Everyone Welcome to my new blog, I hope you are doing well…

In this blog we will Discuss about IAM.

### What is IAM:-

Identity and Access Management (IAM) is a web service that provides secure control of access to AWS resources. It allows you to manage users, security credentials such as access keys and passwords, and permissions that determine which AWS resources users can access.

With IAM, you can create and manage AWS users and groups, and use permissions to allow and deny their access to AWS resources. You can also set up and manage permissions for your AWS resources using AWS Identity and Access Management policies.

IAM is a feature of AWS that is free to use. There is no additional charge for using IAM, and there are no minimum fees or startup costs.

It is an important tool for securing your AWS resources and maintaining regulatory compliance by controlling access to your AWS resources and data. IAM enables you to enforce the principle of least privilege, where users are granted only the minimum permissions necessary to perform their jobs.

Here are some important topics to focus on while studying AWS Identity and Access Management (IAM):

> **IAM Users:** An IAM user represents a person or service who accesses your AWS account. You can create, modify, and delete IAM users, and manage the permissions and access levels for each user.

> **IAM Groups**: An IAM group is a collection of IAM users. You can manage the permissions for a group as a single entity, making it easier to manage permissions for multiple users.

> **IAM Roles:** An IAM role is a set of permissions that define what actions an entity can perform in AWS. Roles can be assumed by AWS services, applications, or users.

> **IAM Policies:** An IAM policy is a document that defines one or more permissions. Policies can be attached to IAM users, groups, and roles, and they determine what actions the associated entity can perform in AWS.

> **Access Keys and Passwords:** IAM users need to have a set of credentials, such as an access key ID and secret access key or a password, in order to access AWS resources. You can manage these credentials through IAM.

> **Multi-Factor Authentication (MFA):** MFA provides an extra layer of security by requiring users to provide two forms of authentication before they can access AWS resources.

> **Federation:** Federation enables you to grant external users, such as employees of a partner company, access to your AWS resources using their existing credentials, such as a Microsoft Active Directory.

> **Identity Provider (IdP):** An IdP is a service that provides authentication for users. IAM integrates with popular IdPs such as Google, Facebook, and Amazon, so you can use these IdPs to authenticate users and manage their access to AWS resources.

> **Audit Logging:** IAM provides the ability to log AWS Management Console sign-in events and API activity, enabling you to monitor and audit user activity in your AWS account.

> **Security Best Practices:** It is important to follow best practices when using IAM to secure your AWS resources, such as regularly rotating access keys and passwords, enabling MFA, and keeping policies and permissions up to date.

> **IAM User Step**

Here is a step-by-step guide to creating a user in AWS Identity and Access Management (IAM):

Log in to the AWS Management Console and navigate to the IAM dashboard.

In the navigation panel, click on “Users” and then click the “Add user” button.

Provide a unique username for the new user.

Choose the access type for the user. There are two options:

AWS Management Console access: This allows the user to log in to the AWS Management Console and access AWS services through the console.  
Programmatic access: This allows the user to access AWS services using the AWS CLI or API.  
If you chose “AWS Management Console access,” select the desired password options. You can either choose to let the user create their own password or you can auto-generate a password for them.

If you chose “Programmatic access,” the next step is to create an access key for the user. This consists of an access key ID and secret access key. You can download the access key information as a CSV file or send it directly to the user via email.

Attach permissions policies to the user to determine what actions they can perform in AWS. You can either use an existing policy or create a new one.

Review the user information to ensure that it is correct, then click the “Create user” button.

If you chose to auto-generate a password, it will be displayed on the next screen. Make sure to send it to the user or provide it in a secure manner.

Once you have completed these steps, the new user will be able to access AWS services with the permissions you have granted.

> **IAM Group Steps**

Here’s a step-by-step guide on how to create a group in AWS Identity and Access Management (IAM):

Log in to the AWS Management Console and navigate to the IAM dashboard.

Click on the “Groups” section in the left-side menu and then click on the “Create new group” button.

Enter a name for the new group and select the policy or policies that you want to attach to the group. You can use the default policies provided by AWS or you can create custom policies.

Click on the “Create group” button to create the group.

After the group has been created, you can add users to the group by clicking on the group name and then clicking on the “Add users to group” button.

Enter the names of the users you want to add to the group and then click on the “Add users” button.

The users you added will now have the permissions associated with the group’s policy or policies.

That’s it! With these steps, you can easily create a group in AWS IAM and manage the permissions for multiple users.

> **IAM Role Steps**

Here’s a step-by-step guide on how to create a role in AWS Identity and Access Management (IAM):

Log in to the AWS Management Console and navigate to the IAM dashboard.

Click on the “Roles” section in the left-side menu and then click on the “Create role” button.

Select the type of entity that will use the role, such as an EC2 instance or a Lambda function.

Select the use case for the role, such as “AWS service” or “Another AWS account”.

Attach one or more policies to the role to define the permissions for the role. You can use the default policies provided by AWS or you can create custom policies.

Review the role and its permissions and then click on the “Create role” button to create the role.

Once the role is created, you can use it to delegate access to AWS resources to an AWS service, another AWS account, or a user in your own AWS account.

That’s it! With these steps, you can easily create a role in AWS IAM and delegate access to AWS resources to other entities.

SO well done we are completed our IAM tutorial.

So let’s move forward to our today’s task..

### Task1:

*   Launch EC2 instance with already installed Jenkins on it. Once server shows up in console, hit the IP address in browser and you Jenkins page should be visible.
*   Take screenshot of Userdata and Jenkins page, this will verify the task completion.

Now first we will launch our instance with jenkins dowlonded and by using public ip address we go to the jenkins page..

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290408377/2c02c4fc-70d7-4aa2-869a-ac584b01298f.png)

This image is of our launching instance

Directing on this page ..

Create three Role named: devops-user

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290410905/18ad2e97-a482-4b98-b40c-40cb2c861160.png)

How to create user, role and group we had discuss above..

Thanks for the reading blog, if u like this then please follow me for such a content.

### Happy Learning..