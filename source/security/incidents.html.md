---
title: Incidents
weight: 1
last_reviewed_on: 2024-07-10
review_in: 6 months
---

# Incidents

An incident is an unexpected event or error which disrupts the design system as a service. These can prevent users from accessing our guidance and code, impact government services, or threaten the security and trust of service teams and end users. When incidents happen, we need to be able to identify them and respond to them.

## Identifying an incident

It's important to be able to identify when an incident is happening so that we can start responding to it. Not noticing or responding to incidents promptly can increase their severity. At the same time, not every issue is an incident. Some useful things to look for when identifying something as an incident are:

- risks or breaches to the security of users or the team
- users not being able to use the design system, either in part or at all
- end users not being able to use services as a result of their use of the design system or govuk-frontend
- risks to the reputation of services or the design system

Additionally, consider if a given issue needs to be solved immediately or if the design system is still able to operate securely with a given issue in place.

### Examples of incidents

- All or part of the design system website being unavailable
- The design system website being defaced
- One or more of our platform accounts being compromised eg: npm, mailchimp, bitwarden
- Malicious code being shipped in govuk-frontend
- Linking to a malicious resource in our documentation eg: a port of govuk-frontend that contains malicious code
- A serious accessibility bug is shipped/discovered in govuk-frontend

### Examples of things that are not incidents

Note that it's still valuable to fix issues like these ones promptly but they don't need to be treated as incidents as they don't seriously impact the design system service.

- Inaccurate information on the design system website
- A non-blocking bug in govuk-frontend code
- An accessibility bug in govuk-frontend that doesn't block users from using services
- A user using the design system inappropriately
- A user needing technical support with the design system or govuk-frontend

## Responding to an incident

Once something has been identified as an incident, the most valuable thing to do is attempt to resolve it. However, it's important to follow procedure so that we can properly document and manage incidents during and after they happen.

Incidents take priority over all other work.

### Let the team know

The first thing to do is let the team know an incident is happening. Post a message in #design-system-team-channel on Slack with a summary of the incident in progress. Use '@here' so that the whole team is aware.

### Establish an incident team

You should assign 2 roles to help manage the incident:

1. An incident lead. This is someone who will coordinate the incident from discovery to resolution. It's recommended to pick an incident lead based on expertise, availability and knowledge of the problem.
2. A comms lead. This person will be responsible for communicating the incident and its status to the team, across our community channels and to key stakeholders.

Incidents are varied and can require different roles to resolve. You also may discover exactly which roles you need as the incident progresses. It's recommended to request roles on the team as you need them.

### Start an incident report

The incident team at this point should start an incident report so that they can keep track of the incident, its impact, its severity, a timeline of events and, once resolved, a list of actions taken out of an incident review. You can find a template for incident reports, as well as a record of all previous incidents by year, [in the INCIDENTS folder in the team drive](https://drive.google.com/drive/u/0/folders/1plXDUGFIoyzWubWNC9J_IjMiEN8eh9pO).

The nature of incidents means that you may not have time to keep the report up to date as the incident is happening. If the incident team are unable to do this, you should update the incident report at the earliest opportunity.

### Decide on severity

You should decide on a severity score for your incident as soon as possible. We have 4 levels of incident severity:

| Priority | Example                                                 |
| -------- | ------------------------------------------------------- |
| P1       | Malicious code in govuk-frontend                        |
| P2       | Malicious package masquerading as govuk-frontend        |
| P3       | Design system website is down                           |
| P4       | Blocking bug introduced into a govuk-frontend component |

Once severity is identified, add it to the incident report. It may take a while to identify severity or the severity may change. A severity score should be decided at least before the incident review, but ideally much earlier.

### Inform key stakeholders

It's important to inform the DSP senior management team (SMT) about the incident as soon as possible, especially for P1 and P2 incidents. SMT can advise if further escalation is needed.

Send an email to dsp-incidents@digital.cabinet-office.gov.uk with a summary of the incident to inform SMT and other key parties.

If you are dealing with a [cyber security incident](https://www.ncsc.gov.uk/section/about-ncsc/incident-management) that affects the security of the platform or our users and/or their data, the CO Digital team should also be informed so that they can assist if necessary. Include report@digital.cabinet-office.gov.uk in your email to dsp-incidents to inform cyber.

You can read more about incident management in DSP in [DSP's Incident Management doc](https://docs.google.com/document/d/1V33F8_1Jw2KoOMzRWCTbauDtHY9tvVK_Od1uJ5WrcxI/edit#heading=h.8ot1tclehhda). This doc includes details on out of hours escalation where, very rarely, we need service teams to resolve extreme P1 issues immediately, outside of working hours.

### Inform our users (if appropriate)

It can be valuable to inform our users if an incident is or has taken place, especially if it's a security issue and/or we want our users to take action in response. Note however that it's not always appropriate. For example, if the design system website was defaced we don't want to highlight this as this may inadvertently drive users to the website, potentially increasing the impact of the incident. Decide as a team if you want to provide comms to our users. If in doubt, let our users know.

You should post comms in the #govuk-design-system channels on both GDS and cross-gov slack.

Don't send comms to the mailing list as service disruption isn't one of the options users have signed up to get emails about.

### Tackle the incident!

Finding the root cause, actioning and finishing an incident can take a variable amount of time, anywhere from a few minutes to several days. Even if an incident is taking a while to resolve, avoid working outside normal hours to resolve it. Instead, try to establish ways to mitigate the issue in hours until it's resolved. For example, if there's malicious code in a version of govuk-frontend, advise users to use a previous version until you remove the malicious code.

Additionally, continue to keep stakeholders, the team and (if appropriate) users informed. DSP SMT will be able to provide additional support if an incident is taking a while to resolve and advise if out of hours support is necessary.

## After an incident

Once an incident is resolved, you should have a complete report from which to work from for an incident review. If your report isn't complete, complete it as soon as possible after the resolution of the incident.

### Is my incident actually resolved?

Some incidents can be de-escalated quickly but have a long tail of extra actions and 'clean up' following a single major fix. For example if there's malicious code in govuk-frontend which we link to in documentation, the primary fix would be removing the malicious code and the long tail would be removing it from documentation. It's up to the incident team on when an incident is resolved but if in doubt, if the primary negative impact to the service has been removed, the incident can be called 'resolved' even if there's more to do.

### Have an incident review

There should be an incident review as soon as possible after the incident is resolved. The comms lead will typically organise this but anyone involved in the incident can take this on. Ideally everyone involved in the incident will be present. Where appropriate, you may want to include product managers, delivery managers, members of SMT and others.

A template for running an incident review can be found on the incident report template. The key aims for a review should be:

- establish root cause of the incident
- come up with actions to take to prevent or mitigate event happening in the future

### Create actions from the incident review

Any actions out of the incident review should be written up as issues on github. Assign issues to the appropriate repo based on the actions themselves. For example, an issue around security will go into our internal repo whilst an issue to do with testing on the design system website will go in the design system website repo.

These actions should be tackled as soon as possible. Ideally they are folded into the following work cycle, for example as small stories.
