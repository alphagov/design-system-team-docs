---
title: Working with Milestones
weight: 8
last_reviewed_on: 2026-07-31
review_in: 12 months
---

# Working with Milestones

[Milestones] are a GitHub feature for tracking progress across a group of issues or pull requests in a repository.

Each issue or pull request can be associated with one milestone.

## How we use milestones

We use milestones to plan and track releases, including:

- upcoming releases that will include current work
- future major releases, and any work that needs to happen in advance of them

### Using milestones to track upcoming releases

Assigning issues for in progress work to milestones helps us to:

- record decisions about how we'll release particular pieces of work
- identify all of the moving parts that need to be 'ready' before we can publish the release.

If we're using milestones consistently, then once everything in the release view is marked as ready to release, we should be in a position to publish the release.

If you don't yet know what the version number for the next release will be when creating the milestone, use the placeholder `[NEXT]` as the name.

Once we know what kind of release we are shipping, the `[NEXT]` milestone can be renamed to the actual version number.

### Using milestones to track the next major release

Milestones are also useful for remembering work that needs to happen in the next major release.

This is particularly relevant for breaking changes, cleaning up deprecations, removing feature flags, or doing work that we have deliberately postponed until the next major version.

Sometimes we also need to track work that must happen before the next major release.

For example, if we know we want to make a breaking change in v7, we may first need to remember to do preparatory work in v6, such as deprecating the old behaviour. The `v6.x-candidate` milestone can be used for this.

## Using release milestones effectively

### Milestones belong to a repository

Each milestone belongs to a single repository. Because we often want to track work across multiple repositories, we often create milestones in multiple repositories with the same name.

When looking at a milestone in a specific repository you will only see the issues and pull requests from that repository.

However, GitHub Projects treats milestones with the same name as a single milestone when filtering or grouping work.

For example, the ['Releases' view] on our cycle board lets us see related work across repositories in one place, rather than needing to look at each repository separately.

You can also search across the organisation to find issues and pull requests in milestones with the same name across different repositories.

### Create release milestones as you need them

Create a release milestone as soon as it's needed, after checking that it doesn't already exist (it may be called `[NEXT]`).

### Name the milestones consistently

Name release milestones using their semantic version, including the "v" prefix. For example, `v1.0.0`.

Using consistent names for milestones across repos ensures that they'll be grouped together in GitHub Projects.

### Only use release milestones for work that gets released

Only work that gets released should be added to a release milestone. This includes both product and code changes that affect users, and guidance or documentation changes that must be published alongside the release.

For GOV.UK Frontend, this generally means the kinds of changes we would include in release notes, such as:

- new features
- deprecations
- bug fixes

Issues that only affect internal documentation, tests or tooling should not be added to release milestones.

For the Design System, release milestones should include issues for guidance that needs to be published at the same time as a release. They should not include layout changes to the Design System itself, or guidance changes that can be published at any time.

### Prefer tracking issues over pull requests

Associate the issue that represents the work with the milestone, rather than the related pull request. Only associate pull requests with the milestone if there is no corresponding issue.

This matches how we use GitHub Projects and helps avoid confusion.

### Close milestones once the release has been published

Close all milestones that relate to a release once the release has been published. This keeps the milestone list tidy and makes it easier to see which release work is still active.


[Milestones]: https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/about-milestones
['Releases' view]: https://github.com/orgs/alphagov/projects/53/views/53
