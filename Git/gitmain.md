# Git Notes

> Git is like a magical notebook for your computer files. Imagine you have a magical notebook that keeps track of all the changes you make to your homework. Whenever you add something new or make changes, the notebook takes a snapshot of how everything looks at that moment. If you ever want to go back to a previous version, you can simply ask the notebook to show you how things looked in the past. Git does the same thing, but for computer files instead of homework.

In other words, Git is an open-source distributed version control system - [What's a distributed version control system?](#version-control-systems) - for managing source code and files in software development projects. It allows you to track changes, collaborate with others, and maintain a history of revisions. Git operates locally, enabling offline work and fast operations. You initialize a repository, make changes to files, stage and commit those changes, and create snapshots of different versions. Git supports branching for parallel development and provides tools for collaboration, code reviews, and integration with CI/CD pipelines. Its flexibility and command-line interface make it widely used in software projects.

Collaboration is a fundamental aspect of Git. You can clone a remote repository (eg. from Github) to your local machine, work on it, and then push your changes back to the remote repository. Git ensures that concurrent changes from multiple developers can be integrated smoothly, resolving conflicts when necessary.

## [Sources and Further Reading](#sources)

## [Back to main](../main.md)

---

## Table of Contents

- [Git Bash](#git-bash)
- [Simple Steps](#simple-steps)
- [Basic Commands](#basic-commands)
- [Advanced Commands](#advanced-commands)
- [Version Control Systems](#version-control-systems)

---

### Git Bash

You don't *need* to use Git Bash. It is just conventional, because Git was developed and designed on Linux and most Git users use Linux and using Git Bash on Windows makes it a uniform experience.

For more information go to the bash notes [here](../Bash/bashmain.md)

---

### Simple Steps

Git can be a bit confusing at first, but once you get the hang of it you will realize how powerful it can be.

Before we start using Git we have to install it on our computer. Git is available for Windows, macOS, and Linux. You can download it from the official [Git website](https://git-scm.com/).

Once we have done that, we need to set up our identity. This is how Git will know who you are, and will associate you with your Git commits. Open a terminal or command prompt and configure your identity using the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

Replace "Your Name" with your actual name and `"youremail@example.com"` with your email address.

Next up we will initialize a repository. Navigate to the directory or project folder where you want to start using Git. Use the `git init` command to initialize a new Git repository in that directory:

```bash
git init
```

The local repository consists of three "trees" maintained by git. The first one is your "Working Directory" which holds the actual files. The second one is the "Index" which acts as a staging area and finally the "HEAD" which points to the last commit you've made.

After initializing the repository we can add files we want to track to the staging area using the following command:

```bash
git add file.extension
```

You can specify individual files or use `git add *` to add all files in the current directory. Then after adding the files we want to track, we can commit the changes to create a snapshot of the current state.

```bash
git commit -m "Commit message".
```

If you want to work with a remote repository, you can either create your own repository on a platform like GitHub, or clone an existing repository. Cloning creates a local copy of the remote repository on your machine.

```bash
git clone repository_URL
```

We can also send committed changes, fetch and merge changes from the remote repository to your local copy.

```bash
# Sending to the remote repository. Change master to whatever branch you want to push your changes to.
git push origin master
# Fetching from the remote repository
git pull
```

If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it with:

```bash
git remote add origin <server>
```

As you become more comfortable with the basics, explore and practice more Git commands like branching, merging, resolving conflicts, and collaborating with others. Remember to refer to Git documentation, or Git resources for more detailed explanations and examples as you progress.

---

### Basic Commands

`git init`
: Initializes a new Git repository in the current directory.

`git clone [repository]`
: Creates a local copy of a remote repository on your machine.

`git add [file]`
: Adds a file or changes to the staging area, preparing it for a commit.

`git commit -m "message"`
: Commits the changes in the staging area to the repository with a descriptive message.

`git status`
: Shows the current status of the repository, including any modified, staged, or untracked files.

`git pull`
: Fetches changes from a remote repository and merges them into the current branch.

`git push`
: Sends committed changes to a remote repository.

`git branch`
: Lists all the branches in the repository.

`git checkout [branch]`
: Switches to a different branch.

`git merge [branch]`
: Merges changes from one branch into the current branch.

`git log`
: Displays a history of commits in the repository.

---

### Advanced Commands

`git reset`
: Allows you to unstage changes, move the HEAD pointer, or even discard commits.

`git rebase`
: Modifies the commit history by applying changes from one branch onto another.

`git cherry`-pick
: Selects specific commits from one branch and applies them to another branch.

`git stash`
: Temporarily saves changes that are not ready to be committed, allowing you to switch branches without losing work.

`git bisect`
: Helps you find the specific commit that introduced a bug by performing a binary search through the commit history.

`git remote`
: Manages connections to remote repositories, including adding, renaming, or removing remotes.

`git submodule`
: Incorporates external repositories as subdirectories within a Git repository.

`git reflog`
: Displays a log of all reference changes, such as commits or branch updates, even those that are no longer
reachable.

`git filter-branch`
: Rewrites the commit history by applying custom filters to files or specific commits.

`git blame`
: Shows who last modified each line of a file, helping to identify the author of specific changes.

---

### Version Control Systems

---

## Sources

[Simple Git Guide](https://rogerdudler.github.io/git-guide/)

[Git Documentation](https://git-scm.com/)
