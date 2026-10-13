---
title: Designing PCD Appeal review emails for the task list
description: How we designed an MVP task-based journey, informed by research for reviewing police appeals against charging decisions.
date: 2026-10-13
---


When a CPS lawyer decides not to charge a suspect, the police can appeal that pre-charge decision (PCD). Today, appeals arrive by email with no task, reminder or audit trail, so they can go unactioned without anyone noticing.

We designed a way to manage appeals as tasks in the case management system (CMS). The work drew on 9 research sessions, a draft to-be process and decisions with the product owner on what goes into the minimum viable product (MVP). We worked in a lean way, moving quickly from research to a reviewed design, so some decisions still need testing with users.

## Why we did this work

An appeal when a police officer, usually an inspector or above, challenges a decision not to charge. It should arrive within 14 days of the original decision.

Today, every appeal relies on someone spotting an email and acting on it by hand within the agreed service level agreement (SLA) for green and red tasks:

- appeals always arrive through email, although some areas copy and post in a central Teams channel, in particular CPSD
- an operational delivery (OD) manager or Charging Manager has to add the email to the case, create a task and assign it to a District Crown Prosecutor (DCP)
- in CPS Direct (CPSD), the out-of-hours charging service, appeals are posted in a Teams channel for any available DCP to pick up
- each area tracks appeals in its own spreadsheet

This makes it hard to see which appeals are waiting, who has them and whether they've been dealt with. If an email is missed, nothing flags it.

Most appeals are routine, but priority appeals, also called red cases, can't wait. They usually involve someone in custody, so they're urgent from the moment they arrive.

We wanted appeals to arrive as tasks in CMS, so the people handling them can see, pick up and complete them in one place.

## What we did

We did not have a 'to-be' process from the buisness, so based on our understanding of how the current process of emails between actors works we put together a design concept to share with our users and get their view.

We ran 9 research sessions with participants from West Mids, Wales/South West, CPSD, London South, South East,
East Mids. Speaking with charging managers, DCPs and SDCP. Each session explored the current process, then tested a clickable prototype.

We then used the findings to iterate a draft to-be journey.

### What we learned from research

Participants strongly supported moving to tasks. As one DCP put it: "It doesn't appear in a task list, it doesn't appear in a reminder or any other format. It's simply an e-mail."

Broadly, the research showed that users need:

- a clear next step, so it's obvious how to start and finish an appeal
- the right information in one place, so they can judge an appeal quickly
- clear explanations of what happens to the case when an appeal comes in


### The MVP journey

We explored separate flows for different users, based on how a task gets assigned. Managers would triage and assign appeals, and DCPs would pick them up and review them. Designing for different assignment models added complexity the MVP didn't need, so we've put it out of scope for now.

Instead, there's one journey for everyone who handles appeals. OD managers, Charging Managers and DCPs all follow the same steps:

1. The police raise an appeal. This creates a "Review PCD appeal" or "Review priority PCD appeal" task in the task list.
2. The user sees a snapshot of the appeal on the case overview.
3. From the task list, they can view the appeal, reassign the task or start it.
4. Starting the task opens the appeal page, which explains that the case has been reactivated.
5. "Continue to case review" hands over to the case review journey, which another team owns. Completing that review completes the task.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
![Screenshot described under image](mvp-flow.png)

*Caption: The MVP journey from task list to case review*

Describe the screenshot here. Include the page heading, what each section contains, and what the buttons and links say.
<!-- END PLACEHOLDER -->

## What we changed and why

### Viewing an appeal without starting it

We added a read-only version of the appeal page, without the button to case review. A manager can check an appeal before assigning it, and anyone can read it without being pushed into a review.

### A snapshot on the case overview

The case overview has a [summary card](https://design-system.service.gov.uk/components/summary-list/#summary-cards) for the appeal. It shows who authorised the appeal, when it was received, when the original decision was made, the suspect and the reason for appeal.

The reason shows its first 35 words, with "See more" to expand it. This keeps the free text research asked for, while keeping the card easy to scan.

We first tried an [accordion](https://design-system.service.gov.uk/components/accordion/) holding all the appeal, charging and review details. We dropped it because the overview only needs a snapshot. The full details are one click away.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
![Screenshot described under image](case-overview-appeal-card.png)

*Caption: The PCD appeal card on the case overview*

Describe the screenshot here. Include the page heading, what each section contains, and what the buttons and links say.
<!-- END PLACEHOLDER -->

### Telling reviewers the case has been reactivated

The appeal page uses a [notification banner](https://design-system.service.gov.uk/components/notification-banner/) to say: "This case has been reactivated. This task can only be completed by carrying out an appeals case review."

We also tried [inset text](https://design-system.service.gov.uk/components/inset-text/) next to the button, but chose the banner because it's more noticeable. A "Continue to case review" button at the bottom of the page replaces a link that participants missed.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
![Screenshot described under image](appeal-reactivated-banner.png)

*Caption: The appeal page with the reactivation banner*

Describe the screenshot here. Include the page heading, what each section contains, and what the buttons and links say.
<!-- END PLACEHOLDER -->

### Reassigning uses the existing journey

Reassigning is unchanged for MVP, and a success message confirms when a task has been reassigned. We explored a "To me" option for CPSD, who pick appeals up from a shared pool, but left it out of MVP as they can technically assign it to themselves in the existing assign journey.

## What we found about case reactivation

The case is reactivated as soon as the police raise the appeal and the task is created, not when a DCP starts the task.

That means every appeal reactivates the case, including appeals that won't be upheld. Participants were already worried that reactivation triggers a new charging decision and counts twice in performance data. The draft to-be process only reactivates a case once an appeal is upheld, so the two don't yet agree.

## What we can do in the future

- **More user research.** We moved quickly in a lean way, so the final MVP flow and the reactivation banner need testing with users.
- **Rejecting at intake.** Charging Managers want to reject appeals that are out of time or come from someone below inspector level, without a full review.
- **Appeals that aren't upheld.** The banner only mentions an appeals case review, but the to-be process has a separate ad hoc review for appeals that aren't upheld.
- **Notifications.** DCPs move between custody suites and courts, so they need notifications and mobile access to build the habit of using tasks.
- **Appeals log and messages to police.** Areas still keep their own spreadsheets and email acknowledgements to police by hand.
