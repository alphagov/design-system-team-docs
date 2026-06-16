---
title: How to decide what to deliver
weight: 5
---

# How to decide what to deliver

The whole GOV.UK Design System product is a multi-faceted service made up of multiple parts including APIs, code and design assets, guidance and community resources. When adding to our product or solving a problem, it is not always obvious how we should deliver whatever we're building for our users.

Use these principles in conjunction with the definitions of things in the product to help decide what form the thing you're working on takes.

To help you decide what to work on and [how to deliver the Design System](./how-we-deliver-the-design-system-to-our-users/) to solve a particular problem, keep these principles in mind.

## Don't decide too early

Making an assumption about the precise form can create expectations for our users and the team which can lead to confusion if we change our minds later.

## It's okay to change your mind

Similar to the previous principle, it’s also fine to change what we’re trying to do as we discover new information. We work in an agile way and should respond appropriately to new information as it arises.

## Sometimes you need more than one thing

There are times when a problem cannot be solved by one thing and you need to deliver additional complementary things to fully achieve what you want.

We have several cases where we've documented a component as well as a pattern applying that component in a whole journey. An example of this is the [Task list component](https://design-system.service.gov.uk/components/task-list/) which describes using the component itself in isolation, as well as the pattern to [Help users to complete multiple tasks](https://design-system.service.gov.uk/patterns/complete-multiple-tasks/) which describes the end-to-end journey of a user completing multiple tasks as part of a service.

If one thing isn't solving the problem then it's okay to expand the scope of what you deliver if you feel that it's necessary.

## Take an MVP approach

Ask yourself what is the minimal effort required to solve the problem at hand. This means we can get it published as quickly as possible. Once it's live, we can be expand and improve as we get new data from our users and their end users.

## If you can avoid new code, do so

New components or changes to components or styles require the most work in a strict 'roles impacted' sense because it means we need to add or change code in GOV.UK Frontend and therefore requires direct involvement from developers. More code also means more for us to maintain. Patterns or guidance are other ways we can affect change that can have a lower impact on the overall team .

A more specific application of this principle is in patterns. If you want to document a new thing that is only made up of existing components and doesn't change the behaviour of those things, then this can be a smaller scale pattern rather than a new component.

## Consider what the user will need to do

The nature of our product as a design system means that users almost always need to take action to make use of anything we add, however the work they need to do varies by what we add. If we can reduce the amount of work our users need to do then we should.

A new component for example requires our users to upgrade to the version of GOV.UK Frontend with that new component and then implement it on their service. A new pattern might require a minimum version of GOV.UK Frontend but typically only requires the user to implement that pattern into their service.

## Adding things are not breaking – changes might be

Part of deciding what to deliver also involves understanding if a change is breaking. A breaking change means that we know at least some users will need to take action for their service to continue functioning, not just to use a new feature.

Keep this in mind when deciding what to deliver. Additions to our library almost always mean that users can upgrade to a new version of GOV.UK Frontend with minimal technical work required because their service can continue working without using the new feature. Changes to existing library items do not always mean users need to make changes themselves but might need to depending on the change. 

The key question to ask is: will this change stop anyone's service from functioning?

Also note that breaking changes do not always mean we cannot do something. There are techniques we can use to manage breaking changes over time to minimise user impact, such as [feature flags](http://../development/feature-flags/).

## Content work is always required

Across all techniques for deciding what to deliver, we always need to add or change guidance in our content spaces. We also need to write documentation and sometimes explain our process and rationale. This could be a small or big piece of work, but it will always need to happen. As a minimum, inform a content designer or technical writer about a piece of work early and ideally involve them in the decision making process on what to deliver.

## Conventions are important

Our design system follows conventions laid out in the definitions of each thing listed in [How we deliver the design system to users](./how-we-deliver-the-design-system-to-our-users/). For example, a component guidance page should always be about a unique component in GOV.UK Frontend and that guidance should be scoped as much as possible to that component's behaviour and how to use it.

Following these conventions lead to a more consistent design system which makes it more predictable and easier to use and maintain. We should try to follow our existing conventions as closely as possible. If we have the choice to not break a convention we should try to follow this path. If we need to break a convention it should be for a good reason.
