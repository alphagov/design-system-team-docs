---
title: Common support responses
weight: 21
last_reviewed_on: 2023-09-04
review_in: 3 months
---

# Common support responses
We often receive queries and requests through our support channels that:

- are mundane requests or tasks that have common responses
- we are not best placed to answer.

Below is a list of the most common responses and redirects that we can use.

You can also check if there’s a relevant [government community] to refer users to.

## Generic responses

### User has not responded for 5 working days

Send a message and close the ticket:

> We haven’t heard back from you for a while so we are going to close this support ticket. If you require further assistance on this issue you can respond to this message which will reopen your ticket.
>
> Additionally, please feel free to open a new support ticket at any time if you have any queries regarding the GOV.UK Design System by emailing govuk-design-system-support@digital.cabinet-office.gov.uk.
>
> Best regards,
> The GOV.UK Design System team.

### Anything that contains PII (personally identifiable information)

If an email contains PII, we must delete it from our inbox. For tickets in Zendesk already you need to assign user support escalation and ask them to deal with it.

1. Ask all team members to delete the email(s) from Gmail and empty their bin.
2. Respond to the user with the response shown below
3. Set Assignee to 2nd Line--User Support Escalation, Primary to "Not for Team" and Secondary to "None of the above"
4. Add internal note asking User Support Escalation to redact
5. Submit as open 

>This email address belongs to the GOV.UK Design System team. We provide support to people who work in the government.
>
>We cannot give general advice to the public. We do not have access to information about you held by government departments.
>
>Data protection legislation prohibits us from storing the type of personal data you have shared with us; therefore the data has been deleted from our systems.
>
>If you need support with a government service, please use the contact form on GOV.UK and they will be able to direct you to the right place: https://www.gov.uk/contact.

### Empty email

This will usually have the heading: “--To unsubscribe from this group and stop receivi…”, with no body text.

Check the original email to make sure it’s empty, and check that the entire email hasn’t ended up as the heading.

Then, simply close the ticket.

## Redirects and Not For Team

### User requires a specific government service

> I have submitted my tax returns 2 weeks ago but have not received confirmation that you have got them

- Set [Design System] Primary to “Not for Team”
- Set [Design System] Secondary to “None of the Above”
- Set Assignee to 2nd Line--User Support Escalation
- Include internal note if appropriate
- “Submit as open”

### Service standard and service assessment queries

> Our service isn’t going to be on GOV.UK so do I have to meet point 13 - “Make user experience consistent with GOV.UK” - in my service assessment?

Direct the user to contact their department’s assurance team. 

If they aren’t sure who that is, or their departmental assurance team is unsure of an answer, advise the user to contact the assessment team at CDDO: dbd-assessments@digital.cabinet-office.gov.uk

### Start pages

The Start using a service pattern says that the content team at GDS is responsible for creating mainstream start points on GOV.UK.

Service teams are encouraged to first get in touch with their own organisation’s content team who can put them in touch with the content team at GDS and help guide the conversation.

Redirect: govuk-enquiries@digital.cabinet-office.gov.uk

### General GDS query

Point the user to the [GDS Request a thing] page.

## Latest release questions

### Browser support changes in GOV.UK Frontend v5

#### In brief, what do these changes mean?

We will stop shipping JavaScript for IE11, but will ensure that nothing is broken in this browser and users can still complete journeys.

We will stop shipping JavaScript and CSS polyfills for versions of IE older than 11, and will not test in these browsers going forward. 

#### How does this relate to the changes to the Service Manual?

The proposal relates to GOV.UK Frontend only. The Service Manual removed the requirement to support Internet Explorer in June 2022. 

We consider the Service Manual to indicate the ‘minimum’ level of support required for compliance, which is why GOV.UK Frontend v4 still supports much older versions of IE. 

#### Will certain components be ‘held back’ for Frontend v5?

This depends on what we’re working on when we’re ready to release v5. At the moment, we’re still working on new things with the assumption that they need to work in IE.

### Projects and users still supporting or using Internet Explorer (IE)

#### What if my project still needs to support old IE or IE11 to a ‘compliant’ level?

Continue using GOV.UK Frontend v4, which will continue to offer compliant support for IE11 and functional support to older IE versions. We aim to support v4 with major bug fixes and security patches for at least 12 months after the release of v5, after which we will reassess the need to support it for longer. 

We intend to maintain documentation for v4 alongside v5 for this period, although we haven’t decided how that will look yet. 

#### Will Frontend v4 be updated for WCAG 2.2?

Version 4 of GOV.UK Frontend will only receive major bug fixes and security patches once version 5 has been released. Changes to support WCAG 2.2 will be made in a future version of Frontend after v5 has been released.

#### Should we tell end users that their browser is no longer supported, or that they’re receiving a degraded experience?

That’s up to what you think is best for your service and users. 

If your service receives a very small number of IE users, you probably don’t need to change anything. 

If your service is still used by a lot of legacy IE users, you probably want to continue using v4 for the time being. 

We have not prepared any components or patterns for this.

#### Will you be supporting IE Mode in Edge?

Not specifically. We only expect users to be using IE11 in situations where Edge is unavailable to them. If they have Edge, we expect them to be using Edge. 

IE Mode is intended to work exactly the same as IE11 from a rendering perspective, so we haven’t considered it separately from IE11. 

In the unlikely event that IE Mode does functionally deviate from IE11, we will probably consider IE11 to be the more important one to support, as:

IE Mode does not come with any built-in devtools, you must use a separate application. This makes it difficult for us to fix anything relating to IE Mode.

IE Mode is only going to be available if manually enabled by the user in their browser settings and on the specific page or domain (or if those settings have been made on their behalf by an enterprise policy, for example). It is intended to be a compatibility tool for legacy sites, and not used for regular web browsing. 

#### IE11 is only being removed from Windows 10. What about older versions of Windows which will still have it?

All previous versions of Windows that run IE11—Windows 7, Windows 8, and Windows 8.1—are now outside of Microsoft’s mainstream support. They no longer receive major updates, and will never be updated to remove IE11. 

We do not take extended support life into account, as this can continue for many years after a browser has virtually disappeared from use. For example, IE7 is still in extended support for some embedded versions of Windows.

The use of IE11 on these older Windows versions only account for a very small number of GOV.UK sessions (0.1% combined, compared to 0.9% for IE11 on Windows 10; in April 2022). 

### Technical questions

#### What technical changes will there be in v5?

In Frontend v5 we will be:

- No longer serving JavaScript functionality for all versions of Internet Explorer.
- Removing JavaScript polyfills that are used to enable functionality in all versions of Internet Explorer.
- Removing HTML, CSS and Sass code that is needed to support IE versions 10 and below.
- Removing the IE8-specific stylesheet and IE8-specific build pipeline.

#### What will happen with HTML/CSS features that require JS polyfills to work in IE11?

For example: details/summary, input[type=”date”], object-fit

- Frontend will no longer polyfill these features where it currently does. 
- We don’t consider these to be breaking changes as most unsupported IE11 features already used in Frontend degrade to reasonable fallbacks (details sections are always open, for example.) 
- These situations should already be accounted for if following [progressive enhancement principles].

#### Will the team start adding HTML/CSS into Frontend that isn’t supported in IE11? 

Initially, no. Some components may look different in IE11, but this will be because we’re no longer shipping JavaScript to that browser. 

In the future we may start to use HTML and CSS features that are not supported by IE11. When we do, we will not treat these as breaking changes. 

#### Will the team start adding JavaScript into Frontend that isn’t supported in IE?

Initially we will only be removing polyfills, however in the future we will start to refactor and incorporate newer JavaScript features that IE does not support. When we do, we will not consider these to be breaking changes. 

We probably won't be using 'bleeding edge' JS features—as we want to avoid transpiling and creating a significant disconnect between the code we author and the code we ship, or having to re-introduce polyfills for other browsers—instead favouring JS features that have been well supported for many years so that there is less detriment to the long tail of users stuck on older Safari or Chrome versions for whatever reasons.

#### How is the Design System team/how should service teams stop serving JS to Internet Explorer? 

We use `<script type="module">` to limit JS loading to modern browsers.

## Accessibility

### Query from outside central gov about accessibility compliance

They should first read <https://accessibility.campaign.gov.uk/>

For questions, direct them to: <https://www.gov.uk/service-manual/communities/accessibility-community>

There’s also the [Accessibility Monitoring and Reporting team] at GDS but we should probably exhaust all other options before sending people to them.

### Accessibility issues with our components / patterns

The GOV.UK Design System styles and components had a DAC audit done in May 2019 and we’ve actioned the things that were raised. You shouldn't need to fix any issues that come up in the audit for Design System components or styles, as long as you're using them correctly, and unless you've extended or modified the component and the modification is causing the issue. For anything that gets raised, it'd be great if you could check if there's an existing issue in <https://github.com/alphagov/govuk-frontend/issues?q=is%3Aissue+is%3Aopen>. If there isn't, it would be great if you could open one. 

## Branding

### Government department branding

>The GOV.UK Design System does not have branding guidelines for departments.
>
>You can request artwork or find further information about branding by emailing the Cabinet Office branding team: branding@cabinetoffice.gov.uk
>
>See the Civil Service branding guidelines website for more information: https://gcs.civilservice.gov.uk/guidance/branding-guidelines/

### Department logos

>The GOV.UK Design System team does not have high resolution logos for departments.
>
>However, you can request artwork or find further information about branding by emailing the Cabinet Office branding team: branding@cabinetoffice.gov.uk
>
>See the Civil Service branding guidelines website for more information: https://gcs.civilservice.gov.uk/guidance/branding-guidelines/

### Adapting GOV.UK Frontend for other branding
>We don’t have any guidance on doing this at the moment. 
>
>There are a couple of things you might find helpful:
>
> - the Sass API reference for changing the colour settings https://frontend.design-system.service.gov.uk/sass-api-reference/#colours
> - the Sass API reference for changing the font https://frontend.design-system.service.gov.uk/sass-api-reference/#govuk-font-family
>
>As headers and footers tend to be the components that deviate most from GOV.UK’s when re-branded, we recommend building them from scratch rather than adapting the GOV.UK one

### Reporting misuse of GOV.UK brand elements (e.g. logo, Transport font)

If a site, service or product (inside or outside of government) is found to be in breach of the [Service Manual’s rules on making a service look like GOV.UK].

Redirect: govuk-enquiries@digital.cabinet-office.gov.uk and/or contact the Policy & Strategy team on Slack for guidance (#govuk-policy-engage)

## Community Resources

### GOV.UK Frontend in other languages / frameworks

See <https://design-system.service.gov.uk/community/resources-and-tools/>

### List of all the design systems & pattern libraries in gov?

We have talked about this. The challenge for us is how we'd maintain it. Our discovery showed that a lot of the resources in question are subject to quite frequent change and, in some cases, sudden retirement. Keeping links working and making sure we have up to date permissions to share and link to this stuff would be quite a bit of work which our team would struggle to do alongside other priorities. That's not to say we wouldn't ever do this, but for now we'll probably stick to linking out to things where relevant from the backlog.

Please see this blog post on government design resources for more information: <https://designnotes.blog.gov.uk/2019/02/14/how-the-gov-uk-design-system-can-work-alongside-other-government-design-resources/> 

(There is this as well: <https://github.com/ctdesign/gov-design-systems-list> Maybe we can hand it out with caveats?)

And this: a list of community developed tools and resources <https://docs.google.com/document/d/1npAUOwumZU2lwpRxSWET5MBpzWAkVSjmy6k_V9TDJio/edit>

## Components

### Date input doesn’t automatically jump to next field

It can be disorientating for users who are using assistive technology, like a screen reader, as the focus is moved unexpectedly.

Also see <https://userresearch.blog.gov.uk/2017/04/18/why-we-care-more-about-effectiveness-than-efficiency-or-satisfaction/>

### Radios example uses bold hint text, but checkboxes examples doesn’t

There is some rationale behind the difference between the two examples. The examples given are not identical, each of the radio’s labels have hints whereas in the checkboxes example there is only one label with hints. The radio example uses bold to help the user identify the option amongst all of the hint text.

### Looking for cookie banner or cookies page code

>We have a cookie banner component available to use here: https://design-system.service.gov.uk/components/cookie-banner/ . The cookie banner and component are based on the approach used on the main GOV.UK website. 
>
>If you aren’t sure what approach to take, I would recommend talking to the privacy expert within your department about what actions you might need to take to meet standards for cookie consent. Unfortunately the GOV.UK Design System team is unable to give you advice or recommendations on that.
>
>The GOV.UK Design System team works hard to ensure that this Design System and Frontend, the codebase it uses, are accessible. Please see the backlog entry here for further details about how we built the component.
>
>ICO guidance - https://ico.org.uk/for-organisations/guide-to-pecr/guidance-on-the-use-of-cookies-and-similar-technologies/

### Has the cookie banner been approved by ICO?

>ICO does not approve specific solutions. Here is the ICO guidance: https://ico.org.uk/for-organisations/guide-to-pecr/guidance-on-the-use-of-cookies-and-similar-technologies/ 
>
>If you aren’t sure what approach to take, I would recommend talking to the privacy expert within your department about what actions you might need to take to meet standards for cookie consent. Unfortunately the GOV.UK Design System team is unable to give you advice or recommendations on that.

### What should I do if my service collects more than essential and analytics cookies? 

>We've included some guidance on how to adapt the cookie banner text and cookie page to different contexts. 
>
>https://design-system.service.gov.uk/patterns/cookies-page/
>https://design-system.service.gov.uk/components/cookie-banner/ 
>
>If you think something is missing or not clear, please raise an issue in our Github backlog. Alternatively, I can raise one for you.

### Can we just include the cookie banner on our landing page?

>The banner should appear on every page in your service, until the user accepts or rejects cookies.

### Do I still need to keep a link to cookies in the footer?

>Yes, we recommend you still have a link to cookies in the footer. The cookie banner won't be visible after the user accepts or declines cookies, so you still need that permanent reference point in case a user wishes to change their cookie preferences.

### Why don’t you provide the JavaScript for the cookie banner?

> We needed to build a component that can be adapted to different technical implementations, across services that collect cookies in different ways and often run other actions such as tracking when a user interacts with the cookie banner.

### The ‘Hide this message’ button has been flagged in an audit

>We changed the recommended cookie ‘hide’ button text on 31st May 2022 to help make the component more accessible.
>
>When a user chooses to accept or reject cookies, a confirmation message should be displayed. We recommend that the hide button text, which was originally ‘Hide this message’, should be updated to ‘Hide cookie message’ to provide more information for users of assistive tech when read out of context.
>
>Teams using the GOV.UK Design System cookie banner component will need to make this change manually in their own service.

### User raises issue or contribution on Accessible Autocomplete repo

Look over the PR first to see if it’s something which falls into the category of [things we do support/pick up]. If not, for an issue:

>Thanks for your suggestion @..............
>
>We’re prioritising bug fixes over new feature development for the accessible autocomplete at the moment so unfortunately we won’t be able to take on / support this work.

And for a contribution:

>Thanks for offering to contribute this work @.... 🙌
>
>We’re prioritising bug fixes over new feature development for the accessible autocomplete at the moment. Since new features add complexity to the component, they increase the maintenance burden and the number of support requests raised. For this reason we won’t be able to accept and support your contribution at this time.

## Contributions

### Contribution of component / pattern that we can’t accept right now

>Thanks so much for offering to contribute this!  We're going to publish a prioritised list soon of the components and patterns that our team are going to be supporting for publication next. We can’t therefore give you an answer on this yet, sorry about that.
>
>Would you be able to share any findings you might have so far in the backlog item? They'll no doubt be helpful to someone. Alternatively, I can raise it for you.  
>
>We’re keen to have this recorded in our backlog so other users can add their thoughts and let us know if they would also find it useful / are also experiencing this issue. This will help us understand the issue better when we come to prioritise it.

### Suggestion for a component / pattern which we’re unable to work on

>Thanks for sharing this component and adding it to the community backlog.
>
>The Design System team are currently working through a backlog of contributions, as well as assessing what will be the priority contributions over the next 12 months. We'll be in touch when we can progress this further. In the meantime, teams across government can benefit from the work you have done via this backlog entry. Thanks again!

### Why we can’t prioritise / work on something

> We’re unable to prioritise work on this right now as we’re currently tackling the epics listed on our roadmap: https://design-system.service.gov.uk/community/roadmap/

If appropriate:
> If there are small, non-contentious updates that you think can be made, you’re welcome to raise them as pull requests? However, we don’t want to guarantee anything – especially as we don’t currently have a [full time content designer on the team / performance analyst / full team / etc.].

If appropriate:
> We have a workaround in place which may solve the issue for you. Would you be interested in trying that?

## Design System Day

During periods running up to Design System Day or following key DS day announcements, you may get questions and comments from users regarding DS day.

### Communications from speakers

You may receive tickets from confirmed or potential speakers for a number of reasons.

- The user is proposing a breakout or workshop
- The user is responding to a mass communication to speakers such as a change in date or confirmation of attendance. The workshop group should update the team on any communications going out to speakers before or as they happen.

If you receive a ticket responding to a mass email:

1. Depending on what the communication was eg: re-confirming based on changed dates, update the relevant sheet where the user is recorded
2. Respond to the user. See below for list of generic responses. If the user has asked a question as part of their response, please ask the workshop group for help.

### Speaker confirms attendance
> Hi {Name}
>
> We're pleased to hear that you can attend Design System Day 2023. We'll be in touch with instructions and a complete agenda closer to the event.
>
> Best regards,  
> The design system team.

## Fonts

### Eligibility criteria for GDS transport

>The use of the ‘GDS Transport’ is specific to services on GOV.UK. You can use it if your service is going to be on one of these domains: 
>
> - gov.uk/myservice
> - myservice.service.gov.uk
> - myblog.blog.gov.uk
>
>If your service meets these requirements then you can also use the font for the service specific offline material, such as paper forms.
>
>If your service is not going to be on those domains then your service should not look like GOV.UK and therefore not use the font.
>
>Could you let us know if your service meets the above criteria?

### Not allowed to use GDS Transport

> If your service doesn't meet the criteria you can still use the other parts of the Design System / GOV.UK Frontend if it makes sense to do so, but you should ensure that it doesn't look like GOV.UK (e.g. by using a different font, using a different header and customising the colour palette). See https://design-system.service.gov.uk/styles/typography/#font for information on alternative fonts you can use.
>
> There is also more guidance about the use of the GDS Transport font in the Service Manual: https://www.gov.uk/service-manual/design/making-your-service-look-like-govuk
>
>There is no “official” recommendation for an alternative font, but our team would recommend: 'Helvetica Neue', Helvetica, Arial, sans-serif; because ‘Helvetica’ is a “better” font (more consistent characters, better kerning) but ‘Arial’ is supported by most operating systems. 

Related: <https://www.gov.uk/service-manual/design/services-for-government-users#logos-and-fonts>

### Allowed to use GDS Transport

> If you want to use the ‘GDS Transport’ webfont, this comes packaged with GOV.UK Frontend and is not available through a CDN. Please do not re-name the font or use any other version of New Transport.
>
>If you want to use the font for static design / prototyping or print material, please let us know and we can provide a version of the font that will be suitable for your use case.

### Fonts for Sketch prototype or paper leaflet

[Download the font files] and attach them to the Zendesk ticket/send them via Slack or email to the user.

Note for reference that these are for v1 of the font. We can’t use the most recent version as it will screw up everyone's sketch files and there’s no way to rename the file where it needs to be renamed. But this shouldn’t matter for prototyping / print.

### Fonts for Axure

>Unfortunately it’s not allowed to upload the GDS Transport font files to Axure’s servers. You should use Arial or other font that’s as close as possible.

Extra context: it shouldn’t be necessary to use Transport in Axure since nothing else is going to behave the same anyway.

## Mailing list
The Design System has a mailing list for users to subscribe to emails about future updates and events.

In most circumstances users can sign up to the mailing list using the link on the Design System homepage, which takes them to a MailChimp landing page. However if for whatever reason that isn’t an option then they can also email the support inbox to ask for us to sign them up manually.

### Blank or unclear sign up request

>We’ve received your request to join our mailing list, but we cannot understand what type of emails you’d like to receive from us.
>
>Please mark an ‘x’ beside the types of email you’d like to receive:
>
> - [ ] new and updated Design System components and patterns
> - [ ] what’s coming up from the Design System team and community
> - [ ] Updates and new about the Prototype Kit
> - [ ] events and workshops

### Existing subscriptions / unsubscribe

>I can see that you’ve already subscribed to receive emails from the GOV.UK Design System team using the form provided.
>
>You’ve asked us to send you emails about:
>
> - [ ] new and updated Design System components and patterns
> - [ ] what’s coming up from the Design System team and community
> - [ ] events and workshops
>
>If you no longer want to receive these emails, you can unsubscribe here:
>https://service.us1.list-manage.com/unsubscribe?u=ada1bae4b177beb9e03502ced&id=367f0a5723

### Design System weeknotes (GDS only)

We send them to the [week-notes google group].

This will send you emails from every team that uses this platform so if you would prefer a single digest email the wiki says:

“If you want to receive all the weeknotes in one digest email, rather than receiving each note separately, you can! Go to the week-notes Google Group > my settings >membership and email settings > change email delivery preference then select ‘combined update’.”

## Meeting requests

Teams from other organisations occasionally ask us to speak to them about the GOV.UK Design System. For example, teams in central and local government, the third sector and sometimes even the private sector.

When we receive a meeting request, use our [meeting requests form] to help:

- decide whether to accept or reject the meeting request
- prep for a meeting we've accepted

## Misc

### JavaScript frameworks, like React

Some potential responses in this [doc about Progressive enhancement].

There’s also the [service manual page].

### What's the difference between service, transaction and content?

Have a read of <https://www.gov.uk/service-manual/design/introduction-designing-government-services> and <https://gds.blog.gov.uk/2018/04/04/what-do-we-mean-when-we-talk-about-services/>

### Using GOV.UK Frontend in internal/admin/caseworking systems

There is some guidance here about services for government users: <https://www.gov.uk/service-manual/design/services-for-government-users>

Also, Amy Hupe who used to work on the GOV.UK Design System wrote about internal services and design systems: <https://amyhupe.co.uk/articles/why-you-dont-need-a-separate-design-system-for-internal-services/> 


We do encourage teams building internal tools to make use of the GOV.UK Design System where it's appropriate for their use case. You should test your application with real users which will help you determine if you're building your application in a way that ensures users can complete their tasks and whether you need to make any adjustments to meet user needs.

We also have an open issue in our backlog about making it easier to create admin systems, case working tools and intranets using the GOV.UK Design System: <https://github.com/alphagov/govuk-design-system-backlog/issues/185>. Feel free to leave any comments about your use case on the issue. Very much related to the above issue, we also have an open issue around changing the default font and colours which you might find helpful: <https://github.com/alphagov/govuk-design-system/issues/1019>

Alos, departmental design systems often document patterns used for ‘admin’ or ‘internal’ services. Some to look at:
<https://moj-design-system.herokuapp.com/>
<https://design.homeoffice.gov.uk/>
<https://design.tax.service.gov.uk/>
<https://ons-design-system.netlify.app/>
<https://hmcts-design-system.herokuapp.com/patterns/perform-an-action>

Some caseworking design patterns from when Chris from Home Office used to  run a cross gov caseworking design community <https://cross-gov-caseworking.herokuapp.com/>

### Application to join the working group - Declined on employability 

>Hi, 
>
>Unfortunately you need to be employed by the UK public sector to be in the working group due to the sensitive nature of the work. This means at this time we would not be able to accept your application to join the working group.
>
>Kind regards

## Spam / Security

### Does the Design System encourage scam sites?

>Sorry you've received that, spam and scam emails are always concerning. In government we do keep an eye out for scam sites and take them down. If you'd like to report one, you can use this link:
>
>https://www.gov.uk/report-suspicious-emails-websites-phishing
>
>As for this repo, unfortunately if people want to run a scam, it's already fairly easy to copy and paste code from any website in order to impersonate it.

## Website

### Code for Design System navigation

The Design System website contains some things that are not in GOV.UK Frontend (for example, the navigation).

If users need to recreate something similar, they can borrow the code from the [Design System repo] on Github.

Emphasise that this code has not gone through the same level of testing or research that the contents of the Design System has.

We have a backlog of components and patterns that aren’t in the design system. This is good place to see other peoples designs and share research. e.g. <https://github.com/alphagov/govuk-design-system-backlog/issues/76>

A hard thing with providing a nav / subnav is that it changes quite a lot depending on the information architecture of the service or website in question. Especially regarding how you handle mobile. But from a generic design standpoint it’s definitely something we want to include eventually.


[Accessibility Monitoring and Reporting team]: https://peoplefinder.cabinetoffice.gov.uk/teams/accessibility-monitoring-and-reporting
[Design System repo]: https://github.com/alphagov/govuk-design-system
[doc about Progressive enhancement]: https://docs.google.com/document/u/0/d/1kF4WPbj7Uhv9Avd8ojjb64O3iK4qxuH4RKuDkwpiu7Q/edit
[Download the font files]: https://github.com/alphagov/fonts/tree/master/fonts/non-web
[GDS Request a thing]: https://www.gov.uk/guidance/contact-the-government-digital-service/request-a-thing
[government community]: https://www.gov.uk/service-manual/communities
[meeting requests form]: https://docs.google.com/forms/d/e/1FAIpQLSdx7xrrnHsGVPxsPtz6DY0f0bVKKc9M41o0Uudr-plBYjAVjg/viewform?usp=sf_link
[progressive enhancement principles]: https://www.gov.uk/service-manual/technology/using-progressive-enhancement
[Service Manual’s rules on making a service look like GOV.UK]: https://www.gov.uk/service-manual/design/making-your-service-look-like-govuk
[service manual page]: https://www.gov.uk/service-manual/technology/using-progressive-enhancement#using-javascript-frameworks
[things we do support/pick up]: https://github.com/alphagov/accessible-autocomplete/issues/430
[week-notes google group]: https://groups.google.com/a/digital.cabinet-office.gov.uk/forum/#!forum/week-notes
