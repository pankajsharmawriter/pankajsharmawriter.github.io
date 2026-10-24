---
title: Top 10 uses of Tortoise SVN
layout: default
---
# Top 10 uses of Tortoise SVN
If you write documentation for a team, you've probably been asked to "check your files into SVN." This article shows you how to install TortoiseSVN on Windows 11 and how to use the 10 features that technical writers rely on every day.

## Introduction
TortoiseSVN is a free, open-source Subversion (SVN) client for Windows. It adds version control commands to File Explorer, so you can manage files by right-clicking them instead of typing commands in a terminal.

## What is version control?
Version control tracks every change you make to a file. It records who made the change, when they made it, and why. If you make a mistake, you can compare versions or return to an earlier one.
## How TortoiseSVN works
Subversion stores your files in a central location called a repository. You don't edit files in the repository directly. Instead, you work in a working copy, which is a local copy of the repository on your computer. When you finish your edits, you send them back to the repository.

TortoiseSVN doesn't replace Subversion. It provides a graphical interface for it.

## Why technical writers use TortoiseSVN
As a technical writer, you can use TortoiseSVN to:

- Keep a history of every edit to your documentation.
- Work on the same documentation set as other writers, engineers, and reviewers without overwriting each other's work.
- Review exactly what changed between two versions of a topic.
- Recover a file you deleted or changed by mistake.

## Terms used in this article

| Term | Definition |
| --- | --- |
| Repository | The central location where Subversion stores all files and their history. |
| Working copy | The local copy of the repository on your computer. |
| Revision | A numbered snapshot of the repository, created each time someone commits changes. |
| Commit | The action of sending your local changes to the repository. |
| Update | The action of getting the latest changes from the repository. |

## Download TortoiseSVN
To download TortoiseSVN, follow these steps:
1. Go to the official TortoiseSVN website:[https://tortoisesvn.net/downloads.html](https://tortoisesvn.net/downloads.html).
1. Under Download, find the latest stable release.
1. Select the installer for your system. For Windows 11, select the 64-bit installer. The file name looks like `TortoiseSVN-1.14.x.xxxxx-x64-svn-1.14.x.msi`.
1. (Optional) Select a language pack if you want the interface in a language other than English. You install the language pack after you install TortoiseSVN.

> **Important** Download TortoiseSVN only from the official website. Installers from third-party sites might be outdated or modified.

### System requirements
- Windows 11 (64-bit). TortoiseSVN also runs on Windows 10 and earlier supported versions.
- Administrator rights on your computer to run the installer.
- Network access to your team's SVN repository.

## Install TortoiseSVN on Windows 11
To install TortoiseSVN, follow these steps:
1. Open the folder where you saved the `.msi` file, and then double-click it.
1. On the Welcome page, select **Next**.
1. Read the license agreement, select **I accept the terms in the License Agreement**, and then select **Next**.
1. On the **Custom Setup** page, review the features. To use svn commands in a terminal, select **command line client tools**, and then select **Will be installed on local hard drive**. This feature isn't selected by default.
1. Select **Next**, and then select **Install**.
1. If the **User Account Control** dialog appears, select **Yes**.
1. When the installation finishes, select **Finish**.
1. Restart your computer if the installer prompts you to. Overlay icons and context menu commands don't appear until you restart.

### Verify the installation
To verify that TortoiseSVN is installed, follow these steps:
1. Open File Explorer, and then right-click any empty space in a folder.
1. In Windows 11, select **Show more options**. Depending on your TortoiseSVN version, you might also see a TortoiseSVN entry directly in the shortened menu.
1. Confirm that the classic context menu includes SVN Checkout and TortoiseSVN.

## Top 10 uses of TortoiseSVN for Technical Writers
The following sections follow the order of a typical writing day: set up your files, see what's changed, edit, review, and submit.

### 1. Check out a repository

Check out means to create a working copy of a repository on your computer. You do this once for each documentation set.
To check out a repository, follow these steps:
1. In File Explorer, create an empty folder, for example `C:\Docs\product-guide`.
1. Right-click the folder, and then select **Show more options > SVN Checkout**.
1. In **URL of repository**, enter the repository URL that your team provided, for example `https://svn.example.com/repos/docs/trunk`.
1. Confirm that **Checkout directory** shows the folder you created.
1. Leave **Revision** set to **HEAD revision** to get the latest version.
1. Select **OK**. If prompted, enter your user name and password.

When the checkout finishes, your folder contains the documentation files and a hidden `.svn` folder. Don't edit or delete the `.svn` folder. Subversion uses it to track your changes.

## 2. Read overlay icons
Overlay icons are small symbols that appear on top of files and folders. They show you the status of each item at a glance.

| Icon | Meaning |
| --- | --- |
| Green check mark | The file is up to date. It matches the repository. |
| Red exclamation mark | You changed the file, or the folder contains changed files. |
| Yellow triangle | A conflict exists. You must resolve it before you commit. |
| Blue plus sign | You added the file, but you haven't committed it yet. |
| Blue question mark | The file isn't under version control. |

> If the icons don't appear, restart your computer.

## 3. Update your working copy
Update gets the latest changes from the repository and merges them into your working copy.
To update your working copy, follow these steps:
1. Right-click your working copy folder.
1. Select **Show more options > SVN Update**.
1. Review the list of changed files in the dialog.
1. Select **OK**.

Updating first reduces the chance of conflicts, because you start from the same version as everyone else. Developers often change code and related documentation, so an update shows you what changed in the product since your last session.