---
title: Analytics on the Design System website
weight: 1
---

# Analytics on the Design System website

We collect user data from the GOV.UK Design System website to understand how users are interacting with the design system. This helps us to make product and design decisions.

## What we use for analytics

### Google Analytics

We use Google Analytics (GA) to analyse collected user data. We can use GA to assess a wide variety of data, such as:
- number of visits to the Design System website over a period of time
- most viewed pages

GA also lets us visualise the data and create custom reports and explorations.

We have a set of custom explorations for each section of the GOV.UK Design System website:
- [Homepage](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/i6OT6xmzSQ6pI3o0LUGOWQ)
- [Get started](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/igLFn24gQiaxW11ojKlNag)
- [Styles](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/wp1wjBO2Qv-6l8M5CMA5NQ) 
- [Components](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/E5gNNdKjR9m4EOvslm1C-g)
- [Patterns](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/u8oRSD7QSlyXGeQHcj3_RQ)
- [Community](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/VVK6VLsBThSNARxrWAOtZQ) 
- [Accessibility](https://analytics.google.com/analytics/web/#/analysis/a72121642p446981526/edit/S9eRClV4SZi_Ocs4-LfvMw)

If you want to make edits to the explorations, create a copy to make any changes. 

We maintain 2 GA properties:

- [Data from the live website](https://analytics.google.com/analytics/web/#/p446981526/reports/intelligenthome)
- [Data from website previews, such as temporary Netlify links generated from pull requests](https://analytics.google.com/analytics/web/#/p446943224/reports/intelligenthome)

### Google Tag Manager

Google Tag Manager (GTM) lets us collect and configure user data and send it to our GA properties. Through our [GTM container](https://tagmanager.google.com/#/container/accounts/341497290/containers/8094879/workspaces/1000045), we can define events on the website, including:

- what triggers the event
- what information to collect
- how to present that information

These events are recorded in GA, where they can be analysed.

GTM uses 3 main concepts to manage event data: tags, triggers, and variables.

Tags are, functionally, events. The tags let us define:

- what a given event is
- what data we send to GA when it happens

Triggers define when an event has happened. For example, a trigger may fire:

- when a link is selected
- when a user navigates to a particular page
- when a user selects something which matches a given CSS selector

Triggers and tags should have a one-to-one relationship unless you want a trigger to fire 2 different events at the same time.
Variables are the data we want to pass to triggers and tags. GTM includes a lot of built-in events, such as:

- page title
- current URL
- target URL if the user has selected a link

However, we can define our own custom variables. Custom variables use the context of where a trigger happens to define themselves. For example, if your variable is the text contents of an element with a given CSS class, the page where the associated tag or trigger happens is where the variable will look for that element.

Our GTM workspace uses a regex table variable attached to all tags called 'Table - GAID'.  This variable pipes event data to either our live property or preview property, depending on what the page domain is.

## User consent

Both GA and GTM require user consent, either through the cookie banner or the [cookies page](https://design-system.service.gov.uk/cookies/), to set cookies on the website. You can find the JavaScript for handling analytics consent in [cookie-functions.mjs](https://github.com/alphagov/govuk-design-system/blob/main/src/javascripts/components/cookie-functions.mjs). 

For a user's data to be sent to Google, the user must:

- opt into tracking cookies
- have JavaScript turned on
- have any ad blockers turned off

Therefore, the data we collect is always going to be an underestimation.

## Collected events

These tags are set up in our GTM container and sent and stored in our GA properties. Where possible, we try to follow [GOV.UK's analytics event schemas](https://docs.publishing.service.gov.uk/analytics/schema.html) when structuring our tag data.

### Page view

- Event name: page_view
- Description: When a user views a page
- Trigger: A user visiting any page
- Data collected:
    - page_h1: H1 of the page
    - status_code: This only detects if the user is viewing a 404 page by checking if the page H1 is 'Page not found'
    - page_section: Current website section, such as Styles, Components or Patterns
    - query_string: Query string attached to the page's URL

### External link click

- Event name: external_link_click
- Description: When a user selects an external link and leaves the website
- Trigger: A user selecting a link that takes them away from the Design System website
- Data collected:
    - link_url: Location of the external link
    - link_domain: User's location on the website

### Top navigation click

- Event name: top_nav_click
- Description: When a user selects one of the main section navigation links in the website header, such as Styles or Components
- Trigger: A user selecting a link with the CSS class `app-navigation__link`
- Data collected:
    - text: Text of selected link

### Sub-navigation click

- Event name: sub_nav_click
- Description: When a user selects a link in the header sub-navigation on small screens
- Trigger: A user selecting a link which matches the CSS selector `.app-navigation__subnav-item .govuk-link`
- Data collected:
    - text: Text of selected link

### Mobile menu button click

- Event name: mobile_menu_button_click
- Description: When a user selects the **Menu** button to open or close the mobile navigation menu
- Trigger: A user selecting a link with the CSS class `app-navigation__menu-button`
- Data collected:
    - state: Text of selected link

### Sidebar navigation click

- Event name: sidebar_nav_click
- Description: When a user selects a link in the sidebar of website sections
- Trigger: A user selecting a link with the CSS class `app-subnav__link`
- Data collected:
    - text: Text of selected link

### Section navigation click

- Event name: section_nav_click
- Description: When a user selects a link in the 'small screen only' link list at the bottom of section landing pages, intended to replace the sidebar for small screen users
- Trigger: A user selecting a link which matches the CSS selector `.category-nav .govuk-link`
- Data collected:
    - text: Text of selected link

### Site search

- Event name: site_search
- Description: When a user types in the site search
- Trigger: We fire this trigger 'manually' using JavaScript linked to the functionality of the site search autocomplete
- Data collected:
    - text: Search query entered into the search bar at the point a query is triggered. The time between a user entering a query and the search bar returning results is handled by the autocomplete, which approximates when a user has stopped typing
    - section: The title of the returned result if a query returns a single result
    - action: One of 3 possible things:
        - 'click' for the initial click on the search bar
        - 'results' if a query returns results
        - 'no result' if a query does not return anything

### View item list

- Event name: view_item_list
- Description: When the user has entered a search query and a list of results is returned
- Trigger: See site_search event
- Data collected:
    - items: A list of returned search results

### Select item

- Event name: select_item
- Description: When the user selects a returned search result and navigates to that page
- Trigger: See site_search event
- Data collected:
    - items: The selected search result item

### HTML/Nunjucks tab click

- Event name: html_or_nunjucks_tab_click
- Description: When a user selects the HTML or Nunjucks tab in code examples
- Trigger: A user selecting an element with the data attribute `data-track`
- Data collected:
    - tab: Text of selected tab

### Copy code button click

- Event name: copy_code_button_click
- Description: When a user selects the 'copy code' button in code examples
- Trigger: A user selecting an element which matches the CSS selector `.app-copy-button, js-copy-button`
- Data collected:
    - copy_code_button: Which tab was copied from. Uses custom JavaScript to find the nearest instance of `.app-tabs__container`

## Making changes to GTM

All team members can submit changes to GTM, but only developers have the ability to review, approve and publish changes.

### Using workspaces

When working on a change, you should create a new workspace in GTM. This reduces the chance of multiple changes to GTM at the same time overlapping and creating conflicts. You can read more in [Google's documentation on GTM workspaces](https://support.google.com/tagmanager/answer/7059647?hl=en).

### Previewing your changes

Before submitting a change, you should preview your changes using GTM's debug view to make sure they are working as expected and that you have not impacted any other tags. You can read more in [Google's documentation on previewing and debugging changes](https://support.google.com/tagmanager/answer/6107056?hl=en). Remember to accept cookies and turn off ad blockers when testing your changes.

### Review and publishing process

Once you're happy with your changes, you should submit them for review. You can read more in [Google's documentation on publishing and reviewing in GTM](https://support.google.com/tagmanager/answer/6107163?hl=en).

A developer must review, approve and publish the change. You cannot request a review from a group of GTM users, so use our Slack channels, either [the main team channel](https://gds.slack.com/archives/C011V7RAAKY) or [the dev channel](https://gds.slack.com/archives/C0447D0STV0) to request a review from the developers on the team once you've submitted your change. 

When you're reviewing a change, you should communicate directly with the team member who submitted the change to work through any necessary edits together. This is because GTM does not notify users when a change request has changed state (for example, a developer has sent a change back with recommendations). Communicating directly means changes will not be missed.

After a change has been approved, it needs to be published. GTM will take you through the publishing process to create a new version of our GTM container automatically after approving. Creating this new version of the container will delete the workspace created to make and test the change.

You then need to manually update the default workspace by going to the default workspace, selecting **Submit** and then selecting **Update now** on the orange banner in the submit view. See the documentation on workspaces above for more details.

### Adding custom dimensions to reflect your changes

Custom dimensions are how GA recognises custom parameters set up in GTM tags. In order to see custom parameters from tags in GA event reporting, you need to set up a custom dimension for each of your parameters. Only admins can update our custom dimensions so ask a team lead or a developer if you don't have the necessary permissions.

You can read [Google's documentation on custom dimensions](https://support.google.com/analytics/answer/14240153?hl=en) for more details, however for our purposes, to add a custom dimension:

1. in our GA property, go to Admin in the bottom left corner and then to Custom definitions under the Data display heading
2. click the Create custom dimension button in the top right corner
3. give your dimension a name and a brief description if necessary. Keep the scope of the dimension set to 'Event'
4. set the event parameter as the name of the custom parameter that you set in GTM. If your event has been active for over 24 hours, GA may suggest it for you. If not, type it out as it is in GTM

Custom dimensions take roughly 24 hours for GA to start reporting on them. It's recommended that you set up your custom dimensions ahead of deploying your tag changes to minimise loss of data.

## Joiners and leavers process

When a new team member joins, a developer or a team lead needs to add them to GA and GTM. Developers and team leads have the  'Administrator' role in both GA and GTM, which lets them add team members.

When a team member leaves, a developer or team lead must revoke their access to the GA properties and the GTM workspace.

Both these tasks can be handled in the admin interfaces of GA and GTM.
