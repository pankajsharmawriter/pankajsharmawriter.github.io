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
