---
title: Using version control (Git and GitHub)
weight: 7
---

# Using version control (Git and GitHub)

Most of our code and documentation is tracked using a version control system called [Git](https://git-scm.com/). Each of our projects is stored in a separate repository hosted on [GitHub](http://github.com/).

Using a version control system:

- lets multiple people work collaboratively on a set of changes before we publish them, without worrying about overwriting each other's work

- allows us to keep a detailed history of our code and documentation, meaning that we can go back and understand why we made a particular change

Git and GitHub are powerful but complex tools. When working with them it's expected that you'll need some support from other people in the team, especially if you are not a developer. Don't be afraid to ask for help.

The rest of this documentation assumes that you have some basic knowledge of Git, and understand terms like 'commits' and 'branches'. If you haven't used Git or GitHub before, you might want to try going through [GitHub's 'Hello World' exercise](https://docs.github.com/en/get-started/quickstart/hello-world) before reading on.

## Repositories

Our repositories are part of the 'alphagov' GitHub organisation. This organisation is shared with multiple teams across GDS.

[Our repos](https://github.com/topics/govuk-design-system-team) are tagged with the `govuk-design-system-team` label.

## Branches

The default branch for each of our repositories is called `main`. This is the branch that users will see by default when they visit the repository on GitHub.

The `main` branch is also an important branch in most of our projects, for example:

- the Design System and Frontend Docs websites will be updated whenever the `main` branch for their respective repo changes.

- when we do a release of GOV.UK Frontend, it's usually done from the `main` branch (or a support branch).

The main branch is protected using [branch protection rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches). This means that you can't make changes to it directly. Instead, you make changes by raising a Pull Request with the changes that you want to make.
