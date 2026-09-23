---
title: How we deliver the design system to our users
weight: 5
---
# How we deliver the design system to our users

The way we provide the different parts of our product each depend on what we are trying to achieve and the work involved.

These include the typical elements that we think most often about as parts of the Design System:

- styles  
- components  
- patterns

There’s also many other outputs that can sit within or around the typical elements:

- features and extensions of styles, components and patterns (sometimes called variants)  
- guidance and documentation

## Styles

Styles make government services look and feel like GOV.UK. They are the foundational design and code elements of GOV.UK Frontend and the wider design system. Examples include [Colour](https://design-system.service.gov.uk/styles/colour/), [Spacing](https://design-system.service.gov.uk/styles/spacing/) and typography, such as our [responsive type scale](https://design-system.service.gov.uk/styles/type-scale/).

These are all strongly tied into the code of GOV.UK Frontend, with the sole exception being [guidance on images](https://design-system.service.gov.uk/styles/images/) which we do not deliver via code but is still important information pertinent to users building services using the design system.

Adding or removing a style would be very rare and require a great deal of work to change it across GOV.UK Frontend and the Design System. Changing styles is more common but still rare. We would need to consider impact across GOV.UK Frontend, to our styles guidance and to our users and how they use those styles in their services.

## Components

Components are reusable parts of a user interface. Using pre-built, core elements allows government teams to build consistent services. Examples include [Buttons](https://design-system.service.gov.uk/components/button/), [Service navigation](https://design-system.service.gov.uk/components/service-navigation/) and [Inset text](https://design-system.service.gov.uk/components/inset-text/).

All component pages in the design system website are tied to technical component code in GOV.UK Frontend, which each include:

- a [Nunjucks](https://mozilla.github.io/nunjucks/) template  
- a [Sass](https://sass-lang.com/) file  
- an API documentation file (a [Yaml](https://yaml.org/) file)  
- a JavaScript file, if the component requires JavaScript and automated tests for the component

Components all add unique code to GOV.UK Frontend. This includes components that rely on other components. For example the [Password input](https://design-system.service.gov.uk/components/password-input/) component imports the text input component and the button component, but adds additional styling and javascript to create the password input.

Therefore it’s expected that if something does not require any additional code and is only made up of existing components, that a new component is not needed.

## Patterns

Patterns are best practice design solutions for specific user-focused tasks and page types.

The scope of the patterns section ranges from single uses of a component such as [how to ask for names](https://design-system.service.gov.uk/patterns/names/), to whole pages in a service such as [confirmation pages](https://design-system.service.gov.uk/patterns/confirmation-pages/), to whole journeys such as [creating accounts](https://design-system.service.gov.uk/patterns/create-accounts/).

Whilst patterns are made up of things from GOV.UK Frontend and will often include example code that can be copied, patterns do not live in GOV.UK Frontend as code like components do and we’d expect not to create any new code solely for a new pattern. This is because we expect patterns to be made up of components only, so a user can make a pattern themselves without needing us to author unique code for them.

There are a couple of instances where patterns are reliant on things outside of GOV.UK Frontend such as the [Step by step pattern](https://design-system.service.gov.uk/patterns/step-by-step-navigation/) which is scoped to the GOV.UK website only, however this still doesn't interact with GOV.UK Frontend.

## Features and extensions of existing styles, components or patterns

Sometimes, a new feature or problem to solve does not need a new library item and instead can be an extension of an existing item. An example of this is the [summary card](https://design-system.service.gov.uk/components/summary-list/#summary-cards), which is a 'feature' of the [Summary list](https://design-system.service.gov.uk/components/summary-list/) component rather than a distinct component which imports the summary list.

There isn't a one-size-fits-all approach to deciding if something similar to an existing part of our library can be extended instead of creating a new thing. An extension can save on the technical weight of GOV.UK Frontend and means that we and our users do not have to maintain one extra thing, but risks making things more complex.

## Guidance and documentation

Another way that we can solve problems is by not providing any new code or pattern guidance at all and instead writing content for our users. This could be technical documentation, a how-to guide or a 'history' document, to name some examples.

This is useful if the problem we’re trying to solve is more around getting users to understand existing parts of the product rather than rolling out a new thing.

Bear in mind that the scope of content work can still vary depending on what it is, ranging from a single page to a whole content journey.  
