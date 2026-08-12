# Placeholder price on product — dev spec
Site: allwayswireless.com · Priority 4 · Urgent · Effort: Medium (2-5 days)

## Problem
The product page displays a placeholder price of $1, making the purchase decision impossible and undermining trust in pricing accuracy.

## Evidence (from the live site)
> Prices shown on the page: $ 1 $ 1 $ 1

## Current state
notes: Price shown as $1 placeholder.

## Required change
notes: Replace with actual retail price.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace with actual retail price.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_placeholder_price_on_product` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
