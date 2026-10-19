---
name: clean-email-list
description: Verify email addresses or clean a contact list with Lakewave before sending. Use when the user asks whether emails are valid, wants to reduce bounces, re-verify an old or purchased list, or check a few addresses before outreach.
---

# Verify addresses and clean a list

Lakewave gives one verdict per address: `valid`, `invalid`, `catch_all` (the domain accepts everything, so the mailbox can't be confirmed), `unknown`, `dead_domain` or `bad_syntax`, each with a reason and a 0 to 5 star rating. It charges 1 credit per definitive verdict (valid or invalid); every other verdict is free.

## Steps

1. **Collect the addresses.** Accept a pasted list or a file the user shares. Remove duplicates and obvious typos you can see, and tell the user what you removed.
2. **Choose the tool by size.**
   - Up to 25 addresses: `verify_emails`. Results come back in the same call.
   - 26 to 5,000: `verify_list`. It returns a `job_id`; call `get_list` about a minute later and again until `status` is `done`.
   - More than 5,000: split into batches of 5,000 and tell the user.
3. **Mind the budget.** The most a list can cost is 1 credit per address. For lists over a few hundred, call `account` and confirm the balance and worst case with the user first.
4. **Report.** Give counts per verdict, then the list to keep (`valid`), the list to drop (`invalid`, `dead_domain`, `bad_syntax`), and the list to treat with care (`catch_all`, `unknown`). Offer the cleaned list as a table or CSV.

## Rules

- `catch_all` is not a failure: the address may well work, but nobody can confirm it. Say that rather than calling it bad.
- Never change an address and present it as verified. To find a replacement for a bad address, use `email_format` for the company's convention and then verify the candidate.
