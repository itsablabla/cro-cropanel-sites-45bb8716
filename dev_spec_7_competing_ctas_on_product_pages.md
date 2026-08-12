# Competing CTAs on product pages — dev spec
Site: allwayswireless.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
Product pages present both 'Buy now' and 'Contact us' as primary actions, splitting user focus and making the next step ambiguous.

## Evidence (from the live site)
> 3 distinct calls to action compete on the same page: “Contact us”, “Sign in”, “Buy now”.

## Current state
cta: Contact us | Sign in | Buy now; notes: Multiple competing CTAs.

## Required change
cta: Make 'Buy now' dominant, de-emphasize 'Contact us'; notes: Single clear next step toward checkout.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Single clear next step toward checkout.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_ctas_on_product_pages` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
