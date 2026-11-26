---
name: reviewrequestgen
description: Write a personal two-message SMS review-request sequence with a direct review link and strict character limits.
compatibility: Created for Zo Computer
metadata:
  author: nonobody.zo.computer
---

# ReviewRequestGen

## Required inputs

- `business_name`
- `customer_name`
- `review_link`: the exact direct URL to use. Do not replace it with a homepage, tracking URL, or invented link.

If any input is missing, ask only for the missing value(s).

## Output rules

Generate exactly two personal, plain-language SMS messages:

1. Initial review request, scheduled for 2 hours after job completion.
2. One gentle reminder, scheduled 5 days later only if no review was received.

Both messages must include the customer's name, business name, the exact direct review link, and `Reply STOP to opt out`. Keep each under 160 characters after substituting the real values (maximum 159). Use the customer's first name when that reads naturally. Do not offer an incentive, pressure the customer, or ask only for a positive review. Count every message after substitution. If the exact link and required text cannot fit, explain that a shorter direct review URL is needed instead of silently dropping the link or exceeding 159 characters.

## Output location

Save the messages as Markdown in `/home/workspace/skills/reviewrequest/`. Use a business/customer-specific filename to avoid overwriting another person's output; keep the generic placeholder example as `review-requests.md` when it already exists.
