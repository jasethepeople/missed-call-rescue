# How to Turn Off Missed-Call Text-Back

Keep this page somewhere easy to find. **Do not delete or release the Twilio phone number just to stop texts**; releasing it can affect calls and may mean losing the number.

## Pause texts but keep calls working

If your setup includes a **Pause Text-Back** switch, turn it off. If you do not see that switch, contact your installer and say: **“Please pause SMS only and keep my call forwarding on.”** The text-back flow needs to be paused safely; the TwiML Bin alone may still forward calls.

**Installer/support contact:** ______________________________

## Turn off the whole missed-call setup

If you want to stop both the text-back and its call routing, open the Twilio Console, go to **Phone Numbers** (or **Numbers & senders**) → **Active Numbers** → choose the service number → **Voice** settings. Change **A Call Comes In** from the service's TwiML Bin/Flow back to your previous route; if there was no previous route, ask your installer to route calls to your phone or voicemail. Save the change.

If you're unsure which setting is the old route, stop and ask your installer before changing it. Do not delete the number, Messaging Service, or registration.

## Turn it back on

Ask your installer to restore the TwiML Bin/Flow and test one answered call and one unanswered call before relying on it again.
