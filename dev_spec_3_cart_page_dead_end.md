# Cart page dead end — dev spec
Site: allwayswireless.com · Priority 3 · Urgent · Effort: Medium (2-5 days)

## Problem
The cart page shows only navigation with no cart contents or checkout button, preventing users from advancing to purchase.

## Evidence (from the live site)
> [Skip to Content](https://www.allwayswireless.com/shop/cart#wrap) [![All Ways Wireless](https://www.allwayswireless.com/web/image/website/1/logo/All%20Ways%20Wireless?unique=4ee3d20)](https://www.allwayswireless.com/) - [Home](https://www.allwayswireless.com/) - [Contact us](https://www.allwayswireless.com/shop/cart#) - [Help](https://www.allwayswireless.com/helpdesk) - [Blog](https://www.allwayswireless.com/blog) - [Brands](https://www.allwayswireless.com/shop/cart#) #### Routers & Gateways * * * [Peplink](https://www.allwayswireless.com/peplink-1)[Teltonika](https://www.allwayswireless.com/t

## Current state
notes: Cart page shows only navigation, no cart contents or checkout button.

## Required change
cta: Add prominent checkout button and continue-shopping link; notes: Display cart contents and clear next-step guidance.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display cart contents and clear next-step guidance.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_cart_page_dead_end` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
