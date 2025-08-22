---
title: Using Service Explorer
weight: 2
---

# Using Service Explorer

The Service Explorer is a cataloguing and analysis tool built in [Airtable](https://airtable.com/). We use it to store data about services using GOV.UK Frontend, and we analyse this data by creating visualisations and reports.

This tool is useful for:

- our team, who want to measure how the GOV.UK Design System is used in services and make decisions
- our regular stakeholders, who want to understand the value of the GOV.UK Design System
- other stakeholders, who want to use the GOV.UK Design System to measure specific deliverables or factors

## Using Service Explorer to analyse service data

### Setting user permissions

The GOV.UK Design System team have a [team plan](https://support.airtable.com/v1/docs/airtable-plans#team-plan) for Airtable, giving us access to useful features like automations and interface design. We only have access at an admin level, through the Design System team’s announcements email address. You can find the credentials in the team’s Bitwarden account.

We can add collaborators as read-only viewers if we want to share interfaces. Read-only viewers can create a free account on Airtable but cannot edit the data.

> Do not invite collaborators as anything more than read-only viewers, and do not change 
> anyone’s permissions beyond read-only. Our current plan charges us for any collaborators above
> read-only, and Airtable does not notify you that you are about to make a billable change.

Our primary data source is our **Services** table. This is a manually maintained list of service information, which we automatically check on a weekly schedule. Using [WebPageTest](https://www.webpagetest.org/) lets us get technical details about the service and build a timeline of changes in service data.

### Collecting service data 

Service data includes data we maintain manually and data we collect automatically through WebPageTest. The data we collect through WebPageTest is a combination of data included by default from WebPageTest and data unique to `govuk-frontend`, which we collect using [WebPageTest custom metrics](https://github.com/alphagov/design-system-custom-wpt-metrics).

The manual service data includes the:

- entry URL
- name of the service
- organisations, such as the Ministry of Justice or the Environment Agency
- tags, such as whether a service is a [Top 75 service](https://www.gov.uk/government/publications/roadmap-for-digital-and-data-2022-to-2025/transforming-for-a-digital-future-2022-to-2025-roadmap-for-digital-and-data#annex-top-75-services)

The automated data includes:

- the GOV.UK Frontend version
- the framework, such as GOV.UK Frontend or precursors to GOV.UK Frontend, such as GOV.UK Elements
- what type of logo a service is using (for example, whether it’s using the new Tudor crown and ‘middot’)
- whether a service is using the June 2025 GOV.UK rebrand
- when the June 2025 GOV.UK rebrand was first detected
- if and how the service is using the Service navigation component
- if and how the service is using the deprecated Header component navigation
- if the service is using [the new type scale feature flag](https://design-system.service.gov.uk/styles/type-scale/)
- what technologies a service is using
- a service’s [Lighthouse](https://developer.chrome.com/docs/lighthouse/) scores, which includes scores for accessibility, performance and best practice
- what [Axe](https://www.deque.com/axe/) violations the service is incurring, if any
- the console output of the service

If WebPageTest is not able to retrieve any data (for example, if the service fails to load), the table cell is left blank.

### Analysing service data

We can assess this data using [interfaces](https://www.airtable.com/guides/collaborate/getting-started-with-interface-designer) in Airtable, a feature that lets us filter and visualise our data in a specific view like a dashboard or a sorted list. You can find our interfaces and create your own in the **Interface** tab in Airtable. 

### Managing service data

We manage data in the Service Explorer across 4 main tables:

- Services: the list of services themselves
- Organisations: a list of organisations to which the services belong
- Snapshots: every instance of a check we’ve done on a service in WebPageTest
- Checks: a set of dates on which we’ve run scheduled checks and the snapshots produced from them

#### Using the Services table

The **Services** table pulls in the data from the latest snapshot of that service and displays the data in its record using [lookup fields](https://support.airtable.com/v1/docs/lookup-field-overview). This gives us an up-to-date instance of a service at any given time. Each snapshot record has a **Taken** field, generated when the snapshot is added, which can be used to identify the latest snapshot and plot snapshots of a service over time.

The data being available both statically (in services) and over time (in snapshots) allows us to manage the data appropriately when building interfaces. For example, if you wanted information about the number of services in each organisation, you would use data from the **Services** table. If you wanted to plot a graph of adoption of the Service navigation component over time, you would use the **Snapshots** table and organise snapshots by the **Taken** field.

#### Using the Checks table

The **Checks** table is a list of dates showing when we ran our scheduled checks on our service list, including links to the snapshots taken during that check. We do this to make sure when we’re plotting changes in our service data over time that we’re measuring each point against a broadly equal number of records. This avoids a limitation of Airtable - it’s hard to cross-reference service data as it was at a point in time unless there are snapshots taken of a given service at that point in time. For example, we could do a full check of all services one day, then test one service the following day and a full check the day after that. A graph would show the second day as only one piece of service data in the dataset, resulting in an inaccurate graph.

### Automating service testing

We use Airtable’s [Automations](https://www.airtable.com/platform/automations) feature to automate the testing of services and the generation of data and records in our tables. We maintain 4 automations, which interact with each other.

1. When a new service is added, create a new snapshot record linking to that service.
2. When a snapshot record does not have a WebPageTest ID but is linked to a service, run a script to call the WebPageTest API to trigger a test on that service and update that same record with a WebPageTest test ID and a test status code.
3. When a snapshot record has a test ID, a status other than 200 (meaning the test has not finished running) and the ‘is stale’ field is `true`, attempt to get the results of that test and update the same snapshot with the results.
4. At 8am every Thursday, create a new snapshot for all services with a corresponding check and service entry URL.

These automations are structured so that 1 and 4 will trigger 2, and 2 triggers 3.

The **Snapshots** table contains a [formula field](https://support.airtable.com/v1/docs/formula-field-reference) named ‘is stale’, which returns `true` when about 15 minutes has passed since the snapshot record was last modified. We do this to avoid 2 issues with getting data from WebPageTest. The first issue is that tests take some time to run and vary in how long they take, so the initiation we do in automation 2 is extremely unlikely to return a completed test. The second issue is that Airtable only triggers an automation on the same record once, unless the record is changed. Because the ‘is stale’ field counts as a change, this re-triggers the automation until the WebPageTest test is finished, which will change the record to stop triggering the automation.

### Dealing with challenges when analysing services

Checking services can be challenging and not always 100% reliable because of the variability in how services are built and managed. You should be aware that services change, sometimes quite often.
 
Services may be replaced with content journeys on GOV.UK and redirect there, and organisations may spin up and tear down services frequently in response to what’s happening in their policy area.

Services may be behind a login screen, often from a different service like GOV.UK One Login or Government Gateway, meaning our tests are run on that login service rather than the service we want to test.

Services may have security measures in place to prevent bots accessing their service and conducting malicious attacks. WebPageTest is a system which mocks human interaction during testing, so these security measures may affect us even though we’re not malicious.

Services will sometimes apply the changes we’re looking for incorrectly, so they’re ‘working’ but aren’t in the places we expect. For example, if we were looking for a CSS class that we expect to be on the `html` element but a service puts it on the `body` element instead.

Services may use build pipelines that reconstruct `govuk-frontend` and make things we check for harder to locate. For example, using a build process which obfuscates CSS classes into random strings.

## Terminology

We use the following terms in the Service Explorer tool:

- Service Explorer: The name of the tool which lets us analyse data from services
- Service: A website that is part of the ‘GOV.UK estate’ - this is mostly websites with a ‘[name].service.gov.uk’ domain name, but there are many outliers 
- Scheduled check: An automated, scheduled task in Airtable that sends all our recorded services to WebPageTest to collect service information
- Snapshot: A collection of information about a service at a specific point in time, following a scheduled check
- Entry URL: The URL for a given service that we send to WebPageTest - there is a chance this will not be the same URL analysed by WebPageTest if the entry URL redirects to a different URL, in which case WebPageTest will end up testing that ‘final’ URL
- Organisation: The body or general entity which owns and operates one or more services
- June 2025 GOV.UK Rebrand: The initial update to the GOV.UK brand, which was launched in June 2025

You will also see terms that are unique to Airtable and WebPageTest. You can learn more about these in the Airtable API documentation(https://airtable.com/developers/web/api/introduction) and the WebPageTest documentation(https://docs.webpagetest.org/).

Common Airtable terms include:

- Automation
- Base
- Tables
- Interfaces
- Dashboards
- Base
- Record

Common WebPageTest terms include:

- Lighthouse
- Test
- Status code
- Results code
