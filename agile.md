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

Scrum defines four formal ceremonies (also called events). Each has a specific purpose, a defined timebox, and expected participants.

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

## Story points

Story points are a unit of estimation used in Scrum to measure the relative effort, complexity, and risk of a backlog item — not the time it takes.

Story points are typically assigned using the Fibonacci sequence: 1, 2, 3, 5, 8, 13, 21. The sequence is non-linear by design — the gap between 8 and 13 reflects that larger tasks carry proportionally more uncertainty.

How estimation works:

- The team reviews a backlog item
- Each member privately selects a story point value
- All values are revealed simultaneously
- Outliers explain their reasoning
- The team discusses and reaches consensus

For technical writers — story point examples:

| Documentation task | Story points |
| --- | --- |
| Minor update to an existing topic (< 100 words) | 1 |
| New conceptual topic (500–700 words) | 3 |
| New procedural guide (multi-step, screenshots needed) | 5 |
| Full API endpoint reference (parameters, request/response examples) | 8 |
| New user guide for a major feature | 13 |

**Key principle**: Story points measure effort relative to your team's baseline, not absolute hours. A task that takes a junior writer 8 hours and a senior writer 3 hours might both be a 5-point task — because the points reflect the work, not the person.

**Velocity**: The total story points completed per sprint is the team's velocity. Over time, velocity stabilizes and becomes a reliable planning input. If your documentation team consistently completes 18–22 story points per sprint, the Product Owner knows how much to plan per cycle.

## JIRA dashboard concepts

JIRA (by Atlassian) is the most widely used project tracking tool in Agile teams. Understanding its core concepts allows you to manage your documentation tasks efficiently and communicate status clearly to your team.

### Backlog

The backlog is the complete, prioritized list of all work to be done — features, bugs, documentation tasks, and technical debt. The Product Owner owns the backlog and continuously grooms (refines) it.

**For technical writers**: Maintain a personal documentation backlog. Create JIRA tickets for every documentation task, even if it is not yet planned for a sprint. This prevents work from becoming invisible.

### Epic
An Epic is a large body of work that spans multiple sprints. Epics are broken down into smaller stories or tasks.

**Example**: An Epic titled "Developer Documentation for Authentication API v2" might contain stories for the overview, endpoint reference, error codes, and migration guide.

### User story
A user story is a backlog item written from the end user's perspective. The standard format is:

As a [user], I want to [action], so that [benefit].

**Example for documentation**:

As a developer, I want a reference for all authentication endpoints, so that I can integrate the API without contacting support.

### Task

A Task is a concrete work item, often a child of a Story or Epic. For technical writers, tasks are the most common ticket type.
Example tasks:

- DOC-201: Write first draft — Authentication Overview
- DOC-202: Peer review — Error Codes Reference
- DOC-203: Publish and link — Migration Guide

### JIRA board views

| View | Purpose |
| --- | --- |
| Scrum Board | Kanban-style columns (To Do, In Progress, In Review, Done) for the active sprint |
| Backlog View | Full list of upcoming and unplanned work |
| Roadmap | Timeline view of Epics across quarters |
| Dashboard | Customizable widgets — sprint burndown, velocity chart, issue breakdown |

### Burndown chart

The sprint burndown chart tracks remaining story points against the sprint timeline. A healthy burndown slopes steadily downward. A flat line indicates blocked work. A cliff at the end indicates the team underestimated or started tasks late.

**For technical writers**: Monitor the burndown mid-sprint. If your documentation tasks are stalled, raise them in the daily standup before they become a sprint-end problem.

## Scrum vs Kanban

Both Scrum and Kanban are Agile frameworks, but they have different structures and are suited to different workflows.

| Dimension | Scrum | Kanban |
| --- | --- | --- |
| Work cycle | Fixed sprints (1–4 weeks) | Continuous flow, no sprints |
| Planning | Sprint planning ceremony | Pull-based; items pulled when capacity allows |
| Roles | Defined (PO, Scrum Master, Team) | No prescribed roles |
| WIP limits | Not prescribed | Explicit WIP limits per column |
| Changes mid-cycle | Generally avoided during a sprint | Can be added anytime |
| Best for | Feature development with predictable cadence | Support queues, maintenance, ops, content updates |

**For technical writers**: Scrum works well when documentation is tied to feature releases with defined sprint cycles. Kanban suits documentation teams that handle ad-hoc requests — a support article update today, a UI string review tomorrow. Many documentation teams use a Scrumban hybrid: sprint-based planning with Kanban-style WIP limits for flexibility.

## Agile vs Waterfall

Waterfall is a sequential, phase-based development model. Agile is iterative and incremental.

| Dimension | Waterfall | Agile |
| --- | --- | --- |
| Delivery | Single delivery at project end | Incremental delivery every sprint |
| Requirements | Fixed upfront | Evolve throughout the project |
| Documentation | Heavy, upfront documentation | Lean, just-in-time documentation |
| Customer involvement | Minimal after requirements phase | Continuous collaboration |
| Change management | Expensive and disruptive | Expected and accommodated |
| Risk | High — issues surface late | Low — issues surface early in iteration |
| Best for | Regulated industries, fixed-scope contracts | Software products with evolving requirements |

**For technical writers**: Waterfall gives you months to write documentation before delivery. Agile gives you two weeks. The discipline required is fundamentally different. In Agile, you write to a moving target — you draft while the feature is being built, review while it is being tested, and publish at sprint close. The skill is not just writing — it is triage, prioritization, and speed.

## Conclusion

Understanding Agile, Scrum, and JIRA is not peripheral knowledge for technical writers — it is operational literacy. Every sprint planning meeting you participate in without understanding story points is a missed opportunity to advocate for documentation scope. Every retrospective you attend without raising a documentation process gap is a problem that repeats next sprint.

This article matters because it closes the knowledge gap that exists for many technical writers who are excellent at writing but underprepared for the team dynamics of iterative development environments. When you understand the language of Scrum — when you can estimate your tasks in story points, track them on a JIRA board, and raise blockers in a standup with precision — you stop being a peripheral contributor and become a fully integrated member of the engineering team.

For your end users — the technical writers who read this article — the immediate benefit is confidence: the confidence to sit in a sprint planning meeting and push back when documentation is scoped out, the confidence to write a JIRA ticket that an engineering manager can read and immediately understand, and the confidence to use retrospectives to fix the broken processes that slow documentation teams down.

Agile is not just how software is built. For modern technical writers, it is how documentation is built too. The sooner you internalize that, the more effective you become.

For any query, contact me at **pankajsharmawriter@gmail.com**.

## Reference

-  [About me](./)