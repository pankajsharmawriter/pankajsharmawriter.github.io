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

## 4. Add files and folders
New files aren't tracked until you add them. **Add** puts a file or folder under version control.

To add a file to SVN, follow these steps:
1. Create or copy the file into your working copy, for example `C:\Docs\product-guide\install.md`. The file shows a blue question mark overlay icon.
1. Right-click the file.
1. Select **Show more options > TortoiseSVN > Add**.
1. In the **Add** dialog, confirm that the file is selected, and then select **OK**.
1. Confirm that the overlay icon changes to a blue plus sign.

At this point, the file exists only on your computer. To send it to the repository, you must commit it (see the next section).

To add several files at once, right-click the parent folder and select **Add**. Then clear the check boxes for files you don't want to track.

## 5. Commit your changes
Commit sends your local changes to the repository and creates a new revision.
To commit your changes, follow these steps:
1. Update your working copy first.
1. Right-click the working copy folder, and then select **Show more options > SVN Commit**.
1. In the **Message** box, describe what you changed and why.
1. In the file list, make sure only the files you intend to commit are selected. Added files must be selected to be included.
1. Select **OK**.
1. If prompted, enter your credentials. When the commit finishes, TortoiseSVN shows the new revision number.

Write clear commit messages. A good message helps other writers, and your future self, understand the change without opening the file.

## 6. Compare versions with Diff
*Diff* shows the differences between two versions of a file, line by line. TortoiseSVN opens TortoiseMerge, which highlights added, removed, and changed lines.

To see what you changed before you commit, follow these steps:
1. Right-click the changed file.
1. Select **Show more options > TortoiseSVN > Diff**.
1. In TortoiseMerge, review the highlighted differences. The left pane shows the repository version. The right pane shows your version.

To compare two earlier revisions, open the revision log (see the next section), select two revisions, right-click, and then select Compare revisions.

## 7. View the revision log
The *revision log* lists every commit to a file or folder, including the revision number, author, date, and commit message.
To view the revision log, follow these steps:
1. Right-click a file or folder.
1. Select **Show more options > TortoiseSVN > Show log**.
1. In the top pane, select a revision to see its message and changed files in the lower panes.
1. To search, use the filter box at the top of the dialog. You can filter by message, author, or file path.
1. To see what changed in a revision, double-click the file name in the lower pane.

> You can also use the log to get an earlier version of a file. Right-click the revision, and then select **Save revision** to or **Revert to this revision**. 

## 8. Resolve conflicts
A conflict occurs when you and another person change the same lines of a file, and Subversion can't merge the changes automatically.
To resolve a conflict, follow these steps:
1. Right-click the conflicted file.
1. Select **Show more options > TortoiseSVN > Edit conflicts**.
1. In TortoiseMerge, review the three panes:
    - **Theirs** shows the version from the repository.
    - **Mine** shows your version.
    - **Merged** shows the result.
1. Right-click each conflicting block, and then choose to use the text from theirs, use the text from mine, or use both. You can also edit the merged text directly.
1. Save the file, and then close TortoiseMerge.
1. When prompted, select **Mark as resolved**.
1. Commit the file.
> **Tip** To reduce conflicts, update often, commit small changes, and agree with your team on who edits which topic.

## 9. Revert changes
*Revert* discards your local changes and restores the file to the last version you got from the repository.

To revert a file, follow these steps:
1. Right-click the file.
1. Select **Show more options > TortoiseSVN > Revert**.
1. In the **Revert** dialog, confirm that the correct files are selected, and then select **OK**.

> **Warning** Revert permanently discards your uncommitted changes. You can't undo this action.
Revert affects only your working copy. To undo a change that's already committed, open the revision log, right-click the revision, and then select **Revert changes from this revision**. Then commit the result as a new revision.

## 10. Rename, move, and delete files
If you rename, move, or delete files in File Explorer, Subversion doesn't know that the files are related. You lose the file history. Use the TortoiseSVN commands instead, so history stays connected.

**To rename a file**, follow these steps:
1. Right-click the file.
1. Select **Show more options > TortoiseSVN > Rename**.
1. Enter the new name, and then select **OK**.

**To move a file**, follow these steps:
1. Right-click the file, and then drag it to the destination folder.
1. Release the mouse button, and then select **SVN Move versioned item(s) here**.

**To delete a file**, follow these steps:
1. Right-click the file.
1. Select **Show more options > TortoiseSVN > Delete**.

After any of these actions, commit the change. Until you commit, the change exists only in your working copy.

## Conclusion
This article introduced TortoiseSVN, from downloading and installing it on Windows 11 to using the 10 features that technical writers rely on every day. By following these steps, new technical writers can understand TortoiseSVN from the basics to more advanced tasks, such as comparing versions and resolving conflicts. With this knowledge, you can check out, edit, review, and commit your documentation and work independently in SVN. As you practice, you’ll spend less time managing files and more time creating clear, accurate content.

For any query, contact me at **pankajsharmawriter@gmail.com**.

## Reference

-  [About me](./)