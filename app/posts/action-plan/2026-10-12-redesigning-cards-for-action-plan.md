---
title: Redesigning action plan cards
description: We rebuilt action plan cards with GOV.UK components to fix accessibility problems, and found that each card's actions depend on its status, not its category.
date: 2026-10-12
---

The action plan lets users see and manage the action points related to a case. Each action was shown as a custom component combining a summary card, details, and a tag. Inside the details component, there are a number of buttons.

A design review recognised the current design as not meeting the service standard by failing to use [common components and patterns](https://www.gov.uk/service-manual/service-standard/point-13-use-common-standards-components-patterns), resulting in a design that was not accessible and mean not everyone can use the service.

We rebuilt the action plan cards using proper GOV.UK components to fix accessibility problems, and found that each card’s actions depend on its status, not its category.

This wasn’t a research-led piece of work. We started with a design review and new design with input and support from subject matter experts (SME)

## Why we did this work

The old design had some problems:

- it wasn’t built on real component or patterns, so it missed the accessibility features GOV.UK components provide, such as semantic structure and consistent keyboard and focus behaviour
- button labels were inconsistent, and it wasn’t clear which buttons applied to the whole action and which applied to a single piece of information
- we didn’t know whether different categories of action (police initiated, pre-charge and post-charge) needed different information or actions

An accessibility specialist reviewed the new rationale before we started and was comfortable it was an improvement on the current version.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
<div class="app-image-row">

![Original 'Key witness details' card, status 'Re-opened', with buttons 'Change date required by', 'Withdraw' and 'Mark as complete'.](/action-plan/redesigning-cards-for-action-plan/key-witness-current.png)
![Original 'Medical evidence' card, status 'Draft', with buttons 'Edit draft' and 'Delete draft'.](/action-plan/redesigning-cards-for-action-plan/medical-evidence-current.png)
![Original 'Non-key witness details' card, status 'Completed', with a 'Re-open' button.](/action-plan/redesigning-cards-for-action-plan/non-key-witness-details-current.png)

</div>

*Caption: Some examples of the original action plan cards*

<!-- END PLACEHOLDER -->

## What we changed

### The new design uses common components and patterns.

We rebuilt each action as a [summary card](https://design-system.service.gov.uk/components/summary-list/#summary-cards). The card has a title, actions in its header, and a summary list of details.

We also built a second version using a plain [summary list](https://design-system.service.gov.uk/components/summary-list/), without the card styling. Looking ahead, we could test the two variants with real users. Both versions are available in the prototype.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
<div class="app-image-row">

![A summary card component from the gov.uk design system](/action-plan/redesigning-cards-for-action-plan/reason-show-more.jpg)
![A summary list component from the gov.uk design system](/action-plan/redesigning-cards-for-action-plan/action-summary-list.jpg)

</div>

*Caption: An action point shown both as a summary card and list components*

<!-- END PLACEHOLDER -->

### Clearer rules for card actions and row actions

We separated actions into 2 types.

Card actions apply to the whole action, for example "Complete action" or "Withdraw". They sit in the card header.

Row actions apply to a single piece of information and sit at the end of its row. These are:

- "Change" for the "Required by" date
- "Change" or "Mark as complete" for the chaser task, depending on whether a date has been set
- "Mark as read" for the reason for the last CPS update

The subject matter expert confirmed that the message to mark as read is the reason for the last update. That's why "Mark as read" belongs to that row and not to the whole card.

### Shortening long update messages

The reason for last CPS update can be very long. We now show only the first few words, followed by a "Show more" button. When the text is opened, the full message is shown with a "Show less" button at the end.

We first tried the [details component](https://design-system.service.gov.uk/components/details/). It couldn't do what the design needed, because its toggle always sits before the content and can't move to the end of the text. Instead, we used a simple button that tells screen readers whether the text is expanded.

The lesson: check what a standard component can and can't do before you commit to it.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
<div class="app-image-row">

![A summary card component from the gov.uk design system](/action-plan/redesigning-cards-for-action-plan/chaser-task-none.jpg)
![A summary list component from the gov.uk design system](/action-plan/redesigning-cards-for-action-plan/chaser-task-mark-complete.jpg)

</div>

*Caption: The new chaser task row showing both states*

<!-- END PLACEHOLDER -->

### Adding a chaser task

The redesign included a note saying users needed to be able to mark a chaser task as complete. We added a "Chaser task" row that works the same way as "Required by":

- if no date is set, the row shows "Change"
- if a date is set, the row shows "Mark as complete"

## What we found

Initially, we thought action buttons might depend on the category: police initiated, pre-charge or post-charge.

After reviewing some legacy designs and following up with and SME we found out that category made no difference. The actions on each card depend only on its status, for example:

| Status | Card actions |
| --- | --- |
| Draft | Edit draft, Delete draft |
| Not sent | Send to police |
| New or In progress | Complete action, Withdraw |
| Completed | Re-open |

The same status always gets the same actions, whichever card it's on.

<!-- SCREENSHOT PLACEHOLDER — duplicate as needed -->
<div class="app-image-row">

![A summary card component showing an action card with the staus of new](/action-plan/redesigning-cards-for-action-plan/roti-new.jpg)
![A summary card component showing an action card with the staus of not sent](/action-plan/redesigning-cards-for-action-plan/roti-not-sent.jpg)
![A summary card component showing an action card with the staus of completed](/action-plan/redesigning-cards-for-action-plan/roti-completed.jpg)

</div>

*Caption: Cards with different statuses showing their actions*

<!-- END PLACEHOLDER -->

## What we have not resolved yet

- **This prototype focused on consistent patterns and components.** None of the actions are connected to real data yet, so we've confirmed how the cards look but not how their ongoing journeys resolve.

- **We haven't done user research on this design.** We’d like to test it with users, especially on action plans with a lot of items. Furthermore, there is a bulk action journey that could be optimised.

