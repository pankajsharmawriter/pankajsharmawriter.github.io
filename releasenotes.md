---

title: How to write release notes
layout: default
---

In this article, I am explaining what release notes are, why they matter, and how to write them effectively. This article also includes a complete template with a real-world example. It is intended for technical writers who are new to release notes or want to improve consistency in their documentation process.

## What are release notes

Release notes are a document that communicates what has changed in a product, software, or service as part of a new version or update. They describe new features, enhancements, bug fixes, deprecated features, and known issues.
Release notes are published every time a product ships a new release — whether it is a major version, a minor update, or a patch. They serve as the official record of what changed and why it matters to the user.

**Example**

When Google Chrome releases version 125, it publishes release notes that list new developer features, security fixes, and deprecated APIs. Developers and IT administrators read these notes to decide whether to upgrade and to plan any required changes in their own systems.

## Purpose of release notes

- They inform end users about new features and improvements they can use.
- They help support teams understand what changed so they can handle user queries.
- They give QA teams a reference to verify that documented changes are shipped.
- They create an audit trail for compliance and internal accountability.


## Intended audience

- **End users**: Want to know what is new and how it benefits them.
- **Developers**: Need precise technical details about new or changed functionality.
- **IT administrators**: Care about compatibility and security patches.
- **Customer support teams**: Use release notes as a reference when handling user issues.


## Types of release notes

### Major release notes
Major releases (for example, v1.0 to v2.0) introduce significant new features or architectural changes. These require detailed documentation covering all changed areas of the product.

### Minor release notes
Minor releases (for example, v2.1 to v2.2) include new features or enhancements that do not break existing functionality. These are moderately detailed and focus on what was added or improved.

### Patch release notes
Patch releases (for example, v2.1.0 to v2.1.1) fix bugs or address security vulnerabilities. These are concise and focused on what was broken and what was fixed.

### Hotfix release notes
Hotfixes are emergency patches released outside the normal release cycle. These are brief, focused on the specific critical issue resolved.

## Key sections in release notes

- **Version number and release date** — Identifies the release clearly.
- **Overview** — A brief summary of what this release includes.
- **New features** — Describes new capabilities added in this release.
- **Enhancements and improvements** — Lists existing features that have been improved.
- **Bug fixes** — Documents issues that have been resolved.
- **Deprecated features** — Lists features being phased out.
- **Known issues** — Discloses unresolved issues users may encounter.
- **Reference links** — Points to related documentation or support.

## How to write each section

### Version number and release date

State the version number and release date at the top of the document. Follow semantic versioning (MAJOR.MINOR.PATCH) if your product uses it.

**Example**:

> Version 3.2.0 | Released: 15 June 2025