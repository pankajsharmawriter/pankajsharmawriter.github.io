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

## What is DITA

DITA stands for Darwin Information Typing Architecture. It is an XML-based standard developed by IBM and now maintained by OASIS (Organization for the Advancement of Structured Information Standards). DITA defines a set of rules for how technical content should be structured, typed, and reused.
The key philosophy behind DITA is topic-based authoring — content is written as independent, typed topics rather than as chapters within a book. Each topic covers one subject and can stand on its own.
DITA is widely used in industries such as software, manufacturing, aerospace, and medical devices where documentation must be accurate, consistent, and publishable across formats like PDF, HTML, and EPUB.


**Real-world example**: A hardware manufacturer uses DITA to write installation guides for 20 different products. Each product shares common safety warning topics. Because these warnings are written as DITA topics, they are authored once and reused across all 20 guides. When legal updates the warning language, one edit propagates across all guides instantly.

## DITA Topic types: Concept, Task, and Reference

DITA defines three primary topic types. Each type has a specific purpose and a distinct XML structure.

### Concept

A concept topic answers the question 'What is it?' It provides background information, definitions, and explanations. Concept topics do not contain procedures or step-by-step instructions.

**Example**: A concept topic titled 'What is a Firewall?' explains what a firewall does, why it is used, and how it fits into a network architecture. It does not tell the reader how to configure one.

### Task

A task topic answers the question 'How do I do it?' It contains numbered steps that guide the reader through a procedure. Each step is tagged as a `<cmd>` element in DITA XML.

**Example**: A task topic titled 'How to Configure a Firewall' contains steps like: 
1. Log in to the admin portal. 
1. Navigate to Security Settings. 
1. Click Add Rule. 

The structured steps make it easy for publishing tools to format them consistently.

### Reference

A reference topic answers the question 'What are the details?' It contains structured, lookup-style information such as API parameters, command-line options, or configuration settings. Reference topics are typically formatted as tables or definition lists.


**Example**: A reference topic titled 'Firewall Rule Parameters' lists all available parameters, their data types, accepted values, and default settings in a table format.

## What is a DITA Map

A DITA map is an XML file that assembles individual DITA topics into a coherent publication. It does not contain content itself — it references topics and defines their order and hierarchy. Think of a DITA map as the table of contents for your documentation.
A DITA map uses <topicref> elements to point to individual topic files. Nested <topicref> elements create a hierarchy of chapters and sections.

**Real-world example**: A DITA map for a software user guide might reference a concept topic on system architecture, three task topics for installation, configuration, and activation, and a reference topic for error codes. The map defines the order in which these topics appear in the final output. The same topics could be referenced in a different map to produce a quick-start guide — without duplicating any content.

## Content reuse with Conref

Conref stands for Content Reference. It is a DITA mechanism that allows you to reuse a specific element from one topic inside another topic. Instead of copying and pasting content, you insert a reference that pulls the content dynamically at publish time.
Conref is used for warnings, notes, standard phrases, and any content that appears repeatedly across topics. If the source content changes, all references update automatically.

**Real-world example**: A standard safety warning — 'Disconnect the power supply before servicing the unit' — is written once in a shared topic called warnings.dita. Every task topic that requires this warning uses a conref to pull it in. When the legal team updates the warning language, the writer edits it in one place and every topic that references it is automatically updated upon the next publish.

Conref is one of the most powerful reuse features in DITA and significantly reduces maintenance effort in large documentation sets.

## Snippets in MadCap Flare

In MadCap Flare, the equivalent of DITA Conref is called a Snippet. A snippet is a reusable piece of content — a paragraph, a warning, a table, or even a list — saved as a separate .flsnp file and inserted into multiple topics.
When you update a snippet, the change is reflected everywhere the snippet is used, just like Conref in DITA.

**Real-world example**: A technical writer at a SaaS company maintains a 'System Requirements' snippet listing supported operating systems and browsers. This snippet is inserted into the installation guide, the release notes, and the quick-start guide. When a new browser version is supported, the writer updates the snippet once, and all three documents reflect the change automatically after the next build.

Snippets in MadCap Flare are the primary content reuse mechanism for writers who do not work in DITA XML but still need modular, maintainable documentation.

## Conditional text

Conditional text is a feature in both DITA and MadCap Flare that allows you to tag content for specific audiences, products, or output formats. Tagged content is included or excluded during publishing based on conditions you define.
In DITA, conditions are applied using attributes such as audience, product, and platform directly on XML elements. In MadCap Flare, conditions are defined as condition tags and applied to content blocks, paragraphs, or even individual words.

**Real-world example**: A software product has two editions — Standard and Enterprise. The user guide shares most content, but certain sections apply only to Enterprise customers. The writer tags those sections with a condition called 'Enterprise'. When publishing the Standard edition guide, the build excludes all Enterprise-tagged content. When publishing the Enterprise edition, all content is included. One source file produces two different outputs.

Conditional text eliminates the need to maintain separate documents for different audiences or product variants.

## Cross-references

A cross-reference is a link from one topic or section to another topic within the same documentation set. Cross-references help readers navigate between related content and provide additional context without duplicating information.
In DITA, cross-references are created using the <xref> element, which points to another topic by its file path or unique ID. In MadCap Flare, cross-references are inserted as internal links and can include dynamic text that automatically updates if the target heading changes.

**Real-world example**: In a task topic titled 'How to Back Up Your Data,' the writer adds a cross-reference at the end: 'For information on restoring data, see Restoring a Backup.' This cross-reference links to the relevant task topic. If the target topic is renamed or moved, Flare's cross-reference feature can automatically update the link text and destination.
Cross-references are essential for non-linear documentation where readers jump between topics based on their needs.

## Hyperlinks

A hyperlink is a clickable link that navigates the reader to an external URL — a website, a knowledge base article, a product page, or an external resource outside the documentation set.
In DITA, external hyperlinks are created using the <xref> element with an href attribute pointing to a URL and a scope attribute set to 'external'. In MadCap Flare, hyperlinks are inserted via the Insert Hyperlink dialog, where you specify the external URL.

**Real-world example**: A topic on API authentication includes a hyperlink to the company's developer portal: 'For the full list of API endpoints, visit the Developer Portal at https://developer.example.com.' In PDF output, the hyperlink appears as underlined text. In HTML5 output, it is a clickable link that opens in a new browser tab.

Unlike cross-references, hyperlinks point outside the documentation set and do not update automatically if the target URL changes. It is good practice to audit hyperlinks periodically in long-lived documentation.

## Variables in MadCap Flare

Variables in MadCap Flare are placeholders for text that changes across outputs, products, or versions. Instead of hardcoding a product name, version number, or company name throughout your content, you define it as a variable and insert the variable wherever it is needed.
When the value changes — for example, when a new product version is released — you update the variable definition once, and every instance across all topics updates automatically.


**Real-world example**: A documentation set covers version 5.0 of a software product. The product name 'DataSync Pro 5.0' appears in hundreds of topics. The writer stores 'DataSync Pro 5.0' as a variable called ProductNameVersion. When version 6.0 is released, the writer updates the variable value to 'DataSync Pro 6.0' in the Variable Set. All topics across the project now display the updated version number without touching a single topic file.










