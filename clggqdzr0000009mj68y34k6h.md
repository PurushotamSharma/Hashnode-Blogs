---
title: "Git and GitHub"
datePublished: Fri Apr 14 2023 15:55:45 GMT+0000 (Coordinated Universal Time)
cuid: clggqdzr0000009mj68y34k6h
slug: git-and-github
tags: linux, technology, devops, kunalkushwaha, trainwithshubham

---

Hello Everyone, Welcome to my blog. I hope you all are doing well.

Let's discuss today's topic, so our today topic is Git and Github.

When we listen to Git and Github, the first thing that comes to our mind is that the both are same but we are wrong both things are different.

### `What is Git?`

Git is a DevOps tool used for **source code management**. It is a free and open-source version control system that handles small to large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.

### `What is GitHub?`

GitHub is **a code hosting platform for version control Systems and collaboration**. It lets you and others work together on projects from anywhere.

So we learn about both Git and GitHub. Git is a version control system and GitHub is a platform that stores code and host the code.

Before getting dive into Git and GitHub we have to know some basic terminologies .

There is a term Source code Management and it has two types:

### `CVCS:- Centralized Version Control System`

### `DVCS:- Distributed Version Control System`

### Centralized Version Control System:-

The developers needed to collaborate with other developers on other systems. The localized version control system failed in this case. To deal with this problem, Centralized Version Control Systems were developed.

![Git Version Control system](https://static.javatpoint.com/tutorial/git/images/git-version-control-system-1.png align="left")

These systems have a single server that contains the versioned files, and some clients to check out files from a central place.

Centralized version control systems have many benefits, especially over local VCSs.

* Everyone on the system has information about the work what others are doing on the project.
    
* Administrators have control over other developers.
    
* It is easier to deal with a centralized version control system than a localized version control system.
    
* A local version control system facilitates with a server software component which stores and manages the different versions of the files.
    

It also has the same drawback as in local version control systems that it also has a single point of failure.

### Distributed Version Control System:-

Centralized Version Control System uses a central server to store all the database and team collaboration. But due to single point failure, which means the failure of the central server, developers do not prefer it. Next, the Distributed Version Control System is developed.

In a Distributed Version Control System (such as Git, Mercurial, Bazaar or Darcs), the user has a local copy of a repository. So, the clients don't just check out the latest snapshot of the files even they can fully mirror the repository. The local repository contains all the files and metadata present in the main repository.

![Git Version Control system](https://static.javatpoint.com/tutorial/git/images/git-version-control-system-2.png align="left")

DVCS allows automatic management branching and merging. It speeds up of most operations except pushing and pulling. DVCS enhances the ability to work offline and does not rely on a single location for backups. If any server stops and other systems were collaborating via it, then any of the client repositories could be restored by that server. Every checkout is a full backup of all the data.

| Centralized Version Control System | Distributed Version Control System |
| --- | --- |
| In CVCS, The repository is placed at one place and delivers information to many clients. | In DVCS, Every user has a local copy of the repository in place of the central repository on the server-side. |
| It is based on the client-server approach. | It is based on the client-server approach. |
| It is the most straightforward system based on the concept of the central repository. | It is flexible and has emerged with the concept that everyone has their repository. |
| In CVCS, the server provides the latest code to all the clients across the globe. | In DVCS, every user can check out the snapshot of the code, and they can fully mirror the central repository. |
| CVCS is easy to administrate and has additional control over users and access by its server from one place. | DVCS is fast comparing to CVCS as you don't have to interact with the central server for every command. |
| The popular tools of CVCS are **SVN** (Subversion) and **CVS**. | The popular tools of DVCS are **Git** and **Mercurial**. |
| CVCS is easy to understand for beginners. | DVCS has some complex process for beginners. |
| If the server fails, No system can access data from another system. | if any server fails and other systems were collaborating via it, that server can restore any of the client repositories |

### Git Architecture:-

![](https://codetej.in/wp-content/uploads/2021/05/3-stage-architecture-of-GIt-1024x576.png align="left")

### Important Terms:-

### Repository:-

* A repository is a place where you have all your codes or kind of folder on the server.
    
* It is a kind of folder related to one product.
    
* Changes are personal to that particular repository.
    

### Server:-

* It stores all repositories.
    
* It contains metadata also.
    

### Working Directory:-

* Where you see files physically and do the modification.
    
* At a time , you can work on a particular branch.
    

### Commit:-

* It uses the SHA1 checksum concept.
    
* Even if you change one dot , commit-Id will change.
    
* Commit is also named the SHA-1 hash.
    

### Commit ID/Version-Id/Version:-

* Reference to identity each changes.
    
* To identify who changed the file.
    

### Tags:-

* Tags assign a meaningful name with a specific version in the repository.Once a tag is created for a particular save, even if you create a new commit , it will not be updated.
    

### Snapshots:-

* Represents some data of a particular time.
    
* It is always incremental.
    

### Push:-

* Push operations copy changes form a local repository server to a remote or central repository.This is used to store the changes permanently in the git repository.
    

### Pull:-

* Pull operation copies the changes from a remote repo to a local machine. The pull operation is used for synchronisation between the repo.
    

### Basic Git Commands:-

<mark>#Set global username and email for Git (locally)</mark>

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

<mark>#Initialize an empty Git Repository:-</mark>

```powershell
git init
```

<mark>#Clone an existing Git Repository</mark>

```powershell
git clone <repository_url>
```

<mark>#Add file/stage to git</mark>

```powershell
git add <fileName>
```

<mark>#Add all the current directory files to git</mark>

```powershell
git add .
```

<mark>#Commit all the staged files to git</mark>

```powershell
git commit m "<your_commit_message>"
```

<mark>#Restore the file from being modified to Tracked</mark>

```powershell
git restore <fileName>
```

```powershell
git checkout <fileName>
```

<mark>#Show the status of your Git Respossitory</mark>

```powershell
git status
```

#<mark>Show the branches of your Git Repository</mark>

```powershell
git branch
```

<mark>#Checkout to a new branch</mark>

```powershell
git checkout -b <branch_Name>
```

<mark>#Checkout to an existing branch</mark>

```powershell
git checkout <branch_name>
```

<mark>#Remove a branch from Git</mark>

```powershell
git branch -d <branch_Name>
```

<mark>#Show remote origin URL</mark>

```powershell
git remote -v
```

<mark>#Add remote&nbsp;origin&nbsp;URL</mark>

```powershell
git remote add origin <your_remote_git_url>
```

<mark>#Remove remote origin URL</mark>

```powershell
git remote remove origin
```

#Fetch all the remote branches

```powershell
git fetch
```

#Push your local changes to the remote branch

```powershell
git push origin <branch_Name>
```

#Pull your remote changes to the local branch

```powershell
git pull origin <branch_Name>
```

#Check your git commands and logs

```powershell
git log
```

## Git Branch:-

Knowing the right Git command for the task at hand can often be challenging. Especially when you're adding complexity to your task, like with Git branching.

As we know Git is a powerful version control system that enables you to track changes to your codebase. One of the key features of Git is its ability to manage branches.

Branches allow developers to work on different features, issues, or bug fixes without affecting the project's main codebase.

In this we learn how to do set of Git commands for creating, committing, merging, and deleting branches.

### For show all branches that we had created:

```powershell
git branch
```

### For creating new branch we use command:

```powershell
git branch <branch_Name>
```

### If you want to go on specific branch the use this command:

```powershell
git checkout <branch_Name>
```

### For deleting any branch:

```powershell
git branch -d <branch_Name>
```

### Merging:

* We can't merge branches of different Repositories.
    
* We use the pulling Mechanism to merge branches.
    

### why we need git merging:

If you and your friend are working on some project and that project is quite complex and you can not take risk on particular branch then you create new branch and do there whatever you do in that project and in your main branch will be remain same.

### for merging the branch:

```powershell
git merge <branch_Name>
```

Here we discuss till the Git merge , In git there are some more concepts regarding the VCS (Version Control System) we will discuss that in next blog.....

If you like this then please like and comment on this ...