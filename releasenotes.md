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

> Version 3.2.0  Released: 30 MAY 2026


### Overview
Write two to three sentences summarising the release. Focus on the most significant change and its value to the user.

**Example**:

> Version 3.2.0 introduces multi-factor authentication support and improves API response times by 40%. This release also resolves three critical bugs reported in the previous version.

### New features
List each new feature separately. Use the feature name as a bold label, followed by a brief description of what it does and where to find it.

**Example**:

> Multi-factor authentication (MFA): Users can now enable MFA from the Security Settings page. MFA supports authenticator apps (TOTP) and SMS verification. Once enabled, users are prompted for a second factor at every login.


### Enhancements and improvements
List improvements to existing features. Describe what changed and what benefit it provides.

**Example**:

> Faster API response times: API response times for the /users and /orders endpoints have improved by 40% due to database query optimisation.

### Bug fixes
List resolved issues with a brief description of the problem and the fix. Include the issue ID if you use a tracking system like JIRA.

**Example**:

> Login page timeout error (BUG-4821): Fixed an issue where users were logged out unexpectedly after 5 minutes of inactivity, even when the "Remember me" option was selected.

### Deprecated features
List features that are still functional in this release but will be removed in a future release. Give users enough notice to migrate.

**Example**:

> Legacy CSV export endpoint: The /export/csv/v1 endpoint is deprecated and will be removed in version 4.0. Use the new /export/v2 endpoint instead. See the migration guide for instructions.

### Known issues
List issues that exist in this release but have not yet been fixed. Include a workaround if one is available.

**Example**:

> Dashboard charts not rendering in Safari 16: Charts on the Analytics dashboard may not load correctly in Safari 16. Use Chrome or Firefox as a workaround while we investigate the issue.

## Release notes template

Use the following template for any software release. Remove sections that are not applicable.

``` yaml

# Release notes — [Product name]

## Version [X.X.X] | Released: [DD Month YYYY]

### Overview

[Two to three sentences summarising the key changes and their value to users.]

---

### New features

**[Feature name]**
[What can the user do now? Where can they find it?]

---

### Enhancements and improvements

**[Enhancement name]**
[What was improved and what benefit does it provide?]

---

### Bug fixes

**[Brief description of the issue] ([Issue ID if applicable])**
[What was the problem? What was fixed?]

---

### Deprecated features

**[Feature name]**
[What is being deprecated? When will it be removed? What should the user use instead?]

---

### Known issues

**[Brief description of the issue]**
[What is the problem? What is the workaround, if any?]

---

### Reference links

- [Full documentation](#)
- [API reference](#)
- [Changelog](#)
- [Contact support](#)
```