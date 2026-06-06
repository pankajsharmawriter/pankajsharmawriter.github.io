---
title: Learn Git commands for Technical Writers
layout: default
---

# Git commands commonly used by technical writers in VS Code

In this article, I am explaining the Git commands that technical writers use most frequently when working on Markdown documentation in Visual Studio Code (VS Code). This article is intended for technical writers who are already familiar with the basics of Markdown and GitHub workflows and want to move beyond GitHub Desktop into using Git directly from the VS Code terminal. Each command is explained with its purpose, syntax, and a real-world example grounded in a documentation workflow.

## Why technical writers need Git commands

GitHub Desktop handles most everyday Git operations through a visual interface. However, there are situations where using Git commands directly in the terminal is faster, more precise, or simply unavoidable — for example, when working in a CI/CD pipeline, resolving a merge conflict from the command line, or following a team workflow that is terminal-based.
Understanding Git commands also makes you a more credible collaborator in engineering environments, where developers work exclusively in the terminal and expect documentation contributors to do the same.

## Open the terminal in VS Code

All Git commands in this article are run from the integrated terminal inside VS Code. To open it:

1. Open VS Code.
1. Press Ctrl + `(backtick) on Windows.
1. The terminal opens at the bottom of the VS Code window, with the working directory set to your current project folder.

Verify that Git is installed by running the following command:

``` cmd

git --version
```

**Expected output**:
``` cmd
git version 2.44.0
```

**Note**: If Git is not installed, download it from [https://git-scm.com](https://git-scm.com) and follow the installation instructions for your operating system.

## Set up your Git identity

Before using Git for the first time, configure your name and email address. Git attaches this information to every commit you make, so reviewers can see who made each change.

``` cmd
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Example**:
``` cmd
git config --global user.name "Pankaj Sharma"
git config --global user.email "pankajsharmawriter@gmail.com"
```
You only need to run this once. To verify your configuration, run:

``` cmd
git config --list
```
This displays all your current Git settings, including your name and email.

## Clone a repository

Cloning creates a local copy of a remote GitHub repository on your machine. This is the first step when you are assigned a documentation task that lives in an existing repository.

``` cmd
git clone <repository-url>
```

**Example**:
``` cmd
git clone https://github.com/pankajsharmawriter/pankajsharmawriter.github.io.git
```

After running this command, Git downloads the repository into a new folder in your current directory. Navigate into it with:

``` cmd
cd pankajsharmawriter.github.io
``` 

You are now inside the repository and ready to work.

## Check the status of your working directory

The `git status` command is the most frequently used command in a documentation workflow. It shows you which files have been modified, which are staged for commit, and which are untracked.

``` cmd
git status
```
**Example**:

``` cmd
On branch feature/update-api-guide
Changes not staged for commit:
  modified:   docs/api-guide.md

Untracked files:
  docs/new-article.md
  ```
Run `git status` before committing, after making changes, and whenever you are unsure about the state of your working directory. It is a safe, read-only command — it never changes anything.

## View existing branches

Before creating a new branch or switching to one, check which branches already exist in the repository.

``` cmd
git branch
```

This lists all local branches. The branch you are currently on is marked with an asterisk (*).

To see both local and remote branches, run:

``` cmd
git branch -a
```

**Example**:

``` cmd
* main
  remotes/origin/feature/update-api-guide
  remotes/origin/feature/release-notes-v3

```
## Create and switch to a new branch

In a docs-as-code workflow, you always work on a separate feature branch — never directly on the main branch. This isolates your changes from the stable, published content until they are reviewed and approved.
To create a new branch and switch to it in a single command:

``` cmd
git checkout -b <branch-name>
```
**Example**:

``` cmd
git checkout -b feature/update-onboarding-guide
```

Use a descriptive branch name that reflects the documentation task. This makes it easier for your manager or reviewer to identify your branch when reviewing pull requests.
To switch to an existing branch without creating a new one:

``` cmd
git checkout <branch-name>
```

**Example**:

``` cmd
git checkout feature/update-api-guide
```
## Pull the latest changes

Before starting work each day, pull the latest changes from the remote repository. This ensures your local branch is in sync with any updates that teammates have pushed since your last session.

``` cmd
git pull origin main
```
Running `git pull` regularly reduces the chance of merge conflicts by keeping your local copy up to date with the remote repository.

## Stage files for a commit

After editing your Markdown files, you need to stage the changes before committing them. Staging lets you choose exactly which changes to include in a commit, rather than committing everything at once.
To stage a specific file:

``` cmd
git add docs/api-guide.md
```

To stage all modified files in the repository at once:

``` cmd
git add .
```
Run `git status` after staging to confirm which files are queued for the commit.