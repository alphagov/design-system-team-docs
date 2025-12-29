---
title: how to create a sub-issue
weight: 5
---
# How to create a sub-issue

In GitHub we use “sub-issues” for tasks. An issue becomes a sub-issue when it is attached to a “parent” issue, usually a brief.

In the majority of cases, you will create sub-issues for your brief after a planning meeting with your squad. During the planning meeting you will determine the tasks you’ll carry out in order to deliver the brief. These are then created as sub-issues for your brief.

## Choosing the appropriate GitHub repository to create the sub-issue in

The context of the task will determine the repository you create it in.

- for a task specific to GOV.UK Frontend, use the [govuk-frontend](https://github.com/alphagov/govuk-frontend)
- for a task which is regarding GOV.UK Prototype Kit, use [govuk-prototype-kit](https://github.com/alphagov/govuk-prototype-kit)
- for a task specific to the Frontend docs, use [govuk-frontend-docs](https://github.com/alphagov/govuk-frontend-docs)
- for a task regarding the Brand Guidelines website, use [govuk-brand-guidelines](https://github.com/alphagov/govuk-brand-guidelines)
- for a task specific to the team playbook, use [design-system-team-docs](https://github.com/alphagov/design-system-team-docs)

If a task is sensitive and should not be seen by people outside of the team, use [design-system-team-internal](https://github.com/alphagov/design-system-team-internal). This repository is private and used only by members of the Design System team.

If a task is specific to the Design System website, use the [govuk-design-system repo](https://github.com/alphagov/govuk-design-system). If your task cannot be categorised by any of the other repos, also use the [govuk-design-system repo](https://github.com/alphagov/govuk-design-system).

## Creating a sub-issue

**Step 1:** Navigate to the brief you wish to attach a sub-issue to.

**Step 2:** At the bottom of the issue textarea, there is a button labelled “Create sub-issue”. Select the drop-down arrow to choose “Create sub-issue”. This is also how you attach pre-existing issues to a brief by selecting “Add existing issue”. 

**Step 3:** Select the “Internal story template”.

**Step 4:** Give your task a title. This should be verb based, and describe what you are doing. 

**Step 5:** Complete the “## What” section by expanding on the title of task by providing more detail.

**Step 6:** Complete the “## Why” section. This is the most important section of the content as you can explain why you are doing the task. 

**Step 7:** Complete the “## Who needs to work on this” section by listing the disciplines which will carry out this task.

**Step 8:** Complete the “## Who needs to review this” section by listing the disciplines who need to review this task before it can be considered done. This can include roles external to the team.

**Step 9:** Define the “## Done whens”. This is where you should break down the task into actions required to complete it. It can be a simple actions list, or you can you a success criteria format — whatever you prefer!

**Step 10:** Attach “Assignees” to the brief (these are your fellow squad members). This feature may be found either at the bottom of the pop-up window or on the right side-navigation of the issue.

**Step 11:** Add the appropriate labels (guide coming soon).

**Step 12:** Add a “Project” board. In most cases this should be “GOV.UK Design System cycle board”. Your sub-issue will not appear on the [cycle board](https://github.com/orgs/alphagov/projects/53/views/72) unless this has been done.

**Step 13:** Select the green “Create” button to open your issue.

After the sub-issue has been created, double check it has been set up correctly by reviewing the right side-navigation to check all the appropriate metadata is showing. 

Under the “Projects” sub-section, you may need to update the “Status” field on the “GOV.UK Design System cycle board” to “Backlog”.

There is no need to use the “Type” field at present — you can leave this blank.

## Watch a demo

To see a demonstration of this in action, you can [watch a recording of a team learning & development session here](https://drive.google.com/file/d/12lp3NUhYQhS711VXSGTNajmF64OLQ9HP/view?t=4).

The recording also includes an alternate way of attaching an issue to a parent issue via the side-navigation. This is useful when needing to change the parent of an issue.
