---
title: Working with Pull Requests
weight: 8
---

# Working with Pull Requests (PRs)

## Making changes to PRs from external contributors

Occasionally, we need to help a contributor by making changes to their Pull Request before we can merge it. For example, we might offer to rebase their branch against main to save them time, or if they are not comfortable using git rebase.

You should let the contributor know that you are going to make changes to their branch, especially if it involves rewriting history – where possible, ask their permission first. 

Contributors do not have write access to our repo, and so when they raise a PR it comes from [their own fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks) of the repository. This means that the process for making changes is slightly different, as any changes need to be made to their fork.

This requires the user to have [allowed maintainers to make changes to their branch](https://help.github.com/articles/allowing-changes-to-a-pull-request-branch-created-from-a-fork/#enabling-repository-maintainer-permissions-on-existing-pull-requests). This is usually enabled by default, but if you have issues with permissions you may need to check that the user has this option enabled.

The easiest way to make a change to a contributor's PR is to use the [GitHub CLI](https://cli.github.com/). Once installed, you can run `gh pr checkout 1234`, replacing `1234` with the ID of the PR you want to work on.

The `gh pr checkout` command configures git so that changes are pushed to the contributor's fork when you run `git push` from the checked out branch. You can see how this works by running `git config --get-regexp branch.<BRANCH-NAME>`.

Note that:

- you should not specify any additional arguments when running `git push`
- pushing the changes using a Git GUI (for example GitHub Desktop) may not work
- pushing with `--force-with-lease` may not work (but `--force` should)

## Reviewing PRs

Consider who needs to review the Pull Request. If a PR includes code, design and guidance changes it may be appropriate for it to be reviewed by a developer, designer and a content designer. As a courtesy, you should consider at least giving those involved an opportunity to review it if they want to.

### Reviewing a PR from a team mate

PRs need to be reviewed and approved by at least 1 other team member. If you paired on a piece of work with another person, they can review and approve it.

### Reviewing a PR from an external contributor

PRs raised by external contributors need to be reviewed by 2 team members.

When reviewing PRs from external contributors:

- review the code using the GitHub interface before checking out the code and running it locally
- be aware of [supply chain attacks](https://www.ncsc.gov.uk/collection/supply-chain-security) – check any new dependencies, and verify any changes to the [lock file](https://docs.npmjs.com/cli/v9/configuring-npm/package-lock-json)

### Reviewing a PR from Dependabot

Dependabot is configured to automatically raise Pull Requests to update our dependencies on a regular basis. These Pull Requests should be reviewed by developers.

Be aware of [supply chain attacks](https://www.ncsc.gov.uk/collection/supply-chain-security), especially if the maintainer of the dependency has changed (Dependabot usually flags this in the Pull Request).

If you want to check the changes being made to the dependency, use a tool like [Package Diff](https://diff.intrinsic.com/) which shows the difference between the published packages.

The PR should be reviewed by 2 developers if:

- it's a major version bump or the release notes suggest there are breaking changes
- it changes the built site or package
- a developer makes changes to the PR

Otherwise the pull request only needs to be reviewed by 1 developer.

## Merging Pull Requests

In order to merge a Pull Request to the main branch:

- all of the tests have to pass
- the PR has to be reviewed and approved by at least 1 other person
- the changes in the PR mustn't conflict with any other changes that might have been made (for example, if two people both try to change the same paragraph in some of our documentation)

Most of these requirements are enforced by GitHub, so you won't be able to merge the PR unless they're met.

It is the responsibility of the person who merges the PR to ensure that the changes have been reviewed by the right people, and that any concerns raised during the review process have been addressed.

### Merging a PR from a team mate

In most cases, the author of the PR should merge it.

If the author isn't around or free to merge a change, and it is blocking some other work or a release, then someone else from the team can merge it.

### Merging a PR from an external contributor or Dependabot

External contributors (including Dependabot) do not have write permissions to merge their own PR, so the PR should be merged by a team member as soon as all of the requirements are met.
