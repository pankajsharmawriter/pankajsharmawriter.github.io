---
title: End-to-end GitHub workflow for Technical Writers
layout: default
---


# End-to-end GitHub workflow for Technical Writers

In this article, I am explaining the end-to-end documentation contribution workflow that I followed as a Technical Writer at Microsoft. This workflow covers every step, from receiving a task assignment via email to getting your changes reviewed and merged into the main branch on GitHub. I walk you through cloning a repository, working on a feature branch, editing documentation files in VS Code, committing and pushing your changes, and finally creating a Pull Request (PR) for your manager to review and approve. Whether you are a new technical writer joining a docs-as-code team or an experienced writer looking to standardize your process, this article gives you a clear, repeatable workflow grounded in real-world practice. The tools covered include Git, GitHub, GitHub Desktop, and Visual Studio Code (VS Code), all of which are industry-standard in modern documentation environments.

## Step 1: receiving the task assignment via email

Every documentation task at Microsoft began with an email from my manager. This email was not just a notification — it was the official task handoff. The email typically contained:
- A brief description of the documentation work to be done (new article, update, review, etc.)
- The link to the specific branch on GitHub that I needed to work on
- Any additional context, style guidelines, or deadline information
- References to any related tickets or project trackers such as Azure DevOps
  
This email-based task assignment ensured that all work was traceable, communication was documented, and I always had the exact branch reference before touching any code or content. It also helped avoid confusion in multi-writer teams where several branches might be active simultaneously.

## Step 2: cloning the repository via GitHub

Once I had the branch link from my manager's email, the next step was to clone the repository to my local machine. Cloning creates a local copy of the remote repository so you can work on the files offline. GitHub makes this straightforward through its web interface without needing any command-line knowledge.

### Cloning via the GitHub web interface

To clone the repository using the GitHub website:

1. Open your browser and go to the repository. For reference, my portfolio repository is at: [https://github.com/pankajsharmawriter/pankajsharmawriter.github.io/](https://github.com/pankajsharmawriter/pankajsharmawriter.github.io/)
1. Click the **green Code button** near the top right of the repository page.
1. In the dropdown that appears, click **Open with GitHub Desktop**.
1. Your browser will prompt you to open GitHub Desktop. Click the **confirmation button** to proceed.
1. GitHub Desktop launches and displays a Clone a Repository dialog with the repository URL and the local path where the files will be saved on your machine.
1. Confirm or change the local path as needed, then click **Clone**.
1. GitHub Desktop downloads the repository to your machine and opens it automatically.

### Switching to the assigned branch in GitHub Desktop

After cloning, GitHub Desktop opens the repository on the default branch. Since my manager assigned a specific feature branch, I needed to switch to it before making any edits.
1. In GitHub Desktop, click the **Current Branch** dropdown at the top of the window.
1. A list of all available branches appears. Locate the branch name shared by your manager in the email.
1. Click the branch name to switch to it.
1. GitHub Desktop updates the working files to reflect the selected branch.

Once the correct branch is active, GitHub Desktop displays the current branch name prominently in the toolbar, confirming that any edits you make will be tracked against that branch and not the main branch.

## Step 3: editing articles in Visual Studio Code

With the branch open in GitHub Desktop, the next step was to edit the documentation files. At Microsoft, most documentation was written in Markdown (.md) and managed within a docs-as-code framework. VS Code was the standard editor for this purpose.

### Opening the repository in VS Code

From GitHub Desktop, opening VS Code is straightforward:
1. In GitHub Desktop, click **Repository** in the top menu.
1. Select **Open in Visual Studio Code**.
1. VS Code opens the entire repository as a workspace.

### Working on documentation files

In VS Code, I navigated the file tree on the left panel to locate the article I needed to edit. Documentation files were typically Markdown files organized in folders by product area or content type. During editing, I focused on several areas:
- **Accuracy**: verifying technical details against the product specifications or engineering notes provided.
- **Style compliance**: applying Microsoft Writing Style Guide conventions, including active voice, sentence-style capitalization, and second-person tone.
- **Formatting**: ensuring proper use of Markdown syntax for headings, code blocks, tables, numbered lists, and notes.
- **Consistency**: maintaining terminology consistency with related articles in the same product area.
- **Link validation**: checking that all internal cross-references and external links were active and correctly targeted.


VS Code's built-in Markdown preview (Ctrl+Shift+V) allowed me to see a rendered version of the document while editing, which made it easier to catch formatting errors before committing changes.



