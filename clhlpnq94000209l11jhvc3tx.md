---
title: "Day 4 Task: Basic Linux Shell Scripting for DevOps Engineers."
datePublished: Sat May 13 2023 08:13:52 GMT+0000 (Coordinated Universal Time)
cuid: clhlpnq94000209l11jhvc3tx
slug: day-4-task-basic-linux-shell-scripting-for-devops-engineers
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1683965568694/121a169d-d890-433a-9508-10865d5def23.jpeg
tags: linux, devops, shell, shubhamlondhe, trainwithshubham

---

Hello Everyone welcome to my new blog. Hope you all are doing well Let's start today's task

## What is Kernel?

The kernel is a computer program that is the core of a computer’s operating system, with complete control over everything in the system.

## What is Shell?

A shell is special user program which provide an interface to user to use operating system services. Shell accept human readable commands from user and convert them into something which kernel can understand. It is a command language interpreter that execute commands read from input devices such as keyboards or from files. The shell gets started when the user logs in or start the terminal.

## What is Linux Shell Scripting?

A shell script is a computer program designed to be run by a linux shell, a command-line interpreter. The various dialects of shell scripts are considered to be scripting languages. Typical operations performed by shell scripts include file manipulation, program execution, and printing text.

## **Tasks:**

### Explain in your own words and examples, what is Shell Scripting for DevOps.

  
Shell scripting is a programming language used to automate repetitive tasks and execute commands in a command-line interface (CLI) or terminal. It is a key tool for DevOps engineers who need to automate the deployment and management of software applications in a consistent and repeatable way.

In DevOps, shell scripting is used to automate a wide range of tasks, such as configuring servers, deploying applications, running tests, and monitoring system performance. These tasks can be executed on a single machine or across multiple machines in a distributed environment.

For example, a DevOps engineer might use shell scripting to create a script that automatically deploys a new version of a web application to a production server. The script would include commands to stop the existing application, download the new version, update any configuration files, and restart the application. The script could be run manually or scheduled to run automatically on a regular basis.

### What is `#!/bin/bash?` can we write `#!/bin/sh` as well?

`#!/bin/bash` is called the "shebang" line and is a special syntax used at the beginning of shell scripts to specify the interpreter that should be used to execute the script. In this case, `#!/bin/bash` specifies that the Bash shell should be used to interpret and execute the script.

Yes, it's also possible to use `#!/bin/sh` to specify that the default system shell should be used. In most Linux/Unix systems, `/bin/sh` is usually a symbolic link to the system's default shell, which could be Bash, Dash, or another shell depending on the distribution and version.

### Write a Shell Script that prints `I will complete #90DaysOofDevOps challenge`

```bash
#!/bin/bash

echo "I will complete #90DaysOfDevOps challenge"
```

You can save this script to a file with a `.sh` extension, for example [`challenge.sh`](http://challenge.sh), and then make it executable with the command:

```bash
chmod +x challenge.sh
```

After that, you can run the script by typing `./`[`challenge.sh`](http://challenge.sh) in a terminal.

### Write an Example of If else in Shell Scripting by comparing 2 numbers?

```bash
#!/bin/bash

# Define two variables 'num1' and 'num2' with some values
num1=10
num2=20

# Compare the values of the two variables using an if-else statement
if [ $num1 -gt $num2 ]
then
  echo "$num1 is greater than $num2"
else
  echo "$num2 is greater than or equal to $num1"
fi
```

Thanks for reading the blog

Happy Learning:::))