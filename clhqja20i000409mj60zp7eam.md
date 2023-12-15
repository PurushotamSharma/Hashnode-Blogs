---
title: "Day 7 Task: Understanding package manager and systemctl"
datePublished: Tue May 16 2023 17:14:08 GMT+0000 (Coordinated Universal Time)
cuid: clhqja20i000409mj60zp7eam
slug: day-7-task-understanding-package-manager-and-systemctl
tags: trends, linux, devops, shubhamlondhe, trainwithshubham

---

Hello Everyone, Welcome to my new Blog. Hope you all are doing well. So our Today's topic is Understanding Package manager and systemctl. Let's Start

### What is a package manager in Linux?

In simpler words, a package manager is a tool that allows users to install, remove, upgrade, configure and manage software packages on an operating system. The package manager can be a graphical application like a software center or a command line tool like apt-get or Pacman.

### What is a package?

A package is usually referred to as an application but it could be a GUI application, command line tool, or a software library (required by other software programs). A package is essentially an archive file containing the binary executable, configuration file, and sometimes information about the dependencies.

### Different kinds of package managers

Package Managers differ based on the packaging system but the same packaging system may have more than one package manager.

For example, RPM has Yum and DNF, package managers. For DEB, you have apt-get, aptitude command line-based package managers.

You have to install docker and jenkins in your system from your terminal using package managers

For Docker I am writing the commands and for Jenkins You have to practice if you did not get then let me know in comment section.

```bash
sudo get-apt update
sudo get-apt install docker.io
systemctl start docker
systemctl enable docker
systemctl status docker
```

### systemctl and systems

systemctl is used to examine and control the state of “systemd” system and service manager. systemd is system and service manager for Unix like operating systems(most of the distributions, not all).

## Happy Learning:))