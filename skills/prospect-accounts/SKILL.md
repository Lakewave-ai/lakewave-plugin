---
name: prospect-accounts
description: Find and verify the right people at named companies with Lakewave. Use when the user wants contacts, decision makers, emails or a prospect list for specific accounts or a territory, such as "who runs IT at these companies", "find the CISO at Acme", or "build me a list of directors of infrastructure in Texas".
---

# Prospect named accounts with Lakewave

Lakewave returns people who already meet its verified bar (4 stars or better): name, title, company, a verified work email and a LinkedIn link. It charges 4 credits per verified person and nothing for a search that finds nobody.

## Steps

1. **Pin down the ask.** You need company names (1 to 25 per search) and role titles (1 to 5). If the user gave a territory instead of companies, ask for the accounts or use `contracts_ending` and `my_contacts` to suggest some. Optional: a location, with `location_mode` set to `hq` (companies headquartered there) or `people` (people located there).
2. **Check what is already paid for.** Call `my_contacts` with the company or domain first. Those contacts are free to reuse. Only search for the companies and roles still missing.
3. **Mind the budget.** Each verified person costs 4 credits, and a company can return more than one person when several titles match. For more than about 10 companies, call `account`, tell the user the balance and a rough worst case (at least 4 credits per company, more with several titles), and confirm before starting.
4. **Start the search** with `find_people`. It returns a `job_id` straight away; searches take 1 to 4 minutes.
5. **Collect results.** Wait about a minute, then call `get_job` with the `job_id`. Repeat until `status` is `done`. Tell the user it is running rather than calling `get_job` in a tight loop.
6. **Present the people** as a table: name, title, company, email, stars. Note the companies where nobody qualified; those cost nothing. Give the credits used if the result includes them.

## Rules

- Only report people Lakewave returned. Never guess an email address; if the user wants a guess for someone not found, use `email_format` and label the result as unverified until `verify_emails` confirms it.
- Lakewave does not send email. If the user wants outreach, use the campaign-drafts skill: drafts wait in Lakewave for a person to approve.
- If a call returns an error about a daily cap or credits, say so plainly and point the user to Integrations or Billing in the Lakewave app.
