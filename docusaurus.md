---

title: How to set up Docusaurus in a Docs-as-Code environment
layout: default
---


# How to set up Docusaurus in a Docs-as-Code environment

I use VS Code to write Markdown content, GitHub Desktop to commit and push changes, and GitHub Pages to publish my documentation as a static site. Until recently, Jekyll was handling the site generation for me. While Jekyll works well for general-purpose blogs and sites, I wanted something purpose-built for documentation — structured navigation, versioning, and a cleaner reading experience out of the box.
That is where Docusaurus comes in. In this guide, I walk you through every step of setting up Docusaurus in the same Docs-as-Code environment you are already using — VS Code, GitHub Desktop, and GitHub Pages — without touching your existing Jekyll configuration. By the end, your documentation site will be live on a public GitHub Pages URL.

## What is Docusaurus

Docusaurus is an open source static site generator built by Meta, designed specifically for documentation. It converts your Markdown files into a structured, searchable documentation website.
Unlike Jekyll — which was built for blogs and general websites — Docusaurus is built from the ground up for technical documentation. It gives you sidebar navigation, search, versioning, dark mode, and a professional documentation layout without any extra configuration.
You write in Markdown. Docusaurus takes care of the rest.

## Who this article is for
This guide is written for technical writers who:

- Already write content in Markdown using VS Code
- Use GitHub Desktop to commit and push changes to GitHub
- Publish their site using GitHub Pages
- Have a Jekyll _config.yml file in their repository that they want to keep untouched
- Have little or no experience with Node.js or command-line tools

No prior experience with Docusaurus or Node.js is required.


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
    1. Click the **Download** button for your operating system.
    1. Run the installer with all default settings.

1. **GitHub Desktop**

    GitHub Desktop is a visual application that lets you use Git version control without typing commands. You click buttons instead of typing instructions, which makes it far more accessible for writers who are new to version control.

    To install GitHub Desktop:

    1. Go to [https://desktop.github.com](https://desktop.github.com).
    1. Click **Download** for your OS.
    1. Run the installer.
    1. When GitHub Desktop opens, sign in with your GitHub account. If you do not have one, go to https://github.com and create a free account first.