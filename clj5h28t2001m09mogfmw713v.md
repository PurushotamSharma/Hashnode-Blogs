---
title: "Day 11 Task: Advance Git & GitHub for DevOps Engineers: Part-2"
datePublished: Wed Jun 21 2023 08:48:19 GMT+0000 (Coordinated Universal Time)
cuid: clj5h28t2001m09mogfmw713v
slug: day-11-task-advance-git-github-for-devops-engineers-part-2
tags: github, git, devops, trainwithshubham

---

If you read my yesterday blog there we discuss Git commands like git branch, git merge, and do their task also if you don't read please read that that was very interesting, I hope you like that…

In this, we will discuss the Git Stash, Cherry-pick, and Resolving Conflicts and do some problems related to them….

Now let’s start with our first topic …

> **What is Git Stash ?**

Sometimes you want to switch branches, but you are working on a project that has been not completed and you do not have to commit half the work. Git stashing allows you to do so. The **git stash command** enables you to switch branches without committing to the current branch.

The below figure demonstrates the properties and role of stashing concerning the repository and working directory.

![](https://miro.medium.com/v2/resize:fit:750/0*DJ2eXGKkbTBxIX9r.png align="left")

Generally, the stash’s meaning is “**store something safely in a hidden place**.” The sense in Git is also the same for stash; Git temporarily saves your data safely without committing.

Stashing takes the messy state of your working directory, and temporarily save it for further use. Many options are available with git stash. Some useful options are given below:

> **Git stash**
> 
> **Git stash save**
> 
> **Git stash list**
> 
> **Git stash apply**
> 
> **Git stash changes**
> 
> **Git stash pop**
> 
> **Git stash drop**
> 
> **Git stash clear**
> 
> **Git stash branch**

### What is Cherry-pick?

Cherry picking is **the act of picking a commit from a branch and applying it to another**. git cherry-pick can be useful for undoing changes. For example, say a commit is accidentally made to the wrong branch. You can switch to the correct branch and cherry-pick the commit to where it should belong.

To use git cherry-pick, you first create two new branches and make some commits to them. Then you use git cherry-pick &lt;commit\_hash&gt; command to select the specific commits from one branch and apply them to the other.

> **What is Resolving Conflicts?**

Conflicts can occur when you merge or rebase branches that have diverged, and you need to manually resolve the conflicts before git can proceed with the merge/rebase. git status command shows the files that have conflicts, git diff command shows the difference between the conflicting versions and git add command is used to add the resolved files.

# Task:1

> **Create a new branch and make some changes to it.**

In this we create new branch test according to question and after that do some changes to file …..

![](https://miro.medium.com/v2/resize:fit:875/1*wCEzHVREzKA0FCC7xZeHhA.jpeg align="left")

![](https://miro.medium.com/v2/resize:fit:875/1*jHrk-8yPOUMyTH8qJA9VYQ.jpeg align="left")

Both work we done in point first . Let’s go forward…..

> **Use git stash to save the changes without committing them.**

![](https://miro.medium.com/v2/resize:fit:875/1*fel9Dt8gYa0R8xV4TgKfqA.jpeg align="left")

> **Switch to a different branch, make some changes and commit them.**

![](https://miro.medium.com/v2/resize:fit:875/1*iWr16RsgzZyZyN1I8wjIuA.png align="left")

> **Use git stash pop to bring the changes back and apply them on top of the new commits.**

![](https://miro.medium.com/v2/resize:fit:875/1*ucfIkSMBk7f_FxjB3FomZA.png align="left")

# Task-02

> **In version01.txt of development branch add below lines after “This is the bug fix in development branch” that you added in Day10 and reverted to this commit.**

For this we go to our version01.txt and make this changes and commit

![](https://miro.medium.com/v2/resize:fit:875/1*VnMHdDT7fxL1j6dyiNAU9g.jpeg align="left")

> **Line2&gt;&gt; After bug fixing, this is the new feature with minor alteration”**
> 
> **Commit this with message “ Added feature2.1 in development branch”**

![](https://miro.medium.com/v2/resize:fit:875/1*QjOfIRerQ2ntCH4TqO8c2g.jpeg align="left")

> **Line3&gt;&gt; This is the advancement of previous feature**
> 
> **Commit this with message “ Added feature2.2 in development branch”**

![](https://miro.medium.com/v2/resize:fit:875/1*Smz9-N_KgLjcmcKYqOny1g.jpeg align="left")

> **Line4&gt;&gt; Feature 2 is completed and ready for release**
> 
> **Commit this with message “ Feature2 completed”**

![](https://miro.medium.com/v2/resize:fit:875/1*saBnzBEFKsL2bE9ttMchPg.jpeg align="left")

> **All these commits messages should be reflected in Production branch too which will come out from Master branch**

In this we use git rebase &lt;from which branch&gt;

![](https://miro.medium.com/v2/resize:fit:875/1*S741l4utyqYdRJqmPtqtDw.jpeg align="left")

# :))Happy learning……….