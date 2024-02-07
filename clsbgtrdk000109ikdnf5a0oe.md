---
title: "Day 10 Task: Advance Git & GitHub for DevOps Engineers."
datePublished: Tue Jan 10 2023 15:26:56 GMT+0000 (Coordinated Universal Time)
cuid: clsbgtrdk000109ikdnf5a0oe
slug: day-10-task-advance-git-github-for-devops-engineers-8fe67e140940
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707290740013/e17b84d6-9f96-42d8-b68f-b65670dbdab1.png

---

In today task we will learn all about Advance Git & GitHub for DevOps Engineers:-

We will learn about all these:-

1.  Git Branching
2.  Git Revert and Reset
3.  Git Rebase and Merge

Let’s Start Today’s topics:-

> **What is Git Branching?**

Git, branches are a part of your everyday development process. Git branches are **effectively a pointer to a snapshot of your changes**. When you want to add a new feature or fix a bug — no matter how big or how small — you spawn a new branch to encapsulate your changes.

**Git Branching**

> **What is Git Revert?**

The git revert command is **a forward-moving undo operation that offers a safe method of undoing changes**. Instead of deleting or orphaning commits in the commit history, a revert will create a new commit that inverses the changes specified. Git revert is a safer alternative to git reset in regards to losing work.

Let’s understand by the piratical:-

The syntax to revert a Git commit and undo unwanted changes is simple. All developers need to do is issue the git revert command and provide the ID of the commit to undo:

> **We will start with a** [**git init**](https://www.theserverside.com/video/How-to-create-a-local-repository-with-the-git-init-command) **command to create a completely clean repository:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290695022/877e8c56-1994-40b0-bdba-33399ff2c117.png)

> **With the repository initialized, we’ll add three files to the repo. Each time a new file is created, we add it to the Git index and create a new commit with a meaningful message.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290696615/fd2b9ffc-b679-4e2f-b017-9a5fca4c4afc.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290698294/dd9e2b24-91d9-4f9c-97c2-b02f888087ca.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290700291/b105969c-06e3-4336-9b59-d60fdfe0d91e.png)

> **A quick directory listing following the initial command batch shows three files in the current folder: By using ls command**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290702086/9cc59bae-1206-429f-9065-08b31936d1e4.png)

> **A call to the** [**git reflog command**](https://www.theserverside.com/video/Git-reflog-vs-log-How-these-commit-history-tools-differ) **will show us our current commit history:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290703652/f6df989e-0f66-4433-868a-417f3359ebf1.png)

> **How to revert a Git commit**

> **What do you think would happen if we did a git revert on the second commit with ID 04ac80d ? This was the git commit that added the beta.html file.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290705018/5483166b-2e1b-4d97-97ac-dc4c5856951a.png)

> **The git revert command will undo only the changes associated with a specific commit. In this git revert example, the second commit added the beta.html file. When we revert said Git commit, the only file removed from our repository is beta.html.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290706471/626c1cdf-0fa7-4543-830d-1fbd36e3c66f.png)

> **What is Git reset?**

Git reset is **a powerful command that is used to undo local changes to the state of a Git repo**. Git reset operates on “The Three Trees of Git”. These trees are the Commit History ( HEAD ), the Staging Index, and the Working Directory. There are three command line options that correspond to the three trees.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290708044/eddf485f-c6f1-4b8d-be76-cfdd134f4f2e.png)

> **What is Git Rebase?**

Rebasing is a process to reapply commits on top of another base trip. It is used to apply a sequence of commits from distinct branches into a final commit. It is an alternative of git merge command. It is a linear process of merging.

In Git, the term rebase is referred to as the process of moving or combining a sequence of commits to a new base commit. Rebasing is very beneficial and it visualized the process in the environment of a feature branching workflow.

It is good to rebase your branch before merging it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290709395/bcbb2df6-02c4-4db4-991e-7e7d918e9127.png)

Generally, it is an alternative of git merge command. Merge is always a forward changing record. Comparatively, rebase is a compelling history rewriting tool in git. It merges the different commits one by one.

Suppose you have made three commits in your master branch and three in your other branch named test. If you merge this, then it will merge all commits in a time. But if you rebase it, then it will be merged in a linear manner. Consider the below image:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290710597/6ebd8a93-59cb-439c-bd0a-2a01700fbc3a.png)

The above image describes how git rebase works. The three commits of the master branch are merged linearly with the commits of the test branch.

> **Syntax:**

> **$git rebase <branch name>**

if there are some conflicts in the branch, resolve them, and perform below commands to continue changes:

> **$ git status**

> **What is Git Merge?**

Git merge is a command that allows developers to merge Git branches while the logs of commits on branches remain intact.

The merge wording can be confusing because we have two methods of merging branches, and one of those ways is actually called “merge,” even though both procedures do essentially the same thing

### **Task:1**

:- Add a text file called version01.txt inside the DevOps/Git/ with “This is first feature of our application” written inside. This should be in a branch coming from `master`,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290712106/71c9b51a-9dbd-4869-b0a3-07c0b1188217.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290713945/f8dffcb9-2084-4887-bfd8-43d7f1113b20.png)

Our first Point of task is completed, now we proceed Further….

> **Git command Use for it: -**

> **cd: change directory**

> **cat :Read data from file**

> **git init :creates a new Git repository**

> **git status: display the state of the working directory and the staging area**

: - switch to dev branch (Make sure your commit message will reflect as "Added new feature").

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290715574/5c6c5adb-bf73-4034-a2a3-67e4692c3a7f.png)

> **Git command Use for it: -**

> **git add . :- add changes to the working directory**

> **git commit :- create a snapshot of the staged changes along a timeline of a git project**

> **git checkout -b <branch name >:- to change the branch**

:- version01.txt should reflect at local repo first followed by Remote repo for review.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290717070/f4eab55b-4923-4dff-ac4a-f0f5ff576ca2.png)

> **Git command Use for it: -**

> **git remote add origin <clone id> :-Validate the existence of your local Git repository**

> **git push -u origin <branch name>:- push term refers to upload local repository content to a remote repository.**

***\==>*** Add new commit in dev branch after adding below mentioned content in DevOps/Git/version01.txt: While writing the file make sure you write these lines

> **1st line>> This is the bug fix in development branch and Commit this with message “Added feature2 in development branch”**

First we will add first line in the version01.txt file …..

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290718740/425e5684-156d-429f-8cb4-d7ec97205c12.png)

Our file is added successfully after that we will commit it by giving message “Added feature2 in development branch”

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290720514/27855b7d-828d-4c50-b497-b8e124dc1f3e.png)

> **2\. add second line >>> This is gadbad code and commit this with message “Added feature 3 in development branch”**

By using nano command be will add the second line and after that we will commit it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290722063/793fa7c0-c14e-47fb-abe3-cf3cbfc7ae71.png)

> **3\. add third line >>> This feature will gadbad everything from now and commit with message “Added feature 3 in development branch”**

In this same as 2 we will add and commit

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290723525/79a6c04e-8819-4cbe-b24b-c9eddc94f578.png)

Next our task is…..

> **Restore the file to a previous version where the content should be “This is the bug fix in development branch**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290725457/6cf50b15-a70c-42c5-bc46-049842cdb63a.png)

> **In this we use command git log and git checkout <commit code> — — <filename/file path>**

### Task 2

> **Demonstrate the concept of branches with 2 or more branches with screenshot.**

In this task we will discuss all about branches ..

By default there is master branches

First we will made one file that is on master branch and we will add and commit that file to dev branch …

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290727296/f281dae7-52e7-49c7-91a3-3db6a23348bc.png)

**we had init the file and after that we will switch to dev branch….**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290729341/3e92ba93-2a18-4cc7-b15e-02e68a7e1e22.png)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290731349/cd770459-3e1d-49c7-b1db-fcf36222ff85.png)

> All the task has been completed…

> \===> Add some changes to dev branch and merge to master branch

> now we make new directory git merge and add one file merge.txt and after that we will init that file and and add , after adding we commit that file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290733015/38101314-2779-48f9-bc82-bda34f20ab36.png)

> **After that we checkout master branch and switch to dev branch and do some changes and after we add and commit that file,**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290734901/700c7c7d-9d2b-4816-9e67-5d090e247c22.png)

> **After we switch to master branch and write in our file that we will merge file , after that we will add and commit**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290736469/87331eb2-51ea-4944-b230-26ee6a63375c.png)

> **Now we will merge the both branches by using command git merge**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707290738319/9ccc0206-edc2-4c97-961c-2243323c32b8.png)

> **Now we merge both file .**

Thanks for reading….