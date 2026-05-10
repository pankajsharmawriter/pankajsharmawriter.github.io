---
title: Agile, Scrum, and JIRA
layout: default
---


# Agile, Scrum, and JIRA

In this article, I am explaining the core concepts of Agile methodology, Scrum framework, and JIRA — three pillars that define how modern software development teams plan, execute, and deliver work. As a technical writer embedded in an engineering team, understanding these concepts is not optional. It is the foundation of your ability to plan documentation sprints, align deliverables with engineering releases, participate meaningfully in team ceremonies, and use JIRA as a project tracking tool for your own documentation tasks.

This article covers Scrum ceremonies (sprint planning, daily standups, retrospectives), story points, JIRA dashboard concepts, and a comparison of Scrum vs. Kanban and Agile vs. Waterfall. Whether you are new to an Agile team or need a structured reference to solidify your understanding, this guide is written specifically for technical writers navigating iterative development workflows.

## What Is Agile

Agile is a software development philosophy, not a single tool or process. It is defined by the Agile Manifesto (2001), which prioritizes:

- Individuals and interactions over processes and tools
- Working software over comprehensive documentation
- Customer collaboration over contract negotiation
- Responding to change over following a plan

For technical writers, the third and fourth values are especially relevant. Agile environments are iterative — features ship in short cycles, and documentation must keep pace. You rarely have the luxury of a six-month documentation plan delivered as a waterfall. Instead, you plan documentation in sprints, ship drafts alongside feature releases, and refine continuously based on user feedback and product changes.
Agile is implemented through frameworks. The most widely adopted framework is Scrum.

## What Is Scrum

Scrum is a lightweight framework within Agile that organizes work into fixed-length iterations called sprints — typically two weeks long. Scrum defines three roles, five ceremonies, and three artifacts.

### Scrum roles

| Role | Responsibility |
| --- | --- |
| Product Owner (PO) | Owns the product backlog; prioritizes features and user stories |
| Scrum Master | Facilitates Scrum ceremonies; removes blockers for the team |
| Development Team | Executes sprint work; includes engineers, QA, and technical writers |

As a technical writer, you are a member of the development team. You participate in all Scrum ceremonies and maintain documentation tasks as items in the product backlog or sprint board.

## Scrum ceremonies

Scrum defines five formal ceremonies (also called events). Each has a specific purpose, a defined timebox, and expected participants.

1.  **Sprint Planning Meeting**

    The sprint planning meeting kicks off every sprint. The team meets to decide which backlog items to pull into the upcoming sprint.

    **Duration**: 2–4 hours for a two-week sprint
    **Participants**: Product Owner, Scrum Master, Development Team (including technical writers).

    What happens:
    - The Product Owner presents the highest-priority backlog items.
    - The team discusses scope, dependencies, and feasibility.
    - Each item is estimated using story points (covered in detail below).
    - The team commits to a sprint goal — a single, clear statement of what the sprint will deliver.

    **For technical writers**: Sprint planning is where you advocate for documentation tasks. If a new API is shipping in the sprint, your documentation task — whether it is a new endpoint reference, a user guide update, or a release note — must be added to the sprint board. If you do not add it here, it becomes invisible to the team.

    **Best practice**: Review the sprint backlog before the meeting. Identify features that will require documentation updates and create corresponding JIRA tickets in advance.

1. **Daily Scrum (Standup)**

    The daily scrum is a 15-minute synchronization meeting held every working day during the sprint.

    **Duration**: 15 minutes (strictly timeboxed)

    **Participants**: Development Team, Scrum Master

    The three standard questions:
    - What did I complete yesterday?
    - What will I work on today?
    - Are there any blockers?

    **For technical writers**: Your standup updates should reference specific documentation tasks by JIRA ticket ID. For example: "Yesterday I completed the first draft of the authentication guide (DOC-142). Today I am starting the error codes reference (DOC-143). No blockers."

    Avoid vague updates like "I am working on documentation." Precision builds credibility in engineering teams.

    ### Common blockers for technical writers:

    - SME unavailability for review
    - Feature not yet implemented in the dev environment
    - Missing API specification or design document

    Flag these early. A blocker unspoken is a deadline missed.

1. **Sprint Review**

    The sprint review is held at the end of each sprint. The team demonstrates completed work to stakeholders and gathers feedback.

    **Duration**: 1–2 hours

    **Participants**: Development Team, Scrum Master, Product Owner, Stakeholders

    What happens:
    - The team demonstrates working software (and documentation deliverables)
    - The Product Owner accepts or rejects completed items
    - Stakeholders provide feedback that may feed into the next sprint backlog

    **For technical writers**: If your documentation is a deliverable — a published help article, a revised API reference, a release note — present it during the sprint review. Share the link, walk through the structure, and invite feedback. This visibility reinforces documentation as a first-class sprint deliverable.

1. **Sprint retrospective**

    The retrospective is a structured reflection meeting held after the sprint review and before the next sprint planning session.

    **Duration**: 1–1.5 hours

    **Participants**: Development Team, Scrum Master

    The three retrospective questions:

    - What went well?
    - What did not go well?
    - What will we improve next sprint?

    The retrospective is a safe space for honest feedback. It is not a blame session — it is a continuous improvement mechanism.

    For technical writers: Retrospectives are an opportunity to raise systemic documentation challenges. Examples:

    - I consistently receive SME feedback in the final two days of the sprint, leaving no time for revisions. Can we define a mid-sprint review checkpoint?.
    - Feature specifications are not finalized when the sprint starts. This delays documentation by 3–4 days each sprint.

    Bring data. If a pattern repeats across sprints, note it. Retrospectives have the most impact when observations are specific and actionable.