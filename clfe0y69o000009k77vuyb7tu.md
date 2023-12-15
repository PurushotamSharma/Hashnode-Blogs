---
title: "Linux & Git commands Cheat sheet"
datePublished: Sat Mar 18 2023 13:48:21 GMT+0000 (Coordinated Universal Time)
cuid: clfe0y69o000009k77vuyb7tu
slug: linux-git-commands-cheat-sheet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681627477216/ad8f9e78-400a-4bb7-b737-7cbce4b597d9.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1679147278948/635386fb-db53-41a4-adc7-082ee1e4a024.png
tags: linux, github, git, developer, devops

---

# Linux:

> **ls — The most frequently used command in Linux to list directories**
> 
> **pwd — Print working directory command in Linux**
> 
> **cd — Linux command to navigate through directories**
> 
> **mkdir — Command used to create directories in Linux**
> 
> **mv — Move or rename files in Linux**
> 
> **cp — Similar usage as mv but for copying files in Linux**
> 
> **rm — Delete files or directories**
> 
> **touch — Create blank/empty files**
> 
> **ssh — Secure Shell command in Linux**
> 
> **service — Linux command to start and stop services**
> 
> **ln — Create symbolic links (shortcuts) to other files**
> 
> **cat — Display file contents on the terminal**
> 
> **clear — Clear the terminal display**
> 
> **echo — Print any text that follows the command**
> 
> **less — Linux command to display paged outputs in the terminal**
> 
> **ps — Display active processes**
> 
> **kill and killall — Kill active processes by process ID or name**
> 
> **df — Display disk filesystem information**
> 
> **mount — Mount file systems in Linux**
> 
> **chmod — Command to change file permissions**
> 
> **chown — Command for granting ownership of files or folders**
> 
> **ifconfig — Display network interfaces and IP addresses**
> 
> **traceroute — Trace all the network hops to reach the destination**
> 
> **wget — Direct download files from the internet**
> 
> **ufw — Firewall command**
> 
> **iptables — Base firewall for all other firewall utilities to interface with**
> 
> **apt, pacman, yum, rpm — Package managers depending on the distro**
> 
> **sudo — Command to escalate privileges in Linux**
> 
> **cal — View a command-line calendar**
> 
> **alias — Create custom shortcuts for your regularly used commands**
> 
> **dd — Majorly used for creating bootable USB sticks**
> 
> **whereis — Locate the binary, source, and manual pages for a command**
> 
> **whatis — Find what a command is used for**
> 
> **top — View active processes live with their system usage**
> 
> **useradd and usermod — Add new user or change existing users data**
> 
> **passwd — Create or update passwords for existing users**
> 
> **man — Access manual pages for all Linux commands**
> 
> **uname — Linux command to get basic information about the OS**
> 
> **whoami — Get the active username**
> 
> **tar — Command to extract and compress files in Linux**
> 
> **grep — Search for a string within an output**
> 
> **head — Return the specified number of lines from the top**
> 
> **tail — Return the specified number of lines from the bottom**
> 
> **diff — Find the difference between two files**
> 
> **cmp — Allows you to check if two files are identical**
> 
> **comm — Combines the functionality of diff and cmp**
> 
> **sort — Linux command to sort the content of a file while outputting**
> 
> **export — Export environment variables in Linux**
> 
> **zip — Zip files in Linux**
> 
> **unzip — Unzip files in Linux**

# Git:

**STAGE & SNAPSHOT:- Working with snapshots and the Git staging area**

`git status :- show modified files in working directory, staged for your next commit   git add :- add a file as it looks now to your next commit (stage)   git reset :-unstage a file while retaining the changes in working directory   git diff:- diff of what is changed but not staged   git diff — staged:- diff of what is staged but not yet committed   git commit -m “[descriptive message]”:-commit your staged content as a new commit snapshot`

**SETUP**

**Configuring user information used across all local repositories**

`git config — global` [`user.name`](http://user.name) `“[firstname lastname]”   set a name that is identifiable for credit when review version history   git config — global` [`user.email`](http://user.email) `“[valid-email]”   set an email address that will be associated with each history marker   git config — global color.ui auto   set automatic command line coloring for Git for easy reviewing`

**BRANCH & MERGE**

**Isolating work in branches, changing context, and integrating changes**

`git branch   list your branches. a * will appear next to the currently active branch   git branch [branch-name]   create a new branch at the current commit   git checkout   switch to another branch and check it out into your working directory   git merge [branch]   merge the specified branch’s history into the current one   git log   show all commits in the current branch’s history`

**SETUP & INIT  
Configuring user information, initializing and cloning repositories  
git init  
initialize an existing directory as a Git repository  
git clone \[url\]  
retrieve an entire repository from a hosted location via URL**

Happy Learning:))