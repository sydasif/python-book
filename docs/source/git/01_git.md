# Working with Git & Basic

## Fundamentals of Git

Git has maintained a file system also known as git structures or trees as below:

- Working directory / local workspace

Starting with the working area, the working area is where the files that are not handled by git, it is the place where all the untracked files are kept.

- Staging area/index

A staging area has files that are added by the git add command, going to be part of the next commit.

- Local repository

The repository contains all the projects and stores all committed items.

- Remote repository

The remote repository contains your copy of the local repo on a server.

## Staging and Committing

Files in Git follow a life cycle as below:

1. Untracked: When you first create a file, Git sees this file but does not perform any operations on it.
2. Staged: when you add a file in Git to track.
3. Unmodified: When a file is committed.
4. Modified: when you made a change in an unmodified file.

## Configuring Git

To start working with Git you need to specify the user name and e-mail that will be used to synchronize the local repository with your GitHub repository:

```console
[$] <> ~
$ git config --global user.name “userName”
$ git config --global user.email “userEmail@gmail.com”
```

## Initializing Repository

There are two ways to initialize a repository:

- The first one is to clone an existing repository from a server to your local machine.
- The second is to create a new repository on your machine locally.

### git init

It initializes an empty repository as a git repository on your local machine.

As shown below, We've created an empty folder - `my-repo` and run the `git init` command to mark it as a git repository or use `git init my-repo` will create a directory and also initialize a repository.

```console
[$] <> ~/my-repo 
$ git init
Initialized empty Git repository in ~/my-repo/.git/
```

Let's add an empty file `script.py` in this local git folder `my-repo`.

```console
[$] <> ~/my-repo (main)
$ ls
script.py
```

### git status

git status will show a list of all files along with their status. Newly added files will be "untracked" by git initially. It is the most frequent command we will use to see file status.

As shown below in the untracked file list we can see "script.py"

```console
[$] <> ~/my-repo (main)
$ git status 
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        script.py

nothing added to commit but untracked files present (use "git add" to track)
```

### git add

Out of all the untracked files, we can pick which file we want to commit. This is called staging. Use the `git add <fileName>` Command to stage a file:

Below we've added `script.py` to the stage and then used git status to check its status.

```console
[$] <> ~/my-repo (main)
$ git add script.py 

[$] <> ~/my-repo (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   script.py
```

### git commit

After all necessary files have been added to a staging area, you can commit changes. Staging is a collection of files that will be added to the next commit. To commit the file to our local repository using  `git commit -m "commit message"`

Below we've committed the `script.py` file with a commit message. Then we used git status to see if our commit is successful or not.

```console
[$] <> ~/my-repo (main)
$ git commit -m "first commit"
[main (root-commit) 2664303] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 script.py
```

So far, we've committed the above file to our local repository only. Now it's time to push this file to the remote repo.

## Synchronizing local repository with GitHub

As we have created a repo on GitHub in the {ref}`Pre-requisite` section. Now it's time to use it, get the link to your remote branch ready.

### git remote

Before sending our code to a remote repository, we need to map our local repo with equivalent remote repo by using the below command as shown below:

```console
[$] <> ~/my-repo (main)
$ git remote add origin git@github.com:sydasif/my-repo.git
```

### git push

At last, using the below push command we can send our file to the remote repo as shown below:

```console
[$] <> ~/my-repo (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 210 bytes | 105.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:sydasif/my-repo.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

## Cloning a GitHub repository

To work locally or if Someone else wants to take your changes, add their changes on top of it and push those changes on the remote git repo we have to clone the repo.

### git clone

When you want to use a remote repo for the first time, you need to clone it first using the below command.

We've cloned our previously created repository for the first time.

```console
[$] ~/Desktop
$ git clone https://github.com/sydasif/my-repo.git
Cloning into 'my-repo'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Receiving objects: 100% (6/6), done.
```

### git fetch

The below "git fetch" command retrieves the latest meta-data from the remote repo and updates the same in the local repo.

```console
[$] <> ~
$ git fetch origin
```

It doesn’t do any file transferring. It just checks if there are any changes available or not.

```{Note}
In the current case, it's optional to do `git fetch` because the git clone will automatically update all metadata. But for later usage fetch will be very useful.
```

## Git Branch

### git checkout

It helps to create a branch, a branch is your own copy of the remote repo where you will apply your changes and later push your changes to the remote repository.

`git checkout -b <branch-name>`

```console
[$] <> ~/Desktop/my-repo (main)
$ git checkout -b first-branch
Switched to a new branch 'first-branch'

[$] <> ~/Desktop/my-repo (first-branch)
$
```

### git diff

We can check the changes made by us, using the below command:

`git diff <file-name>`

We've modified `script.py` in the new branch. Newly added lines will be shown with the `"+"` prefix and removed lines will be shown with the `"-"` prefix.

```console
[$] <> ~/Desktop/my-repo (first-branch)
$ git diff
warning: in the working copy of 'script.py', LF will be replaced by CRLF the next time Git touches it
diff --git a/script.py b/script.py
index e69de29..7df869a 100644
--- a/script.py
+++ b/script.py
@@ -0,0 +1 @@
+print("Hello, World!")
```

Now, using the following sequence of commands we can send our modified file to the remote repo:

```console
[$] <> ~/Desktop/my-repo (first-branch)
$ git add script.py 
warning: in the working copy of 'script.py', LF will be replaced by CRLF the next time Git touches it
```

```console
[$] <> ~/Desktop/my-repo (first-branch)
$ git commit -m "add code"
[first-branch 8245dcc] add code
 1 file changed, 1 insertion(+)
```

```console
[$] <> ~/Desktop/my-repo (first-branch)
$ git push origin first-branch
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 295 bytes | 295.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'first-branch' on GitHub by visiting:
remote:      https://github.com/sydasif/my-repo/pull/new/first-branch
remote:
To https://github.com/sydasif/my-repo.git
 * [new branch]      first-branch -> first-branch
```

After this, our code will be added to the respective remote branch.

### git pull

Many times you are working on the same file on which someone else is also working.

In such a case, we need to get the latest copy of the same file before pushing our copy. Add our changes to it and then push, to avoid any conflicts.

```console
[$] <> ~/Desktop/my-repo (first-branch)
$ git pull origin first-branch
From https://github.com/sydasif/my-repo
 * branch            first-branch -> FETCH_HEAD
Already up to date.
```

## Pull Request

In such a case, you need to raise a PR, go through the code review process and then merge your changes on the destination branch.

To Create PR:

[Creating a pull request](https://docs.github.com/en/enterprise-cloud@latest/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

After Review Merge PR:

[Merging a pull request](https://docs.github.com/en/enterprise-cloud@latest/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)

## Additional Features

### `.gitignore` file

Git has the option to specify which file or directories to ignore. To do this, you need to create appropriate templates in the .gitignore file in the repository directory. To make Git ignore, you can add such a file name to `.gitignore` file.

### Repo history

- The git log command shows a history of the repository in descending order.
- The git log command displays a brief description of a repository it includes the change, date and time, who made the changes, commit message and commit identifier (hash value).
- You can tidy this history with the git log –oneline command, which shows a clean-cut history.

There are many ways to see commit history:

The most basic one, shows all the commits from end to start, with all the info related to commits.

```console
[$] <> ~
$ git log
```

Last five commits

```console
[$] <> ~
$ git log -5
```

To see the stat of the commits:

```console
git log --stat
```

## Check out and Detach Head

Git checkout changes your working directory to match a specific commit and your git’s head is in a detached head state, the Git repository is reverted and your work is temporarily lost means going back to the past.

The commands below are used:

```console
[$] <> ~
$ git checkout <first 7-bits of commit>
$ git checkout master
```

## GitHub Authentication

### With SSH

In order to start working with GitHub, you need to register on it. It is better to use SSH key authentication to work safely with GitHub.

Generation of a new SSH key (use an e-mail that is linked to GitHub):

`ssh-keygen` on all questions, just press enter.

### Add SSH key to GitHub

To add a key you have to copy it. For example, you can display a key with a `cat` command to copy it:

```console
cat ~/.ssh/id_rsa.pub
```

After copying, go to GitHub, in the upper right-hand corner click on the picture of your pro-ﬁle and select `Settings` in the drop-down list. In the list on the left, select `SSH and GPG keys`. Then press `New SSH key` and in, the `Title` field write the key name (for example “my_laptop”) and in the field `Key` insert the content that was copied from file `~/. ssh/id_rsa.pub`.

To check if everything is working successfully, try executing the command `ssh -T git@Github.com`.

The output should be as follows:

```console
ssh -T git@github.com
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

### With Token

Open your browser and go to your GitHub account and generate the token as below:

`Settings` -->> `Developer settings` -->> `Personal access tokens` -->> `Generate new token` -->> `Add note` -->> `Set Expiration` -->> `Add Scope and generate token`.

Add a token to your configuration with the below command:

```console
git config credential.helper store
```

or store globally in Git configuration

```console
git config --global credential.helper store
```

Copy your token to notepad and use it for authentication on GitHub.

## Some Useful Commands

```console
[$] git config --list             # check git setting
[$] git config --global --list    # check global setting
[$] git show                      # to check the details of a commit
[$] git rm                        # delete a tracked file
[$] git mv                        # rename a tracked file
[$] git diff --staged             # diff between staging and last commit
[$] git merge <branch name>       # merge branch
[$] git branch -d <branch name>   # delete branch
[$] git branch                    # list all branches
[$] git branch -a                 # list all branches
```
