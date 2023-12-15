---
title: "Jenkins"
datePublished: Wed Jun 21 2023 09:32:01 GMT+0000 (Coordinated Universal Time)
cuid: clj5imfpv00080ajjdnz19vxt
slug: jenkins
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1687339881711/3afbc717-6b84-47bc-adf9-c95098160028.jpeg
tags: devops, node, jenkins, shubhamlondhe, trainwithshubham

---

Hello everyone, Welcome to my new blog , hope you all are doing well.

Let's Discuss today's agenda..

### Agenda:-

✨ What is Jenkins?

✨Workflow of Jenkins.

✨Advantages of Jenkins.

✨What is Node in Jenkins?

✨ What is Agent in Jenkins?

Let's Start

### ➥What is Jenkins?

◈ Jenkins is an open-source project written in Java, that runs on Windows,macOS, and other Unix-like OS. It is a free community supported and might be your first choice tool for CI(Continuous Integration.)

◈ Jenkins automates the entire software development life cycle.

◈ Jenkins was originally developed by Sun Microsystem in 2004 under the name Hudson.

◈ The project was later named Jenkins when oracle bought Microsystems.

◈ It can run on any major platform without any compatibility issues.

◈ When developers write code, we integrate all that code and then build, test, and deliver/ deploy to the client. This process is called **CI/CD.**

◈ Because of **CI** Bugs will be reported fast and get rectified fast. So the entire software development happens fast.

### ➥ Workflow of Jenkins

◈ We can attach Git, Maven, Selenium, and Artifactory plugins to Jenkins.

◈ Once developers put the code in GitHub, Jenkins pull that code and send it to Maven for build or other build tools.

◈ Once the build is done, Jenkins pulls that code and sends it to selenium for testing.

◈ Once testing is done, Jenkins will pull that code and send it to Artifactory as per requirement.

◈ We can also deploy with Jenkins.

### ➥ Advantages of Jenkins.

◈ It has a lot of plugins available.

◈ You can write your plugins.

◈ You can use community plugins.

◈ Jenkins is not just a tool.It is a framework i.e. you can do whatever you want. All you need is just plugins.

◈ We can attach slaves (nodes) to Jenkins master. It instructs others (slaves) to do Jobs. If slaves are not available, Jenkins itself does the Job.

◈ Jenkins also behaves as a Cron Server replacement, i.e. can do the scheduled task.

◈ It can create labels.

### What is Node

A machine that is part of the Jenkins environment and capable of executing Pipelines or Jobs. Both the controller and Agent are considered to be Nodes.

### What is Agent in Jenkins?

An agent is typically a machine, or container, which connects to a Jenkins controller and executes tasks when directed by the controller.

### What is Pipeline?

A pipeline is a collection of steps or jobs which are interlinked with one another in a sequence.

There are two types of pipeline

Declarative Pipeline

Scripted Pipeline

### Declarative Pipeline:

Declarative is a more recent and advanced implementation of a pipeline as a code.

### Scripted Pipeline:

Scripted was the first and most traditional implementation of a pipeline as a code in Jenkins. It was designed as a general-purpose DSL(Domain Specific Language) built with Groovy.

### How to install Jenkins In Ubuntu:

**Step 1: Install Java**

Jenkins requires the Java Runtime Environment (JRE). This guide uses OpenJDK for the Java environment. OpenJDK is a Development Kit and includes the Java Runtime Environment.

Follow the steps below to install Java on Ubuntu:

1\. Check if you already have Java installed on your Ubuntu system:

<mark>java -version</mark>

Since Java is not installed on our system, we will install it using OpenJDK.

**Note**: If Java is installed on your Ubuntu system, skip ahead to Step 2.

2\. First, open a terminal window and update the system package repository by running:

```plaintext
sudo apt update
```

3\. Depending on which Java version you want to install, Java 18, run one of the following commands:

```plaintext
sudo apt install openjdk-18-jdk -y
```

**Step 2: Add Jenkins Repository**

It is recommended to install Jenkins using the project-maintained repository, rather than from the default Ubuntu repository. The reason for that is because the Jenkins version in the default Ubuntu repository might not be the latest available version, which means it could lack the latest features and bug fixes.

Follow the steps below to add the Jenkins repository to your Ubuntu system.

1\. Start by importing the GPG key. The GPG key verifies package integrity but there is no output. Run:

```plaintext
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

2\. Add the Jenkins software repository to the source list and provide the authentication key:

```plaintext
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
```

The command adds the Long Term Support (LTS) stable release to the sources list, but there is no output.

**Step 3: Install Jenkins**

After setting up the prerequisites, follow the steps below to install Jenkins on Ubuntu:

1\. Update the system repository one more time. Updating refreshes the cache and makes the system aware of the new Jenkins repository.

```plaintext
sudo apt update
```

2\. Install Jenkins by running:

```plaintext
sudo apt install jenkins -y
```

3\. To check if Jenkins is installed and running, run the following command:

```plaintext
sudo systemctl status jenkins
```

4\. Exit the status screen by pressing **Ctrl**+**Z**.

**Note:** If the Jenkins service is not running or active, run the following command to start it:

```plaintext
sudo systemctl enable --now jenkins
```

That's Great we install Jenkins in our system.

Hope you all enjoy this blog and thanks for reading the blog.

Happy Learning:))

References:

[https://phoenixnap.com/kb/install-jenkins-ubuntu](https://phoenixnap.com/kb/install-jenkins-ubuntu)