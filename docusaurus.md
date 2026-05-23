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

## Step 1: Open your repository in VS Code

1. Open GitHub Desktop.
1. In the left sidebar, select your repository — **pankajsharmawriter.github.io**.
1. Click **Open in Visual Studio Code**.

VS Code opens with your project files visible in the Explorer panel on the left. You will see your existing files including _config.yml and your Markdown articles. Do not touch any of these files.

## Step 2: Open the VS Code integrated terminal

In VS Code, press Ctrl+` to open the integrated terminal at the bottom of the screen.
The terminal opens at your project root directory. You will see a path like **C:\Users\YourName\Documents\GitHub\pankajsharmawriter.github.io>**.
All commands in the steps below are typed into this terminal.

## Step 3: Create a new Docusaurus project inside your repository

You will create a Docusaurus project inside a subfolder of your existing repository. This keeps it completely separate from your Jekyll files.
In the terminal, type the following command and press **Enter**:

```cmd
npx create-docusaurus@latest my-docs classic
```

### What does this command do

- **npx** is a tool that comes with npm. It runs a package without installing it permanently.
- **create-docusaurus@latest** downloads the latest version of Docusaurus and sets up a new project.
- **my-docs** is the name of the subfolder that will be created. You can change this name, but if you do, replace my-docs with your chosen name in every step that follows.
- **classic** is the template — it includes a docs section, a blog section, and a landing page.

The command takes a minute or two to run. It downloads Docusaurus and creates a `my-docs/` folder inside your project.
When it finishes, you will see a message like `Happy building awesome docs!` in the terminal.

### What the installer asks you

During setup, it may ask:

- Which language do you want to use? Select **JavaScript**.
- Do you want to use TypeScript? Select **No**.

## Step 4: Navigate into the Docusaurus folder

In the terminal, type:

``` cmd
cd my-docs
```

This moves the terminal into your new Docusaurus folder. All commands from this point forward run from inside `my-docs/`.

## Step 5: Install dependencies

Type the following command and press **Enter**:

``` cmd
npm install
```


This downloads all the packages that Docusaurus needs to run. It creates a folder called `node_modules/` inside `my-docs/`. This folder is large — it can contain thousands of small files — but you will exclude it from GitHub in a later step so it does not get pushed to your repository.
The installation takes one to two minutes. You will see a progress indicator in the terminal.

## Step 6: Run Docusaurus on localhost

Now you will preview your Docusaurus site on your computer before publishing it publicly.
In the terminal, type:

``` cmd
npm start
```

Docusaurus compiles your project and opens it in your default browser automatically at `http://localhost:3000`.

You will see the default Docusaurus site — a landing page with a **Docs** section. This is your site running locally on your machine. No one else can see it yet.

To stop the local server at any time, click inside the terminal and press **Ctrl+C**.

## Step 7: Add your Markdown articles to Docusaurus

Your existing Markdown articles live in the root of your repository. You now copy the ones you want to publish with Docusaurus into the `my-docs/docs/` folder.

1. In the VS Code Explorer panel, expand the `my-docs` folder.
1. Inside it, open the `docs/` subfolder.
1. Copy your Markdown articles into `my-docs/docs/`.

### Add frontmatter to each article

Docusaurus reads a small block of metadata at the top of each Markdown file called frontmatter. This tells Docusaurus the page title, URL, and sidebar label.
Add the following block to the very top of each Markdown file, before any other content:

``` yaml

---
id: api-documentation-basics
title: API Documentation Basics
sidebar_label: API Documentation
---
```
## Step 8: Update the Docusaurus configuration file

Open `my-docs/docusaurus.config.js` in VS Code. This is the main configuration file for your Docusaurus site.
Find and update the following fields:

``` javascript
const config = {
  title: 'Pankaj Sharma | Technical Writer',
  tagline: 'Articles on API documentation, Docs-as-Code, and technical writing tools',
  url: 'https://pankajsharmawriter.github.io',
  baseUrl: '/my-docs/',
  organizationName: 'pankajsharmawriter',
  projectName: 'pankajsharmawriter.github.io',
  deploymentBranch: 'gh-pages',
  trailingSlash: false,
};
```
**Important**: The `baseUrl` value must match the subfolder name you used in Step 4. If you named your folder `my-docs`, set `baseUrl` to `/my-docs/`. If you used a different name, update this value to match.

Save the file after making changes.

## Step 9: Exclude node_modules from GitHub

The `node_modules/` folder must never be pushed to GitHub. It is too large and is automatically recreated from `package.json` by anyone who clones your project.

1. In VS Code, open the `.gitignore` file in the root of your repository (not inside `my-docs/`).
1. If the file does not exist, create a new file in the root folder and name it `.gitignore`.
1. Add the following line to the file:
    ``` cmd
    my-docs/node_modules/
    ```
1. Save the file.

GitHub Desktop will now ignore the `node_modules/` folder and will not include it in your commits.

## Step 10: Build the static site

Before deploying to GitHub Pages, you need to compile your Docusaurus site into static HTML, CSS, and JavaScript files.
In the terminal (make sure you are inside `my-docs/`), type:

``` cmd
npm run build
```

Docusaurus compiles your Markdown files and outputs the static site into a `my-docs/build/` folder. This folder contains everything GitHub Pages needs to serve your site.
The build process takes about 30 to 60 seconds.

## Step 11: Deploy to GitHub Pages

Now you publish your site to the public URL on GitHub Pages.
In the terminal, type the following command exactly as written, replacing `pankajsharmawriter` with your own GitHub username:

``` cmd
cmd /C "set GIT_USER=pankajsharmawriter && npm run deploy"
```

### What does this command do?
It builds your site and pushes the compiled output from the `build/` folder to a special branch in your repository called `gh-pages`. GitHub Pages serves your site directly from this branch.

The command takes one to two minutes. When it finishes, you will see a message: Website is live at: **https://pankajsharmawriter.github.io/my-docs/**

**Note**: This is the Windows syntax for running the deploy command. The `cmd /C "set GIT_USER=..." ` part sets your GitHub username as an environment variable before running the deploy script.

