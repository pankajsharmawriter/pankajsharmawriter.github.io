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