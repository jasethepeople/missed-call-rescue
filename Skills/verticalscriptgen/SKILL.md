---
name: verticalscriptgen
description: Generate short missed-call text-back scripts for plumbing, tax/accounting, and salon/spa businesses, with daytime, after-hours, and urgent variants.
compatibility: Created for Zo Computer
metadata:
  author: nonobody.zo.computer
---

# VerticalScriptGen

Generate a set of nine customer-ready SMS examples: daytime, after-hours, and emergency/urgent for plumbing; tax/accounting; and salon/spa. No inputs are required. If the user supplies a business name or hours, personalize only where it fits without changing the required question or exceeding the character limit.

## Required wording and limits

Every message must:

- Be fewer than 160 characters after any personalization.
- Include the exact opt-out line `Reply STOP to opt out`.
- Include its vertical's exact question in every one of the three variants:
  - Plumbing: `Is this an emergency or scheduling?`
  - Tax/accounting: `Are you calling about a deadline or a document question?`
  - Salon/spa: `What service would you like to book?`
- Keep daytime, after-hours, and emergency/urgent variants distinct. The salon urgent variant may describe a last-minute booking; do not imply a medical emergency. The tax urgent variant may ask whether a deadline is today but must not give tax advice.

Use ASCII SMS wording and count every finished message. If adding a business name or hours pushes a message to 160 characters or more, shorten or remove the personalization; never remove the required question or STOP line.

## Output

Save the complete nine-message set as `/home/workspace/skills/verticalscripts/vertical-scripts.md`, grouped by vertical and labeled by timing. Include character counts for the finished messages.
