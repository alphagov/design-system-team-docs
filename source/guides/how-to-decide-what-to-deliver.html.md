---
title: How to decide what to deliver
weight: 5
---

# How to decide what to deliver

The whole GOV.UK Design System product is a multi-faceted service made up of multiple parts including APIs, code and design assets, guidance and community resources. When adding to our product or solving a problem, it isn't always obvious how we should deliver whatever we're building our users. This guide is intended to help disambiguate the different parts of the design system and how and when to use them to deliver something new.

## What makes up the Design System

The design system is principally made up of 3 separate but intersecting artifacts that help us serve our users in different ways.

### GOV.UK Frontend

The frontend code package that we publish via [NPM](https://www.npmjs.com/). Service teams use this package when building their service to more easily make their services look like GOV.UK and gain access to our styles and components.

We also include APIs which enable our users to:

- manipulate individual components
- gain access to and interact with our styles

### GOV.UK Design System

[Our design system website](https://design-system.service.gov.uk/) which functions as a directory of everything in GOV.UK Frontend, notably our [styles](https://design-system.service.gov.uk/styles/) and [components](https://design-system.service.gov.uk/components/), as well as [common frontend patterns](https://design-system.service.gov.uk/patterns/) in government services such as form questions and pages.

We also provide [ways that users can interact with us and get involved in contribution or community activities](https://design-system.service.gov.uk/community/) as well as [links out to additional digital government resources such as ports of GOV.UK Frontend for specific tech stacks](https://design-system.service.gov.uk/community/resources-and-tools/).

### GOV.UK Frontend docs

[The technical documentation for GOV.UK Frontend](https://frontend.design-system.service.gov.uk/). This is another guidance website focused on technical documentation rather than as a directory of the design system and a 'brochure' for the product the way that the design system website is. This contains:

- technical guides for installing and using GOV.UK Frontend
- guides for managing frontend architecture and staying up to date
- complete API references for our [Sass](https://frontend.design-system.service.gov.uk/sass-api-reference/) and [javascript](https://frontend.design-system.service.gov.uk/javascript-api-reference/)

We expect the audience for the frontend docs to be more technical and at a point in their development process where they're trying to understand how to build something with GOV.UK Frontend.

## How we deliver the design system to our users

The way we provide the different parts of our product each depend on what we are trying to achieve and the work involved.

### Styles

Styles are the foundational design and code elements of GOV.UK Frontend and the wider design system. The include:

- [colours](https://design-system.service.gov.uk/styles/colour/)
- typography, such as our [responsive type scale](https://design-system.service.gov.uk/styles/type-scale/)
- [spacing](https://design-system.service.gov.uk/styles/spacing/)
- [our common page template](https://design-system.service.gov.uk/styles/page-template/)

These are all strongly tied into the code of GOV.UK Frontend. The design system website also includes [guidance on images](https://design-system.service.gov.uk/styles/images/) which we don't deliver via code but is still important information pertinent to users building services using the design system.

Adding or removing a style would be very rare and require a great deal of work to change it across GOV.UK Frontend and the design system. Changing styles is more common but still rare. We would need to consider impact across GOV.UK Frontend, to our styles guidance and to our users and how they use those styles in their services.

### Components

Components are individual, reusable parts of a government service's UI. Examples include:

- [Buttons](https://design-system.service.gov.uk/components/button/)
- [Text inputs](https://design-system.service.gov.uk/components/text-input/)
- [Service navigation](https://design-system.service.gov.uk/components/service-navigation/)
- [Pagination](https://design-system.service.gov.uk/components/pagination/)
- [Inset text](https://design-system.service.gov.uk/components/inset-text/)

All component pages in the design system website are tied to technical component code in GOV.UK Frontend, which each include a [Nunjucks](https://mozilla.github.io/nunjucks/) template, a [Sass](https://sass-lang.com/) file, an API documentation file (a [Yaml](https://yaml.org/) file) a javascript file if the component requires javascript and automated tests for the component.

Components all add unique code to GOV.UK Frontend. This includes for components that rely on other components. For example the [password input](https://design-system.service.gov.uk/components/password-input/) component imports the text input component and the button component, but adds additional styling and javascript to create the password input.

Therefore it is expected that if something does not require any additional code and is only made up of existing components, that a new component is not needed.

### Patterns

Patterns are common UI elements that expand on components to demonstrate specific users of those components or how one or more components can be used together to solve a common design problem.

The patterns section includes a wide range in terms of scope of each pattern. These can range from single uses of a component such as [how to ask for names](https://design-system.service.gov.uk/patterns/names/), to whole pages in a services such as [confirmation pages](https://design-system.service.gov.uk/patterns/confirmation-pages/), to whole journeys such as [creating accounts](https://design-system.service.gov.uk/patterns/create-accounts/).

Whilst patterns are made up of things from GOV.UK Frontend and will often include example code that can be copied, patterns do not live in GOV.UK Frontend as code like components do and we would expect not to create any new code solely for a new pattern. This is because we expect patterns to be made up of components only, therefore a user can make a pattern themselves without needing us to author unique code for them.

There are a couple of instances where patterns are reliant on things outside of GOV.UK Frontend such as the [step by step pattern](https://design-system.service.gov.uk/patterns/step-by-step-navigation/) which is scoped to the GOV.UK website only, however this still doesn't interact with GOV.UK Frontend.

### Features and extensions of existing styles, components or patterns

Sometimes a new feature or problem to solve doesn't need a new library item and instead can be an extension of an existing item. An example of this is the [summary card](https://design-system.service.gov.uk/components/summary-list/#summary-cards), which is a 'feature' of the [summary list](https://design-system.service.gov.uk/components/summary-list/) component rather than a distinct component which imports the summary list.

There isn't a one-size-fits-all approach to deciding if something similar to an existing part of our library can be extended rather than a new thing. An extension can save on the technical weight of GOV.UK Frontend and means that us and our users don't have to remember one extra thing, but risks making the thing being extended more complex.

### Guidance and documentation

Another way that we can solve problems is by not providing any new code or pattern guidance at all and instead writing content for our users. This could be technical documentation, a how-to guide or a 'history' document, to name some examples.

This is useful if the problem you're trying to solve is more around getting users to understand existing parts of the product rather than a new thing.

Bear in mind that the scope of content work can still vary depending on what it is, ranging from a single page to a whole content journey.

## Guiding principals for picking what to deliver

Use these principals in conjunction with the definitions of things in the product to help decide what form the thing your working on takes.

### Don't decide too early

Making an assumption about the precise form can create expectation for our users and the team which can lead to confusion if we change our minds later.

### It's ok to change your mind

Counter to the previous principal, it's also fine if we discover new information which means that what we are trying to do needs to change its form. We work in an agile way and should respond appropriately to new information as it arises.

### Sometimes you need more than one thing

There are times when a problem can't be solved by one thing and you need to deliver additional complementary things to fully achieve what you want.

We have several cases where we've documented a component as well as a pattern applying that component in a whole journey. An example of this is the [task list](https://design-system.service.gov.uk/components/task-list/) component which describes using the component itself in isolation, as well as the pattern for [helping users complete multiple tasks](https://design-system.service.gov.uk/patterns/complete-multiple-tasks/) which describes the end-to-end journey of a user completing multiple tasks as part of a service.

If one thing isn't solving the problem then it's ok to expand the scope of what you deliver if you feel that it's necessary.

### Take an MVP approach

Ask yourself what is the minimal work required to solve your problem. This means we can get it published as quickly as possible. Once it's live, it can be expanded and changed as we get new data from our users and their end users.

### If you can avoid new code, do

New components or changes to components or styles require the most work in a strict 'roles impacted' sense because it means we need to add or change code in GOV.UK Frontend and therefore requires direct involvement from developers. More code also means more for us to maintain. Patterns or guidance as an avenue for change remove this problem.

A more specific application of this principal is in patterns. If you want to document a new thing that is only made up of existing components and doesn't change the behaviour of those things, then this can be a smaller scale pattern rather than a new component.

### What work does the user need to do?

The nature of our product as a design system means that users almost always need to take an action to make use of anything we add, however the work they need to do varies by what we add. If we can reduce the amount of work our users need to do then we should.

A new component for example requires our users to upgrade to the version of GOV.UK Frontend with that new component and then implement it on their service. A new pattern might require a minimum version of GOV.UK Frontend but typically only requires the user to implement that pattern into their service.

### Additions aren't breaking, changes might be

Part of deciding what to deliver also involves understanding if a change is breaking. A breaking change means that we know at least some users will need to take action for their service to continue functioning, not just to opt into a new feature.

Keep this in mind when deciding what to deliver. Additions to our library almost always mean that users can upgrade to new version of GOV.UK Frontend with minimal technical work required because their service can continue working without using the new feature. Changes to existing library items don't always mean users need to make changes themselves but might need to depending on the change. The key question to ask is: will this change stop anyone's service from functioning?

Also note that breaking changes don't always mean we can't do something. There are techniques we can use to manage breaking changes over time to minimise user impact, such as [feature flags](../development/feature-flags/).

### Content work is always required

Across all techniques for deciding what to deliver, we always need to add or change content to our content estate. This could be small or big but it will always need to happen. As a minimum, inform a content designer or tech writer about a piece of work early and ideally involve them in the decision making process on what to deliver.

### Conventions are important

Our design system follows conventions laid out in the definitions of each thing in our library on this page. For example a component guidance page should always be about a unique component in GOV.UK Frontend and that guidance should be scoped as much as possible to that component's behaviour and how to use it.

Following this conventions lead to a more consistent design system which makes it more predictable and easier to use and maintain. We should try to follow our existing conventions as closely as possible. If we have the choice to not break a convention we should try to follow this path. If we need to break a convention it should be for a good reason.
