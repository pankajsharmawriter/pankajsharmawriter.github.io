---

title: How to set up MkDocs in a Docs-as-Code environment
layout: default
---


# How to set up MkDocs in a Docs-as-Code environment

In this article, I will explain how to set up MkDocs as a static site generator in an existing Docs-as-Code environment. If you already use VS Code to write Markdown content, GitHub Desktop to commit and push your changes, and GitHub Pages to publish your site, this guide walks you through every step — from installing Python to publishing your MkDocs site on a live public URL. By the end of this article, you will have a professional documentation site running locally on your computer and published on GitHub Pages, without using a single Git command.

## What is MkDocs

MkDocs is a free, open source static site generator built specifically for documentation. It converts your Markdown files into a clean, structured documentation website. Unlike Jekyll, which is a general-purpose site generator, MkDocs is purpose-built for technical documentation — it generates a sidebar navigation automatically from your folder structure, requires minimal configuration, and produces a fast, readable documentation site out of the box.

MkDocs also supports themes. The most popular theme is Material for MkDocs, which gives your site a modern, professional appearance used by companies like Kubernetes, FastAPI, and Google.

## Step 1: Install Python

MkDocs is built on Python. You must install Python before you can install MkDocs.

**Install Python on Windows**:

1. Open your browser and go to [https://www.python.org/downloads](https://www.python.org/downloads).
1. Click the **Download Python** button. The site detects your operating system automatically and suggests the correct version.
1. Open the downloaded installer file (named something like `python-3.12.x-amd64.exe`).
1. On the first screen of the installer, select the checkbox labelled **Add Python to PATH**.

    **Important**: You must select Add Python to PATH before clicking Install. If you skip this step, Python will not be recognized in the VS Code terminal and you will need to reinstall it.


1. Click **Install Now** and wait for the installation to finish.
1. Click **Close** when the installer completes.

**Verify the Python installation**

1. Open VS Code.
1. Press Ctrl+` to open the integrated terminal.
1. Type the following command and press **Enter**:
    ``` cmd
    python --version
    ```

1. You should see a version number such as `Python 3.12.2`. This confirms Python is installed correctly.

## Step 2: Install MkDocs

With Python installed, you can now install MkDocs using pip. pip is Python's package manager — it works the same way npm works for Node.js. It was installed automatically with Python.

1. In the VS Code integrated terminal, type the following command and press **Enter**:

    ``` cmd
    pip install mkdocs
    ```
1. pip downloads and installs MkDocs and its dependencies. This takes about one minute.
1. Verify the installation by running:
    ``` cmd
    mkdocs --version
    ```
1. You should see output like `mkdocs, version 1.5.3`. This confirms MkDocs is installed.

## Step 3: Install the Material for MkDocs theme

The default MkDocs theme is functional but basic. Material for MkDocs is a free, professionally designed theme that makes your documentation site look polished and modern. It is the most widely used MkDocs theme in the industry.

In the terminal, type the following command and press **Enter**:

``` cmd
pip install mkdocs-material
```
## Step 4: Open your repository in VS Code

1. Open GitHub Desktop.
1. In the left sidebar, select your GitHub Pages repository.
1. Click **Open in Visual Studio Code**.

Your existing project files — including your Jekyll _config.yml and Markdown articles — appear in the VS Code Explorer panel. Do not modify any of these files.

## Step 5: Create a new MkDocs project inside your repository

You create the MkDocs project as a subfolder inside your existing repository. This keeps it completely separate from your Jekyll configuration.

1. In the VS Code integrated terminal, confirm you are at the root of your project. You should see a path like:
    ``` cmd
    C:\Users\YourName\Documents\GitHub\your-repository>
    ```

1. Type the following command and press **Enter**:

    ``` cmd
    mkdocs new my-mkdocs-site
    ```

    Replace `my-mkdocs-site` with any folder name you prefer. Use this same name in every step that follows.

1. MkDocs creates a new folder named `my-mkdocs-site/` inside your repository with the following structure:

    ``` yaml
    my-mkdocs-site/
   ├── docs/
   │   └── index.md
   └── mkdocs.yml
   ```

    - **docs/** — the folder where all your Markdown articles go.
    - **index.md** — the default home page of your site.
    - **mkdocs.yml** — the configuration file for your MkDocs site.

## Step 6: Configure the mkdocs.yml file

Open `my-mkdocs-site/mkdocs.yml` in VS Code. This file controls your site's name, theme, and navigation.

Replace the default contents with the following configuration:

``` yaml
site_name: Pankaj Sharma | Technical Writer
site_url: https://pankajsharmawriter.github.io/my-mkdocs-site/
site_description: Articles on technical writing, API documentation, and Docs-as-Code
site_author: Pankaj Sharma

theme:
  name: material
  palette:
    primary: indigo
    accent: indigo
  font:
    text: Roboto
    code: Roboto Mono
  features:
    - navigation.sidebar
    - navigation.top
    - search.highlight

nav:
  - Home: index.md
  - Articles:
    - API documentation basics: api-documentation.md
    - Docs-as-Code with Markdown: docs-as-code.md
    - Agile and Scrum: agile.md
```

**Note**: Update the **nav** section to match the actual filenames of your Markdown articles inside the `docs/` folder. Every file listed in **nav** must exist in `docs/`.

Save the file after making your changes.

## Step 7: Add your Markdown articles

Copy the Markdown articles you want to publish into the `my-mkdocs-site/docs/` folder.

Each article does not require a frontmatter block — MkDocs reads the first H1 heading in each file as the page title. However, you can optionally add a simple frontmatter block for better control:

``` yaml
---
title: API Documentation Basics
---

# API documentation basics

Your content starts here.
```

**Tip**: Keep your filenames lowercase with hyphens and no spaces — for example, `api-documentation.md`, not `API Documentation.md`. This ensures clean URLs on your published site.

## Step 8: Run MkDocs on localhost

Before publishing your site, preview it locally to verify that everything looks correct.

1. In the VS Code terminal, navigate into your MkDocs folder:

    ``` cmd
    cd my-mkdocs-site
    ```

1. Start the local development server:

    ``` cmd
    mkdocs serve
    ```

1. MkDocs compiles your site and displays the following message in the terminal:

    ``` cmd
    INFO - Serving on http://127.0.0.1:8000/
    ```

1. Open your browser and go to `http://127.0.0.1:8000/`.
Your MkDocs site opens with the Material theme applied. The left sidebar shows your navigation, and the search bar is functional.

1. To stop the server, click inside the terminal and press **Ctrl+C**.

**Note**: Any changes you make to your Markdown files while the server is running are reflected in the browser immediately without restarting the server.

## Step 9: Build the static site

When you are satisfied with the local preview, build the static site files that GitHub Pages will serve.

In the terminal (from inside `my-mkdocs-site/`), run:
``` cmd
mkdocs build
```
MkDocs compiles all your Markdown files into static HTML, CSS, and JavaScript files and outputs them into a `my-mkdocs-site/site/` folder.

## Step 10: Add the site folder to .gitignore

The `site/` folder is auto-generated each time you build. It does not need to be committed to GitHub as source code because you will deploy it separately in the next step.

1. Open the `.gitignore` file in the root of your repository. If it does not exist, create a new file named `.gitignore` in the root folder.

1. Add the following line:
    ``` cmd
    my-mkdocs-site/site/
    ```

1. Save the file.

## Step 11: Deploy to GitHub Pages

MkDocs includes a built-in deploy command that builds your site and pushes it directly to the `gh-pages` branch of your repository — the branch that GitHub Pages serves.

In the terminal (from inside `my-mkdocs-site/`), run:

``` cmd
mkdocs gh-deploy
```

MkDocs builds the site, creates the `gh-pages` branch if it does not already exist, and pushes the compiled files to GitHub.

When the command finishes, you will see a message like:

``` cmd
INFO - Your documentation should shortly be available at:
https://pankajsharmawriter.github.io/my-mkdocs-site/

```

**Note**: The `mkdocs gh-deploy` command handles the entire deployment in one step. You do not need to manually push any files or run separate build commands.