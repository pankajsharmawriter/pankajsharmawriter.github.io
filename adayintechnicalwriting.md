---
title: Learn Git commands for Technical Writers
layout: default
---

# A day in the life of a technical writer in an Agile environment

In this article, I am walking through a typical working day as a senior technical writer embedded in an Agile software development team. This is not a theoretical exercise — it is a practical account of how documentation work unfolds across a sprint day, from the morning standup to the end-of-day JIRA update. If you are a technical writer transitioning into an Agile team, or a hiring manager curious about how documentation fits into an iterative development workflow, this article gives you an honest, ground-level view.

A technical writer in an Agile environment does not simply write. They plan, coordinate, review, publish, and track — all within the rhythm of a two-week sprint. Understanding this daily rhythm is what separates a writer who delivers on time from one who is always catching up.

## Morning: starting the day with context

The day begins not with writing, but with reading. Before the standup, I spend 15–20 minutes catching up on what happened overnight — Slack messages from developers, email notifications from JIRA, and review comments left on shared documents. This triage sets the agenda for the day.

### Typical morning triage checklist:

- Review comments received on active drafts (via Google Docs, Confluence, or email)
- JIRA notifications — ticket status changes, new assignments, sprint updates
- Slack messages — developer questions, SME availability confirmations, last-minute feature changes
- Any updated API specifications or design documents shared by the product team

This 15-minute window prevents surprises later in the day. If a developer changed an API endpoint overnight, I know before I spend two hours documenting the old version.

## Daily scrum: 15 minutes that define your day

At 11 AM (or whichever time the team has fixed), the daily scrum begins. This is a 15-minute standup — no chairs, no presentations, no detours. The Scrum Master facilitates. Every team member answers three questions:

1. What did I complete yesterday?
1. What will I work on today?
1. Are there any blockers?

As a technical writer, my standup update is specific and ticket-referenced. A good update sounds like this:

> "Yesterday I completed the first draft of the data export API reference (DOC-118). Today I am starting the error codes section for the same endpoint (DOC-119). I have a blocker — I am waiting on Rahul to confirm the behaviour of the 429 error code before I can finalize that section."

### What to raise in a standup as a technical writer

- A feature is marked Done in JIRA but the developer has not responded to your documentation questions
- You need access to the staging environment to verify a procedure
- An SME promised a review two days ago and has not responded
- A feature scope changed mid-sprint and your draft is now outdated

Raise these early. A blocker mentioned on day eight of a ten-day sprint is a missed deadline.

## Mid-morning: core writing time

After the standup, I protect the next two hours for focused writing. This is the most cognitively demanding work of the day, and it deserves the best hours — before meetings accumulate and context-switching begins.

What I am writing depends on where we are in the sprint:

| Sprint phase | Typical documentation task |
|---|---|
| Sprint days 1–3 | Review feature specs, create doc tickets, draft outlines |
| Sprint days 4–7 | Write first drafts — user guides, API references, release notes |
| Sprint days 8–9 | Incorporate SME review feedback, finalize drafts |
| Sprint day 10 | Final review, publish, update JIRA tickets to Done |

During writing, I keep the JIRA ticket open in a browser tab. If I discover a gap — a missing parameter definition, an undocumented error code, a step I cannot reproduce in the test environment — I log it as a comment on the ticket immediately. This creates a traceable record and keeps my draft moving without getting stuck.

### Tools open during writing time:

- VS Code (Markdown writing in a Docs-as-Code workflow)
- Postman (for testing API endpoints I am documenting)
- The product's staging environment (to verify procedures step by step)
- JIRA (sprint board and active ticket)
- Confluence or SharePoint (for accessing existing documentation and internal specs)

## Early afternoon: SME coordination and review follow-up

Around 12:30 PM, I shift to coordination work — the part of the job that does not show up in a job description but consumes a significant part of every day.

### SME (Subject Matter Expert) coordination involves:

- Sending review requests for drafts that are ready for technical validation
- Following up on reviews that are past due
- Scheduling a 20-minute call with a developer to walk through an undocumented feature
- Asking targeted questions over Slack rather than waiting for a formal meeting