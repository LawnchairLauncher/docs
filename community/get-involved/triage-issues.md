# Triage issues

This document defines the official workflow for triaging issues on Lawnchair's GitHub repository. The goal of the triage team is to maintain a clean, organized, and actionable issue tracker, allowing developers to focus on writing code.

We utilize centralized boards to track and organize our development pipeline:

* **Bug and Issue Tracker:** [Lawnchair GitHub Projects (Issues)](https://github.com/orgs/LawnchairLauncher/projects/10)
* **Feature Request Tracker:** [Lawnchair GitHub Projects (Feature Requests)](https://github.com/orgs/LawnchairLauncher/projects/11)

### The triage lifecycle

Every issue follows a structured lifecycle managed by `status:` labels. The primary goal of triage is to move an issue from its initial reported state to a finalized, actionable state.

#### Status labels

* `status: needs triage` is the default state for all new issues, indicating they have not yet been reviewed by the triage team.
* `status: needs info` is used when an issue has been reviewed but is missing critical details from the author, such as steps to reproduce, device specifications, or crash logs. Issues will be closed after one month of no reply.
* `status: needs repro` is applied when an issue has been reviewed and seems valid, but requires independent reproduction or confirmation by other contributors or developers.
* `status: reviewed` indicates the issue has been fully validated, reproduced, and documented. This is the signal that an issue is developer-ready.

#### High-priority labels

Some validated issues may receive a high-priority label to denote their impact:

* `tracking-issue` is used for high-impact bugs or highly requested features. These issues serve as the official curated list of project priorities and are used in addition to the `status: reviewed` label. You can view the list of current [Lawnchair tracking issues on GitHub](https://github.com/LawnchairLauncher/lawnchair/issues?q=is%3Aissue+is%3Aopen+label%3A%22tracking+issue%22).

#### Topic-specific labels

We use specific category labels to route complex subsystems to the correct developers:

* `quickswitch issue` is applied to problems involving the root-based QuickSwitch integration for system Recents.
* `gesture issue` is used for non-root gesture navigation problems, which are often related to OEM-specific system behaviors.

### The triage process

{% stepper %}
{% step %}
#### Find an issue requiring review

Start by selecting an issue that has not yet been processed. You can find the list of pending reports on the [GitHub triage list](https://github.com/LawnchairLauncher/lawnchair/issues?q=is%3Aopen+is%3Aissue+label%3A%22status%3A+needs+triage%22+sort%3Acreated-asc).
{% endstep %}

{% step %}
#### Investigate the report

Analyze the issue to determine its correct state:

1. Search the repository (especially existing `tracking-issue` reports) to see if the problem has already been reported. If it is a duplicate, recommend closing the issue (e.g., `Recommendation: Close as duplicate of #1234`).
2. Verify if the author completed the issue template. If the report is completely empty or incomprehensible, recommend immediate closure. If it is simply missing crucial details, recommend requesting the information (e.g., `Recommendation: Change status to 'needs info'. Please provide a screen recording`).
3. If the report is clear, attempt to reproduce the behavior using the latest [Lawnchair Nightly build](https://github.com/LawnchairLauncher/lawnchair?tab=readme-ov-file#development-builds). For feature requests, assess if the concept aligns with the project's goals.
{% endstep %}

{% step %}
#### Make a recommendation

Post a comment with your findings and a clear recommendation for the core team:

* `Recommendation: Change status to 'reviewed'. This is a valid, reproducible bug.`
* `Recommendation: Change status to 'needs repro'. The issue seems valid but requires independent testing on different hardware.`
* `Recommendation: Change status to 'reviewed' and add 'tracking-issue'. This is a major regression affecting multiple users.`
{% endstep %}
{% endstepper %}

#### Workflow for the core triage team

Members of the core triage team have permission to apply labels, move items on the project boards, and close issues directly. They may perform these actions based on their own investigations or by reviewing the recommendations left by other contributors.
