---
title: Support channels
weight: 18
last_reviewed_on: 2023-09-04
review_in: 12 months
---

# Support channels

Turn on notifications for the following channels and check them regularly through the day:

## Slack

[#govuk-design-system][#govuk-design-system-xgov] channel on Cross Government Slack 
[#govuk-design-system][#govuk-design-system] channel on GDS Slack

You can choose to monitor other channels (like #design or #frontend), but we don’t officially support them.

### Inviting people to Slack

#### Joining Slack

Those with a government email address can just join the [cross government Slack].

There isn’t an up-to-date list of the email domains that have been approved as a government email address for this Slack instance ([this is the last available list][xgov-domain-list] but it’s not being kept up-to-date anymore).

#### Being invited to Slack

Occasionally we have people ask us for access to the cross-government Slack when their email hasn’t been approved as a government email address (see above). 

To invite someone, first try writing `/invite <user's email>` in Slackbot (your private bot channel). The invite request then goes to the Slack workspace admins who decide whether to approve it.

We occasionally get scenarios where `/invite` doesn't work. Typically this is when a user's account has been deactivated, usually because of inactivity. To solve this, go to the [#ask-an-admin] channel on x-gov slack and ask the workspace admins to add or reactivate the user. Once an admin has responded, you can respond in kind to the user.

The good news is that once someone’s invite has been approved by the Slack workspace admins, that person can then invite others on the same email domain themselves by using `/invite`.

#### Single channel guests
We have previously added people outside the organisation to the GDS Support Slack channel in order to provide support if they’re undertaking a piece of work in government but can’t get on cross government Slack. Ideally the period they need to be invited for won’t be very long.

To add a single channel guest:

1. Follow the [guidance to invite the guest on the GDS wiki][guidance-to-invite-the-guest] (under ‘Guest accounts’). Cc in another member of our team for visibility on the IT ticket.
2. Post a message on our team Slack telling them about the single channel guest.
3. When the user is added to the support Slack channel, post the following messages there:
  - “Hello x and welcome!”
  - “Hello everyone. X works for an external organisation on behalf of GDS and has joined this channel temporarily to get support on using the Design System.”

Create a team calendar event for checking the day after the account closure date set in the IT ticket whether the person has been removed from the Slack support channel. If not, leave a message on the IT ticket to remove the user.

## Github

- govuk-frontend [issues][govuk-frontend-issues] and [pull requests][govuk-frontend-prs]
- govuk-design-system [issues][govuk-design-system-issues] and [pull requests][govuk-design-system-prs]

Whilst on daily support, any new pull requests or issues raised that day should be shared with the team.

All new pull requests should be added to the cycle board.

### How to see new issues, PRs and comments on our repos

There is a view you can set up in GitHub which will notify you when new issues / PRs  / comments are added to a repository. This could be useful when you are on support.

Go to your icon in top-right corner > Settings > Notifications

Skip to ‘Watching’. Untick ‘Email’ and tick ‘Web and Mobile’.

Now select the repositories you want to “watch”. This should be:

- [alphagov/govuk-design-system]
- [alphagov/govuk-frontend]

You can watch each of these repositories by selecting the ‘Watch’ drop-down in the top right and selecting ‘All activity’.

To get the notifications view, click on [this link][github-notifications-view]

It should look like this:

![Github notifications view](../assets/images/github-notifications-view.png)

## Email

Emails sent to our support email address are automatically turned into [Zendesk] tickets. If you are part of the support rota you will be given access to Zendesk. See this guide on [how to use Zendesk][Zendesk-help] for more details.

### Mailing list

We have a mailing list for users to subscribe to emails about future updates and events.

In most circumstances users can sign up to the mailing list using the link on the Design System homepage, which takes them to a Mailchimp landing page with a signup form.

However if for whatever reason the Mailchimp form isn’t an option then users can also email the support inbox to ask for us to sign them up.

If a user sends an email asking to join the mailing list, but without having selected any of the options for things they are interested in, we should reply with something like

> Thank you for your interest in emails from the GOV.UK Design System team.
>
> It looks like you have not selected anything under the types of emails you’d like to receive. Could you reply with at least one option selected?

Once the user has clarified which topics they want to hear about you can add them to mailchimp manually by:

1. [Logging into mailchimp][mailchimp]. Credentials can be found in the Design System team’s Bitwarden account.
2. Navigate to Audience (left hand sidebar) > All contacts > Add contacts > Add a subscriber
3. Fill out the Add subscriber form
  - Enter the user’s email address
  - Check the topics the user expressed interest in
  - Check the boxes at the bottom relating to the person giving you permission to email them and to update their profile if they already have one
  - Click subscribe
4. Go back to the ticket and let the user know that they’ve been added:

> We've added you manually to our mailing list with the requested settings. Please feel free to contact us in future if you require further assistance.
