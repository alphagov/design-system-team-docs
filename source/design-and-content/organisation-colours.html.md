---
title: Organisation colours in GOV.UK Frontend
weight: 2
last_reviewed_on: 2024-10-08
review_in: 6 months
---

# Organisation colours in GOV.UK Frontend

GOV.UK Frontend includes the brand colours of various ministerial departments within the [bundled `_colours-organisations.scss` file](https://github.com/alphagov/govuk-frontend/blob/main/packages/govuk-frontend/src/govuk/settings/_colours-organisations.scss).

This collection of organisations and brand colours is managed by the Design System team, but uses information originating from the HMG Identity System.

## Deciding which organisations to include

The organisation list should include all [ministerial departments](https://www.gov.uk/government/organisations#ministerial_departments).

It should also include a few overreaching bodies that have their own brand colours and identities within the HMG Identity System, including:

- HM Government
- Civil Service
- Prime Minister's Office, 10 Downing Street

Non-ministerial departments, agencies and other public bodies don't need to be included, as these will use the same brand colour as their parent department and commonly have a website separate from GOV.UK.

Exceptions can be made where the organisation uses GOV.UK as its primary web presence and has a different brand colour to its parent department (such as HM Revenue & Customs).

## Determining the brand colour

Brand colours are determined from a number of sources. These are:

- the HMG Identity System and related assets – these are distributed via the [HMG Brand Portal](https://hmgbrand.gcs.civilservice.gov.uk/)
- the Cabinet Office branding team, who own the HMG Identity System
- [Design102](https://design102.co.uk/), the government's in-house design agency, who are responsible for updating the HMG Identity System
- assets and guidelines supplied by individual organisations

Where different sources provide conflicting information, the HMG Brand Portal is considered the most authoritative source and individual organisations are the least authoritative.

Machinery of government changes can be chaotic times, where a lot of information and assets are being updated quickly. We might not receive updated identity guidelines until months afterwards, requiring us to rely on less reliable sources in the interim.

### Creating contrast-safe alternatives

Some brand colours don't provide the minimum 4.5:1 contrast ratio required by [WCAG Level AA's minimum contrast criterion](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html) when used against white. For these organisations, we additionally provide a 'contrast-safe' colour.

This is done systematically by converting the brand colour to the HSL colour model and continuously reducing the lightness until the resulting colour meets the desired contrast ratio.
