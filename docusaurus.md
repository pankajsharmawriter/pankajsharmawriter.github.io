---

title: How to set up Docusaurus in a Docs-as-Code environment
layout: default
---


# How to set up Docusaurus in a Docs-as-Code environment

In this article, I am explaining how to set up Docusaurus as your static site generator in a Docs-as-Code environment. You will learn what Docusaurus is, how to install it on your computer, how to connect it to GitHub Desktop for version control, and how to write and organize your documentation using Markdown in Visual Studio Code.
If you have never set up a documentation website before, this article walks you through every step — from installing the required software to seeing your first page live in a browser. Every instruction is written with technical writers in mind, not developers. You do not need to know programming to follow this guide.
By the end of this article, you will have a fully working Docusaurus documentation site running on your computer, connected to a GitHub repository, and ready for you to write and publish documentation.

## What Is Docs-as-Code?

Before diving into Docusaurus, it helps to understand what Docs-as-Code means, because it shapes everything about how you will work.
Docs-as-Code is an approach to writing documentation where you treat your content the same way software developers treat their code. Instead of writing in a word processor like Microsoft Word, you write in plain text files using Markdown. Instead of emailing files to reviewers, you use version control (GitHub) to track every change, collaborate with others, and publish updates.
In a Docs-as-Code workflow, your standard toolkit looks like this:

| Tool | Purpose |
| --- | --- |
| Visual Studio Code | Your writing and editing environment |
| Markdown | The format you write content in |
| GitHub Desktop | Version control — saving and tracking changes |
| Docusaurus | Converts your Markdown files into a documentation website |

## What Is Docusaurus

Docusaurus is a free, open-source tool that converts your Markdown files into a fully functional documentation website. You write content in plain `.md` files, and Docusaurus handles all the HTML, CSS, navigation, search, and layout automatically.
It was originally built by Meta (the company behind Facebook) to manage their own large-scale open-source documentation. Today, it is used by thousands of organizations worldwide — including companies like Algolia, Supabase, and React — to publish technical documentation.

### Why Docusaurus is built for Technical Writers

Docusaurus is not a blogging platform and it is not a generic website builder. It is specifically designed for documentation. Out of the box, it gives you:
- **Structured navigation**: Your docs automatically appear in a sidebar, organized by folder structure. You do not build menus manually.
- **Versioning**: If you document software that has multiple releases (v1.0, v2.0), Docusaurus lets you maintain separate documentation for each version without duplicating your work.
- **Built-in search**: Readers can search across your entire documentation site without any extra setup.
- **Dark mode**: Every Docusaurus site supports light and dark mode by default, with no extra configuration.
- **MDX support**: You can embed interactive elements inside your Markdown files if you ever need to — though for most technical writers, standard Markdown is all you will ever need.
- **Fast local preview**: You can see your documentation in a browser on your computer as you write, before publishing anything. Every time you save a file, the browser updates automatically.

### Docusaurus is free

Docusaurus is licensed under the MIT License, which means it is completely free to use for any purpose — personal projects, employer documentation, portfolio sites, or commercial use. There is no trial period, no license fee, and no paid tier.
When you pair it with GitHub (free for public repositories) and GitHub Pages (free static site hosting), your entire documentation pipeline costs nothing.

## What you need before you start

This section covers every piece of software you need to install before setting up Docusaurus. Install them in the order listed.

1. **Node.js**

    Docusaurus runs on Node.js, a software platform that lets you run JavaScript-based tools on your computer. You do not need to know JavaScript — Node.js simply powers the engine that Docusaurus uses behind the scenes.

    **To install Node.js**:
    1. Open your browser and go to https://nodejs.org.
    1. You will see two download options on the homepage. Click the one labeled LTS (Long-Term Support). This is the stable version recommended for most users.
    1. Download the installer for your operating system (Windows or macOS).
    1. Run the installer and follow the on-screen prompts. Accept all default settings.

    **To verify the installation worked**:

    After installation, open the Command Prompt (Windows) or Terminal (macOS):

    - **Windows**: Press `Windows key + R`, type `cmd`, and press **Enter**.
    - **macOS**: Press `Command + Space`, type `Terminal`, and press **Enter**.

    In the window that opens, type the following and press Enter:

    ```cmd
    node --version
    ```

    You should see a version number printed, like `v20.11.0`. If you see a number, Node.js is installed correctly. If you see an error, restart your computer and try again.

    Also type this and press Enter:

    ```cmd
    npm --version
    ```

    npm is the package manager that comes bundled with Node.js. You use it to install Docusaurus. You should see a version number like `10.2.4`.

1. **Visual Studio Code**

    Visual Studio Code (VS Code) is a free text editor made by Microsoft. For technical writers in a Docs-as-Code workflow, it serves as your primary writing environment.

    To install VS Code:

    1. Go to [https://code.visualstudio.com](https://code.visualstudio.com).
    1. Click the Download button for your operating system.
    1. Run the installer with all default settings.