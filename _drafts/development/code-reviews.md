# Code reviews

All changes, no matter how small, should be reviewed by another member of the
team. The only exceptions to this are when working on prototypes where you do
not intend to use the code in production in the future.

Make sure to allow time to review other team members work every day.

## When you open a pull request...

Don’t assign a specific reviewer unless you think it’s important that a specific
person reviews your change.

If the pull request addresses an open issue, you might want to comment on the
issue with a link to the review app. However, you do not need the person who
opened the issue to review or approve the code change.

Once your change has been reviewed by someone from our team you should merge it
using the GitHub interface.

## When you review someone else’s pull request…

Generally, you should avoid reviewing changes that you were involved in making.

Assign yourself as a reviewer before you start reviewing the code changes. This
lets other people know you’re already looking at it.

If you don’t understand the changes they are making or want more context you
should find time with the author to talk through it in person. Consider if
documentation or comments need to be added or updated as a result of the
conversation to help the next person understand it.

You should check that the pull request:

- works correctly
- is understandable
- is compliant with our code standards
- introduces or updates the appropriate tests
- links to the Trello card
- meets (or partially meets) the definition of done in the Trello card
- has good, clear commit messages
- has clear comments and documentation so that you understand what it’s doing
- updates any related documentation or comments

You might also consider:

- if there is a better way of doing things
- if there are any abstractions that should be introduced

When you’re happy with the changes, you should approve it.

Generally, you should leave the actual merging of the change to the original
author.

## After your pull request has been approved...

If your branch is out of date you might need to rebase it. Always rebase rather
than merging the base branch into your branch (unfortunately this is what
GitHub’s ‘update branch’ button does)

Update the relevant Trello ticket for the PM to review the change (or should
this happen before the merge?)

## When you review a Dependabot PR

To make sure the pull request works correctly:

- Read the release notes for the new version and look for changes that would impact our codebase. This is especially important with major releases.
- Look at where in our codebase the package is used with `npm ls` - [see this example, where tests, Rollup and linting used the updated package](https://github.com/alphagov/govuk-design-system/pull/1813#issuecomment-896654240). Test that the parts of the codebase using the package work correctly.
- If the new version is a major release, consider waiting for a few days before updating to see if anyone reports issues that could impact us.

After the first developer to review the pull request approves it, they should ask another developer for a review. The second developer can then approve the pull request, before merging it themselves.
