---
title: "Day 10 Task: Advance Git & GitHub for DevOps Engineers."
datePublished: Wed Jun 21 2023 08:41:39 GMT+0000 (Coordinated Universal Time)
cuid: clj5gtnwe002a09mg3gv90jkf
slug: day-10-task-advance-git-github-for-devops-engineers
tags: github, git, devops, shubhamlondhe, trainwithshubham

---

In today's task we will learn all about Advance Git & GitHub for DevOps Engineers:-

We will learn about all these:-

1. Git Branching
    
2. Git Revert and Reset
    
3. Git Rebase and Merge
    

Let’s Start with Today’s topics:-

> **What is Git Branching?**

Git, branches are a part of your everyday development process. Git branches are **effectively a pointer to a snapshot of your changes**. When you want to add a new feature or fix a bug — no matter how big or how small — you spawn a new branch to encapsulate your changes.

![](https://miro.medium.com/v2/resize:fit:875/0*kLdCiLDnbK7_ctTM.png align="left")

> **What is Git Revert?**

The git revert command is **a forward-moving undo operation that offers a safe method of undoing changes**. Instead of deleting or orphaning commits in the commit history, a revert will create a new commit that inverses the changes specified. Git revert is a safer alternative to git reset in regards to losing work.

Let’s understand by the piratical:-

The syntax to revert a Git commit and undo unwanted changes is simple. All developers need to do is issue the git revert command and provide the ID of the commit to undo:

> **We will start with a** [**git init**](https://www.theserverside.com/video/How-to-create-a-local-repository-with-the-git-init-command) **command to create a completely clean repository:**

![](https://miro.medium.com/v2/resize:fit:875/1*Svc-c6mlq7G47R0-bogtsw.png align="left")

> **With the repository initialized, we’ll add three files to the repo. Each time a new file is created, we add it to the Git index and create a new commit with a meaningful message.**

![](https://miro.medium.com/v2/resize:fit:875/1*Z-024wjSczlLcQD9Y1Ps_w.png align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*yFMnQUWVmV9JGEyvzEJilw.png align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*fcvwOhMEPouI77Yfu-oEqA.png align="left")

> **A quick directory listing following the initial command batch shows three files in the current folder: By using ls command**

![](https://miro.medium.com/v2/resize:fit:875/1*Y04GjVA_4qPVhy3RLtXATQ.png align="left")

> **A call to the** [**git reflog command**](https://www.theserverside.com/video/Git-reflog-vs-log-How-these-commit-history-tools-differ) **will show us our current commit history:**

![](https://miro.medium.com/v2/resize:fit:875/1*Ba-K7boSa_GUo28DjKr-yA.png align="left")

> **How to revert a Git commit**
> 
> **What do you think would happen if we did a git revert on the second commit with ID 04ac80d ? This was the git commit that added the beta.html file.**

![](https://miro.medium.com/v2/resize:fit:875/1*9MPegyLWCz8v6XcKKOXbUg.png align="left")

> **The git revert command will undo only the changes associated with a specific commit. In this git revert example, the second commit added the beta.html file. When we revert said Git commit, the only file removed from our repository is beta.html.**

![](https://miro.medium.com/v2/resize:fit:875/1*vIq17dXiEHA66utjYOComQ.png align="left")

> **What is Git reset?**

Git reset is **a powerful command that is used to undo local changes to the state of a Git repo**. Git reset operates on “The Three Trees of Git”. These trees are the Commit History ( HEAD ), the Staging Index, and the Working Directory. There are three command line options that correspond to the three trees.

![](https://miro.medium.com/v2/resize:fit:625/0*J0JSQ3hpD0TEds9j.png align="left")

> **What is Git Rebase?**

Rebasing is a process to reapply commits on top of another base trip. It is used to apply a sequence of commits from distinct branches into a final commit. It is an alternative **to the** git merge command. It is a linear process of merging.

In Git, the term rebase is referred to as the process of moving or combining a sequence of commits to a new base commit. Rebasing is very beneficial and it visualized the process in the environment of a feature branching workflow.

It is good to rebase your branch before merging it.

![](https://miro.medium.com/v2/resize:fit:500/0*03rtbGrpImrb77vj.png align="left")

Generally, it is an alternative to the git merge command. Merge is always a forward-changing record. Comparatively, rebase is a compelling history-rewriting tool in git. It merges the different commits one by one.

Suppose you have made three commits in your master branch and three in your other branch named test. If you merge this, then it will merge all commits in a time. But if you rebase it, then it will be merged in a linear manner. Consider the below image:

![](https://miro.medium.com/v2/resize:fit:739/0*49oSfHz1f-_djUge.png align="left")

The above image describes how git rebase works. The three commits of the master branch are merged linearly with the commits of the test branch.

> **Syntax:**
> 
> **$git rebase &lt;branch name&gt;**

if there are some conflicts in the branch, resolve them, and perform below commands to continue changes:

> **$ git status**
> 
> **What is Git Merge?**

Git merge is a command that allows developers to merge Git branches while the logs of commits on branches remain intact.

The merge wording can be confusing because we have two methods of merging branches and one of those ways is actually called “merge,” even though both procedures do essentially the same thing

# **Task:1**

:- Add a text file called version01.txt inside the DevOps/Git/ with “This is first feature of our application” written inside. This should be in a branch coming from `master`,

![](https://miro.medium.com/v2/resize:fit:875/1*Zmq3o4tP8q_NRphLCtMENg.png align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*kKnnH7zYzh1xgcFR0YhP1w.png align="left")

Our first Point of task is completed, now we proceed Further….

> **Git command Use for it: -**
> 
> **cd: change directory**
> 
> **cat :Read data from file**
> 
> **git init :creates a new Git repository**
> 
> **git status: display the state of the working directory and the staging area**

: - switch to dev branch (Make sure your commit message will reflect as "Added new feature").

![](https://miro.medium.com/v2/resize:fit:875/1*7TrmJCWgdjDMNZIcCJmKSg.png align="left")

> **Git command Use for it: -**
> 
> **git add . :- add changes to the working directory**
> 
> **git commit :- create a snapshot of the staged changes along a timeline of a git project**
> 
> **git checkout -b &lt;branch name &gt;:- to change the branch**

:- version01.txt should reflect at local repo first followed by Remote repo for review.

![](https://miro.medium.com/v2/resize:fit:875/1*_e6G-dItwGKmJXHbecESWA.png align="left")

> **Git command Use for it: -**
> 
> **git remote add origin &lt;clone id&gt; :-Validate the existence of your local Git repository**
> 
> **git push -u origin &lt;branch name&gt;:- push term refers to upload local repository content to a remote repository.**

***\==&gt;*** Add new commit in dev branch after adding below mentioned content in DevOps/Git/version01.txt: While writing the file make sure you write these lines

> **1st line&gt;&gt; This is the bug fix in development branch and Commit this with message “Added feature2 in development branch”**

First we will add first line in the version01.txt file …..

![](https://miro.medium.com/v2/resize:fit:875/1*p14ehGFN-zlNv2RdPa36mA.png align="left")

Our file is added successfully after that we will commit it by giving message “Added feature2 in development branch”

![](https://miro.medium.com/v2/resize:fit:875/1*qrU_1Pz_3gY7ARX4Cq6FrA.png align="left")

> **2\. add second line &gt;&gt;&gt; This is gadbad code and commit this with message “Added feature 3 in development branch”**

By using nano command be will add the second line and after that we will commit it.

![](https://miro.medium.com/v2/resize:fit:875/1*yUNy71hpXX8Yhol18hILLA.png align="left")

> **3\. add third line &gt;&gt;&gt; This feature will gadbad everything from now and commit with message “Added feature 3 in development branch”**

In this same as 2 we will add and commit

![](https://miro.medium.com/v2/resize:fit:875/1*4Q3xrpJbivXx4mMo6AK7Ww.png align="left")

Next our task is…..

> **Restore the file to a previous version where the content should be “This is the bug fix in development branch**

![](https://miro.medium.com/v2/resize:fit:875/1*qTxrqLH1uXp3cNgffukfJg.png align="left")

> **In this we use command git log and git checkout &lt;commit code&gt; — — &lt;filename/file path&gt;**

# Task 2

> **Demonstrate the concept of branches with 2 or more branches with screenshot.**

In this task we will discuss all about branches ..

By default there is master branches

First we will made one file that is on master branch and we will add and commit that file to dev branch …

![](https://miro.medium.com/v2/resize:fit:875/1*xSQ7zlaBDQBt57A-H7WZwQ.png align="left")

**we had init the file and after that we will switch to dev branch….**

![](https://miro.medium.com/v2/resize:fit:875/1*EtcAvKQFhT8VmEDwMwJ5tQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*hRWgqcsAyvO5NZYBAOHGNA.png align="left")

> All the task has been completed…

> \===&gt; Add some changes to dev branch and merge to master branch
> 
> now we make new directory git merge and add one file merge.txt and after that we will init that file and and add , after adding we commit that file.

![](https://miro.medium.com/v2/resize:fit:875/1*tHk7voKjHQdYQx2TIY9NMA.png align="left")

> **After that we checkout master branch and switch to dev branch and do some changes and after we add and commit that file,**

![](https://miro.medium.com/v2/resize:fit:875/1*YQyPB2l8DkDTlTkHEo2R0Q.png align="left")

> **After we switch to master branch and write in our file that we will merge file , after that we will add and commit**

![](https://miro.medium.com/v2/resize:fit:875/1*THh9_0UDisxhbWFQzW8l-A.png align="left")

> **Now we will merge the both branches by using command git merge**

![](https://miro.medium.com/v2/resize:fit:875/1*tVVKJOZavtOkRvm6cQDn8w.png align="left")

> **Now we merge both file .**

# Thanks for reading…. Happy Learning...