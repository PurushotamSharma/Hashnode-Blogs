---
title: "Day 6 Task: File Permissions and Access Control Lists"
datePublished: Tue May 16 2023 16:04:13 GMT+0000 (Coordinated Universal Time)
cuid: clhqgs5lo000009jnck2whgvb
slug: day-6-task-file-permissions-and-access-control-lists
tags: linux, technology, devops, shell, trainwithshubham

---

Hello Everyone Welcome to my new blog, Hope you all are doing well. In today's blog we will be discussing the File Permissions and Access Control Lists. Let's Start...

The concept of Linux File permission and ownership is important in Linux. Here, we will be working on Linux permissions and ownership and will do tasks on both of them. Let us start with the Permissions.

### What is Permission?

  
In Linux, file and directory permissions are important for controlling access to files and ensuring security. The permissions determine who can read, write, and execute a file or directory.

Permissions are divided into three categories: user, group, and others. Each category has three types of permissions: read (r), write (w), and execute (x). Here's a breakdown of the permission levels and their meanings:

* Read (r): Allows the user to view the contents of a file or list the contents of a directory.
    
* Write (w): Allows the user to modify the contents of a file or create/delete files in a directory.
    
* Execute (x): Allows the user to execute a file (if it is a program or script) or access files within a directory (if it is a directory).
    

\=&gt; Create a simple file and do `ls -ltr` to see the details of the files.

Each of the three permissions are assigned to three defined categories of users. The categories are:

"**chown**" is used to change the ownership permission of a file or directory.

```bash
Owner: The owner of the file or application.
```

**"chgrp" is used to change the group of a file or directory.**

```bash
group: The group that own that files or application
```

**"chmod" is used to change the other user's permission of file or directory.**

```bash
other: All user that has access to the system
```

As a task, change the user permissions of the file and note the changes after `ls -ltr`

let's try by yourself if you can't get then comment to me I will give you the answer.

Thanks for reading the blog. If you like this then like the blog. If you have any sought then let me know in the comment section. I will we there always for you.

# Happy Learning:))