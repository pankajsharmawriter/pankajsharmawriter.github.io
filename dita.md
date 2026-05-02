---

title: Structured authoring with DITA and MadCap Flare
layout: default
---

# Structured authoring with DITA and MadCap Flare

In this article, I am explaining the core concepts of structured authoring using two widely adopted tools and standards in the technical writing industry — DITA (Darwin Information Typing Architecture) and MadCap Flare. The topics covered include the foundations of XML, DITA topic types, DITA maps, content reuse techniques such as Conref and Snippets, Conditional Text, Cross-References, Hyperlinks, and DITA outputs.
Whether you are a technical writer just stepping into the world of structured authoring or a seasoned professional looking to consolidate your knowledge, this article will help you understand how DITA and MadCap Flare complement each other. You will learn how to write modular, reusable content that can be published across multiple formats and channels — a skill that is increasingly essential in modern documentation environments.
By the end of this article, you will have a clear understanding of the building blocks of structured authoring and how they are applied in real-world documentation projects.

## Introduction to structured authoring

Structured authoring is an approach to creating content where information is written according to a defined structure or schema. Instead of writing long, free-flowing documents, authors create modular, self-contained topics that can be reused, reorganized, and published across multiple formats.
In traditional documentation, a writer might create a single large Word document covering installation, configuration, and troubleshooting. In structured authoring, each of these areas is a separate topic. This separation allows the same topic to be reused in different documents without rewriting it.

**Real-world example**: A software company maintains documentation for three products. Instead of writing three separate user guides from scratch, the technical writing team uses structured authoring to write shared topics — such as 'System Requirements' or 'Installation Steps' — once and reuse them across all three guides. Any update made to the shared topic automatically reflects in all publications.

## What is XML

XML stands for Extensible Markup Language. It is a text-based format used to store and transport structured data. XML uses tags — similar to HTML — to describe the meaning of content, not its visual appearance.
In technical documentation, XML provides the underlying structure for DITA. Every DITA topic is an XML file. Tags in DITA XML identify whether a piece of content is a title, a paragraph, a step, a note, or a code block — making the content machine-readable and format-independent.

**Example**: A simple XML snippet for a DITA task step looks like this: `<step><cmd>Click the Install button.</cmd></step>`. The tag `<cmd>` tells the authoring tool and publishing engine that this is a command instruction, not a regular paragraph. This semantic tagging is what makes structured content so powerful.
XML forms the backbone of DITA. Without understanding XML basics, it is difficult to troubleshoot DITA files or customize publishing output.

