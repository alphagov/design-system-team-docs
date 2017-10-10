# Slack

## The Seal

The seal will post to Slack every morning with a list of PRs that need
reviewing. This is managed via the [seal config] which specifies a list of users
and the channel to post to.

PRs that include 'DO NOT MERGE’ or ‘WIP’ in their titles will not be included in
the list.

## GitHub integration

We have a GitHub integration to post ‘real-time’ activity from our core repos to
the channel.

This can be managed by changing the [GitHub integration config].


[seal config]: https://github.com/binaryberry/seal/blob/master/config/alphagov.yml
[GitHub integration config]: https://govuk.slack.com/services/B323V30AK
