---
name: campaign-drafts
description: Create a Lakewave outreach campaign for a set of companies, with the right person found at each and a personalized draft written for them, ready for a human to approve. Use when the user wants to start outreach, a sequence or a campaign to named accounts, or asks Claude to "write emails to these companies".
---

# Campaigns with drafts a person approves

Lakewave can build a campaign end to end: it finds the best person at each company and writes a personalized first email for each. Nothing is ever sent from here. Drafts wait in the Lakewave app, where the user reviews, approves and schedules them from their own mailbox.

This needs the campaign permission on the user's Lakewave connection. If `create_campaign` is not available, tell the user to reconnect Lakewave and tick "Create campaigns with drafts", or to enable the campaign scope on their API key.

## Steps

1. **Gather the inputs.** A campaign name, the companies, and 1 to 5 role titles to reach. Optional: a location.
2. **State the cost and confirm.** Drafting costs 4 credits per verified person plus 1 per draft, so up to 5 credits per company. Call `account`, tell the user the balance and the worst case, and get a yes before continuing.
3. **Create it** with `create_campaign` and `draft: true`. Without `draft`, it creates the campaign and target list only, at no cost.
4. **Follow progress** with `get_campaign`: company statuses, and counts of drafts, approved and sent.
5. **Hand off.** Give the user the link to the campaign in the Lakewave app and tell them the drafts are waiting for their review there.

## Rules

- Never say that email was sent, scheduled or queued by Claude. Approval and sending happen only in Lakewave, by a person.
- Don't paste drafts into the chat as if they were final; the reviewed version lives in the app.
- For a handful of hand-written emails instead of a campaign, find and verify the people with the prospect-accounts skill and let the user send from their own mail client.
