# Twilio Client Setup Guide

A plain-English walkthrough for a missed-call text-back number. Your setup provider should supply the secure callback URL; do not invent or reuse someone else's URL.

## 1. Buy a local Twilio number

In the Twilio Console, open **Phone Numbers** and choose **Buy a number** (the menu may appear under **Numbers & senders**). Search your area code, then confirm the number supports both **Voice** and **SMS** before buying it. Keep the number in the business owner's Twilio account.

> Screenshot placeholder: local-number search with Voice and SMS capabilities selected.

## 2. Create the call-forwarding TwiML Bin

Open **TwiML Bins**, create a new Bin, and name it something clear, such as “Missed Call Forwarding.” The Bin tells Twilio to ring the owner's mobile. Replace the mobile number and callback URL with the values your setup provider gives you:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Response>
  <Dial timeout="20" action="https://YOUR-SECURE-CALLBACK/call-result" method="POST">
    +1OWNER_MOBILE
  </Dial>
</Response>
```

Use the owner's number in international format, such as `+1` followed by the 10-digit number. The callback is an HTTPS address supplied by your installer. When the ring attempt ends, Twilio sends a `DialCallStatus` result (`completed` when answered; `no-answer`, `busy`, or `failed` when it did not connect) to that address.

> Screenshot placeholder: TwiML Bin editor showing the call-forwarding instructions.

## 3. Point the local number at the Bin

Open the new number's settings. In **Voice** or **Voice & Fax**, set **A Call Comes In** to **TwiML Bin**, select the Bin you just made, and save. The owner should receive calls at the mobile number entered above.

> Screenshot placeholder: phone-number settings with the TwiML Bin selected for incoming calls.

## 4. Connect the callback to the text-back flow

The callback is the part that recognizes a missed call and starts the text. Your setup provider must connect it to a Twilio Function or secure webhook that checks `DialCallStatus`, securely matches the callback to the original caller's number, and sends the correct daytime or after-hours text only for an approved missed-call result such as `no-answer` or `busy`. It should not text when the call was `completed`, should prevent duplicate texts, and must honor STOP/HELP requests.

**Important:** a TwiML Bin can forward the call, but it does not by itself send an SMS after a missed call. Do not go live until the callback URL and text-back flow have been tested.

> Screenshot placeholder: callback/webhook settings and the text-back flow's enabled status.

## 5. Register for U.S. A2P 10DLC

For texts from a U.S. local 10-digit number, open Twilio's **A2P 10DLC** registration area. Register the **Brand** (who is sending) first, then the **Campaign** (what the messages do and how customers agree to receive them). Be ready with accurate business and owner details, the use case, how a customer opts in, representative sample texts, and STOP/HELP wording. Add the local number to the Messaging Service linked to the approved Campaign, then wait for approval before sending live texts.

A sole proprietor with no EIN may use Twilio's Sole Proprietor Brand path; if the business has an EIN, Twilio directs it to a Standard or Low-Volume Standard Brand. See the [A2P checklist](../skills/compliance/checklist.md) for the EIN distinction and the information to gather.

> Screenshot placeholder: Brand and Campaign status showing approved, with the local number linked.

## 6. Test before launch

Call the number and let it ring unanswered; confirm the right text arrives. Call again and answer; confirm no missed-call text is sent. Test daytime and after-hours behavior, reply STOP, and verify the Google review link before sharing it.

### Official references

- [TwiML Bins: getting started](https://www.twilio.com/docs/serverless/twiml-bins/getting-started)
- [TwiML `<Dial>` and its action callback](https://www.twilio.com/docs/voice/twiml/dial)
- [Twilio A2P 10DLC quickstart](https://www.twilio.com/docs/messaging/compliance/a2p-10dlc/quickstart)
