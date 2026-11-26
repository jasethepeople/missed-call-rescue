# MissedCallRescue Deployment Package

*Reusable template: replace the four input placeholders before using. SMS counts below are for the literal placeholders shown; recount after replacement.*

## Business setup

- Business name: `{{business_name}}`
- Business type: `{{business_type}}`
- Business hours: `{{business_hours}}`
- Owner mobile to ring: `{{owner_mobile}}` *(private setup detail; do not include in customer-facing messages)*

## 1. Daytime text-back

> Sorry we missed your call at {{business_name}}. How can we help with your {{business_type}}? Reply STOP to opt out

**114 characters with the placeholders shown.**

## 2. After-hours text-back

> Thanks for calling {{business_name}}. We're closed now; our hours are {{business_hours}}. Text us and we'll reply when open. Reply STOP to opt out

**146 characters with the placeholders shown.**

## 3. Google review request

> Hi from {{business_name}}! Thanks for choosing us. Would you leave an honest Google review? [REVIEW_LINK] Reply STOP to opt out

**127 characters with the placeholders shown.**

## 4. Twilio setup checklist

- [ ] Buy a local Twilio number with both Voice and SMS capability.
- [ ] Register the sender Brand and text-back Campaign for U.S. A2P 10DLC; wait for approval before live sending. A sole proprietor with no EIN uses Twilio's Sole Proprietor Brand path; one with an EIN uses the appropriate Standard/Low-Volume path.
- [ ] Attach the approved Campaign to a Messaging Service and add the local number.
- [ ] Point incoming voice calls to a TwiML Bin that forwards to `{{owner_mobile}}` with an agreed ring timeout.
- [ ] Connect the Bin's `<Dial action>` callback to the service's secure HTTPS webhook/Function. The callback must check the call outcome and send the text only for a true missed call; the Bin alone does not send the text.
- [ ] Set the service to use the daytime message during `{{business_hours}}` and the after-hours message outside those hours. Confirm the business time zone before launch.
- [ ] Confirm STOP/HELP handling and honor opt-outs. Send test calls from three different phones: answered, unanswered/busy, and after-hours.
- [ ] Replace `[REVIEW_LINK]` with the client's direct Google review URL and open it on a phone to verify it reaches the right business.

*Only message people in response to an expected, permission-based interaction; follow applicable carrier and messaging rules.*
