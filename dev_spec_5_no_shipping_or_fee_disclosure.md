# No shipping or fee disclosure — dev spec
Site: allwayswireless.com · Priority 5 · High · Effort: Medium (2-5 days)

## Problem
Across crawled pages, no shipping costs, taxes, or other fees are mentioned, so visitors cannot anticipate total cost until later in the purchase process.

## Evidence (from the live site)
> A section heading reads “Shop our Featured 5G Routers”.
> 3 distinct calls to action compete on the same page: “Contact us”, “Sign in”, “Buy now”.

## Current state
notes: No shipping or fee information visible.

## Required change
notes: Add shipping and fees section on product and cart pages.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add shipping and fees section on product and cart pages.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_shipping_or_fee_disclosure` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
