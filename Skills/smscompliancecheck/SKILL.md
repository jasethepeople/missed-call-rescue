---
name: smscompliancecheck
description: Produce a concise, plain-English U.S. A2P 10DLC registration checklist that distinguishes IRS sole-proprietor EIN rules from Twilio Brand eligibility.
compatibility: Created for Zo Computer
metadata:
  author: nonobody.zo.computer
---

# SMSComplianceCheck

Create a one-page checklist for a small U.S. business registering SMS sent from a local 10-digit number. No inputs are required.

Before each run, verify the current requirements on official Twilio A2P 10DLC documentation and current IRS guidance. Separate these two questions clearly:

- IRS tax identification: explain when a sole proprietor generally must obtain an EIN (for example, employees/employment taxes, applicable excise filing, or a qualified retirement plan) and when an SSN can generally be used for federal tax reporting. Avoid presenting this as personal tax advice.
- Twilio A2P Brand eligibility: a U.S./Canadian sole proprietor with no EIN may use the Sole Proprietor Brand path; a business that has an EIN should use the applicable Low-Volume Standard or Standard Brand path. Do not tell users to enter an SSN in an EIN field.

The checklist must cover information to prepare for Brand registration (accurate business/legal name and type, industry, tax or registration ID when applicable, address, representative's identity and contact details, and website/social details if requested); Campaign registration (use case, clear description, consent/opt-in flow, representative sample texts, and HELP/STOP handling); and what can happen when sending unregistered (filtering/blocking and failed delivery, including Twilio error 30034 when applicable).

Keep the output to one printed page, aim for 350 words or fewer, use plain English, and include links to the official Twilio and IRS references used. Do not invent carrier fines, promise approval, or imply registration replaces customer consent.

Save the current checklist to `/home/workspace/skills/compliance/checklist.md`.
