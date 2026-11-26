---
name: missedcallrescue
description: Create a reusable missed-call text-back deployment package for a local business, including compliant short SMS copy and a practical Twilio setup checklist.
compatibility: Created for Zo Computer
metadata:
  author: nonobody.zo.computer
---

# MissedCallRescue

Generate a complete, business-specific missed-call text-back package without changing this skill's core logic.

## Required inputs

- `business_name`: the business's approved public-facing name.
- `business_type`: what it does, such as plumbing, tax/accounting, or salon/spa.
- `business_hours`: the actual open schedule. Preserve the supplied timezone; if none is supplied, flag that the owner must confirm it before launch rather than guessing.
- `owner_mobile`: the number that should ring for forwarded calls, preferably in E.164 format. Treat it as private setup information; never put it in a customer-facing SMS.

If a required input is missing, ask only for the missing value(s). Do not invent a business name, hours, phone number, or review URL.

## Package contents

Create one Markdown deployment package containing:

1. A daytime text-back under 160 characters after substitution, including the exact phrase `Reply STOP to opt out`.
2. An after-hours text-back that uses the supplied hours and stays under 160 characters after substitution.
3. A Google review request under 160 characters after substitution, with `[REVIEW_LINK]` left as a clear placeholder because the review URL is not an input.
4. A simple Twilio checklist covering a local Voice+SMS number, a TwiML Bin that rings `owner_mobile`, an HTTPS callback/webhook that starts the text-back flow only for missed calls, U.S. A2P 10DLC Brand/Campaign registration and number association, and live tests including STOP and the review link.

Use the business name/type naturally where they fit. Keep SMS copy short and plain; avoid emoji and unnecessary special characters. Count each final SMS after substitution. If a long input pushes it to 160 or more, shorten the wording (or omit a long business label) until it is at most 159 characters. Keep the exact opt-out phrase in the daytime message. Preserve the review-link placeholder and never promise a review or offer an incentive.

Explain in the checklist that a TwiML Bin can route the call but the callback service must detect `no-answer`/`busy` and send the SMS; the Bin alone does not send the text. Do not claim that Twilio has been configured, and do not send texts, buy numbers, or submit registrations.

## Output

Save a Markdown package in `/home/workspace/skills/missedcallrescue/output/`. Use a business-name slug in the filename, such as `acme-plumbing-deployment-package.md`, and never overwrite an existing client's package. Keep `deployment-package.md` as the reusable placeholder template when it is already present.
