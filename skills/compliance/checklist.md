# U.S. A2P 10DLC Registration Checklist

For SMS sent from a U.S. local 10-digit Twilio number. Registration identifies the sender and message program; it does not replace customer consent.

## Sole proprietor: EIN or SSN?

- **IRS tax rule:** You generally need an EIN if you hire employees, must file employment or excise tax returns, or set up a qualified retirement plan. If none of those rules apply, a sole proprietor can generally use an SSN for federal tax reporting. Ask a tax professional if your situation is unclear.
- **Twilio registration rule:** A U.S./Canadian sole proprietor with no EIN may use Twilio's Sole Proprietor Brand path. If the business has an EIN, register as a Low-Volume Standard or Standard Brand instead; do not put an SSN in an EIN field.

## Brand: have ready

Accurate legal/business and public-facing name; business type and industry; EIN or other registration number if applicable; business mailing address; website or social profile if requested; and the authorized representative's legal name, role, email, and phone. For a sole proprietor, the owner is the representative and may need a mobile number for verification. Enter private identifiers only in Twilio's secure registration form.

## Campaign: have ready

The message use case and a clear description; how people opt in and how consent is recorded; representative sample texts; and the opt-out/HELP process and wording. Samples should match the real texts, identify the sender, show links or phone numbers that will be used, and include an opt-out method. Link the approved Campaign and local number through the right Messaging Service.

## If you send without registering

U.S. A2P messages from an unregistered 10DLC number sent through Twilio are blocked and will not reach customers (often Twilio error 30034). Wait for Brand/Campaign approval and number association before launch.

**Official references:** [Twilio: required business and Campaign information](https://www.twilio.com/docs/messaging/compliance/a2p-10dlc/collect-business-info) · [Twilio: unregistered-number error 30034](https://www.twilio.com/docs/api/errors/30034) · [IRS: Instructions for Form SS-4](https://www.irs.gov/pub/irs-pdf/iss4.pdf) · [IRS: sole-proprietor SSN/EIN guidance](https://www.irs.gov/instructions/i1099gi)

*Plain-English orientation, not legal or tax advice. Confirm current requirements in Twilio Console before registering.*
