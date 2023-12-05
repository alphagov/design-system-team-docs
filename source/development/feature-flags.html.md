---
title: Feature flags in GOV.UK Frontend
weight: 1
last_reviewed_on: 2023-11-28
review_in: 6 months
---
# Using feature flags in GOV.UK Frontend
Feature flags are a way for us to do a 'soft' release of large scale or experimental actions. They allow users to opt in or out of new or breaking changes. Read this guidance to decide whether a feature flag is a useful addition to your project.

## When a feature flag is useful
Feature flags are useful when the following conditions are true:

- The action is a breaking change
- The action might be a long term project for users
- We are unsure of the action's value

### The action is a breaking change
You should only use feature flags for actions considered breaking changes. A breaking change is something that might require our users to update their serice so that said service continues to work with govuk-frontend. In this case, a feature flag would be a way for users to stay up to date while also being able to opt out of the change for a period of time. Feature flags are not needed for minor releases or new features, such as a new component, because it is simpler to opt out by not using the new feature.

### The action might be a long term project for users
When assessing if a breaking change should be behind a feature flag, consider the scope of work required by the user. A feature flag is useful if the change is very difficult to implement and/or has wide scope. For example, we could decide that all links in govuk-frontend should be green instead of blue. This would impact all links in a service and potentially massively impact a service's visual language. That service team will need to assess their entire service to ensure their design choices still made sense against the new link colour, which could take a long time and interact negatively with any existing service roadmaps.

Feature flags are more useful for wide scope changes that are likely to take a long time to implement in services over changes that might just be difficult to implement. For difficult to implement but short term changes, consider using a pre-release instead (see below section on pre-releases).

### We are unsure of the action's value
This is an alternative to the previous principle on implementation difficulty, where we are not 100% confident of the value of a significant change and need to test it further. In this instance, putting our new/updated feature behind a feature flag would allow us to get early feedback from users willing to use and test it, which enables us to iterate the change with data.

## When a feature flag is not useful
Even if you have a scenario where feature flags might be useful, consider the following before implementing one.

### When releasing the change carries no significant risk
We should avoid using feature flags in most cases. We have alternative systems for communicating big or impactful changes such as feature depreciation where we tell people we’ll be removing something in a future breaking release and breaking releases themselves where users know that by upgrading, they might need to change something in their service. Feature flags should be used as a way to alleviate instances where releasing as normal is challenging.

### We could use a pre-release instead
We also use pre-releases to test breaking changes before a breaking release. A pre-release is a version of govuk-frontend that we release to npm as if its a normal release, but we tag it as a “beta”. For example, instead of the tag 5.0.0, we might use 5.0.0-beta.0. This communicates that it is not the next major version of govuk-frontend, but an early “experimental” version for users to assess with their service.

Pre-releases are ideal for short term investigations or providing early access to the community so they have time to assess a breaking change that might be difficult to implement. Also, pre-releases are generally easier to manage compared to feature flags. Consider if you could use a pre-release instead of a feature flag.

## Types of feature flag
There are 3 types of feature flag. These are defined by the change you’re making rather than implementation of the flag itself.

### Experimental
You can use a flag to create early previews of future releases to help assess their value in a live environment. The flag will enable you to receive feedback from members of the community who’re willing to test early versions in their service.

### Extended release
You can use a flag to facilitate an extended release of a new long term, wide reaching feature or change, while not making it available by default. This allows users to implement large or complex features incrementally while enabling them to continue staying up to date with new releases from our library.

### Extended deprecation
You can use a flag as a 'reverse' extended release where you remove a feature, but keep it available through a feature flag. This is a form of extended deprecation which gives users the option to stop using removed features incrementally. 
**Only use an extended deprecation as a last resort**. While extended releases enable you to roll out changes slowly, extended deprecations are more likely to facilitate bad or outdated practices. In the first instance, you should aim to remove features that are outdated or have issues.

## Additional considerations
Once you’ve established that a feature flag is a useful option for your project, consider the following principles when implementing and operating your flag.

### Try to minimise the scope of the change
Try to have your flag controlling as little as possible. Minimising how much is behind a feature flag reduces the burden of technical management and the impact of the change. Check if there’s anything in your change that you can release outside the feature flag as a separate change.

### Be aware of the need for multiple feature flags
Your feature might impact multiple parts of our tech stack, for example, the Sass and the javascript. If this happens, you should make sure your flag is built so the impacted element states are “synced” where possible. For example, if you have a flag in a component macro that controls the markup of that macro, but also requires a Sass change, your flag should automatically add a CSS class that applies that styling change.

## The lifecycle of a feature flag
Follow these instructions for applying, working with and removing feature flags.

### Implementing a feature flag
You should release feature flags and the change they’re controlling in a minor release (X.**X**.X). As part of this release, you should write automated tests to take account for govuk-frontend having the feature flag on and off. This is to check for unforeseen impacts to parts of the codebase that the flag was not intended to affect.

At this stage, you should create GitHub issues to remove the feature flag in a future major release and add them to the relevant plans.

We use release notes and guidance to provide information on any impacts from a feature flag, how to use it and whether the new change is 'experimental'.

### Working with a feature flag in flight
By turning a feature flag on, you presume a user is opting into the following conditions:

- We might release 'breaking' changes to things behind the feature flag. We will communicate these in release notes.
- Depending on what the feature is and whether it’s experimental or not, the change behind the feature flag might not be 100% operable. For example, there might be bugs or users might provide negative feedback.

It’s important to monitor community feedback on a feature flag, how it's used and how well the change functions, so we can iterate the change before the flag's removal.

### Removing a feature flag
You should maintain a consistent process where you check for active feature flags and decide if you still need them. You should always aim to remove feature flags in the next major version of govuk-frontend after the flag was implemented and consider their removal as a breaking change. For example, if you release a feature flag in 5.2.0, you should remove it in 6.0.0. There are many reasons why this might not always be possible, such as users asking for more time or other breaking changes taking priority. If you cannot complete the removal in the next major release, you should plan to remove the feature flag in a future breaking release.
