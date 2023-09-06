---
title: Support branches
weight: 2
last_reviewed_on: 2023-09-04
review_in: 3 months
---

# Support branches

Use support branches to:

- publish a new release of previous major versions of GOV.UK Frontend

- publish a 'hotfix' release of GOV.UK Frontend without including other unreleased changes on the `main` branch

Once a support branch has been created it should be maintained in parallel to the `main` branch. The support branch will never be merged into the `main` branch.

## Using support branches for previous major versions

You can use a support branch to publish new releases of a previous major version.

For example, if we found a bug that affected all versions of GOV.UK Frontend between v4.6.0 and v5.1.0, we might choose to release a new version of v4 as well as a new version of v5 so that users stuck on v4 can get the fix without needing to upgrade to v5.

We might also use a support branch so that we can continue to release when we have unreleased breaking changes on the main branch during the initial development of a new major version.

![Graph showing the main and support branch running in parallel. The support/4.x branch diverges from the last v4 tag on the main branch. After the point the two branches diverge, the main branch has tags for v5.0.0 and v5.0.1 and the support branch has tags for v4.6.1 and v4.6.2.](/images/support-branch-prev-major.svg)

<!-- 
gitGraph
    commit
    commit tag: "v4.6.0"
    branch "support/4.x"
    checkout "main"
    commit
    commit
    commit
    commit tag: "v5.0.0"
    commit
    checkout "support/4.x"
    commit
    commit tag: "v4.6.1"
    checkout "main"
    commit
    commit
    commit tag: "v5.0.1"
    checkout "support/4.x"
    commit
    commit tag: "v4.6.2"
-->

There should only be one support branch for each previous major version. The support branch should be named using only the major version number, for example the branch name for the v4 major release would be called `support/4.x`.

Because the support branch will never be merged back into the main branch, any changes that affect both current and previous major versions require multiple pull requests. Raise one pull request against the support branch for each previous major version, and one against the main branch for the current major version.

## Using support branches for hotfixes

If we discover a bug in GOV.UK Frontend that we urgently need to fix, we can use a support branch to release just the fix without including other unreleased changes on main.

(Ideally the main branch is always kept in a releasable state, but we might still prefer to release a set of changes together to provide a more coherent release, or hold off releasing a change until we have accompanying documentation ready to go.)

Support branches should only be used to fix bugs, not to introduce new features.

![Graph showing the main and support branch running in parallel. The support/4.6.x branch diverges from the v4.6.0 on the main branch. After the point the two branches diverge, the main branch has unreleased changes and the support branch has a tag for v4.6.1](/images/support-branch-hotfix.svg)

<!-- 
gitGraph
    commit
    commit tag: "v4.6.0"
    branch "support/4.6.x"
    checkout "main"
    commit
    commit
    commit
    checkout "support/4.6.x"
    commit
    commit tag: "v4.6.1"
-->

The support branch should be named using the major and minor version number of the previous release. For example, if the last release was v4.6.0 and we expect the unreleased changes on the main branch to go out as part of v4.7.0, the support branch should be named `support/4.6.x`.

Make sure that the bug is also fixed on the `main` branch, otherwise the bug will be introduced in the next release. This may mean you need to raise a second pull request with the same changes against `main`.

## Creating a support branch

If the support branch doesn't already exist, create it by following these steps.

1. Make sure you have all tags in our local version of the repo by running `git fetch --all --tags --prune`

2. Run `git checkout tags/v<LAST RELEASED VERSION NUMBER> -b <NAME OF SUPPORT BRANCH>`. For example, `git checkout tags/v4.6.0 -b support/4.x`

3. Push the support branch to GitHub. You should push the branch without making any further changes.

4. Set up [branch protection rules] for the support branch.

    When using support branches for hotfixes, the branch protection rules should be the same as the branch protection rules for the `main` branch.

    When using support branches for previous major versions, the required status checks should be configured to match the status checks that run on the branch.

## Making changes to a support branch

Before making changes:

1. Check out the support branch

2. Run `nvm use` to make sure you're using the right version of Node.js and npm, then run `npm install`

3. Given there may be significant differences between the development environment in main and the support branch, run the tests to make sure everything works as expected before making changes

4. Create a new branch based on the support branch which you'll use to raise the pull request

If you are releasing a fix for a bug that has already been fixed on the main branch, you can then cherry-pick the commits that fix the bug onto your new branch.

Otherwise, make whatever changes are required and then commit your code changes, before raising a pull request with the support branch as the target branch

Remember that you might also need to make the same change to the main branch or other support branches.

## Releasing from a support branch

The release process may be different from the release process used on the main branch, especially when releasing from a support branch for a previous major release. You should follow the documentation from the support branch to publish a release.

If you're publishing a release for a previous major version, do not tag this release as the 'latest' release on npm. Instead, give the tag the format latest-v<major-version-number>, for example, `latest-v4`.

## Keeping the changelog on the `main` branch up to date

The changelog on the `main` branch should include the changes from all releases, including releases published from support branches.

Raise a pull request to add the release notes to the changelog on the `main` branch.

Immediately after the version number heading, add a note:

> Note: This release was created from the `<SUPPORT BRANCH NAME>` branch.

[branch protection rules]: https://docs.github.com/en/enterprise-cloud@latest/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches
