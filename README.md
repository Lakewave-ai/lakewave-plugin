# Lakewave for Claude

Lakewave finds and verifies the people a B2B seller needs at the accounts they name, checks email addresses before anyone sends, surfaces public-sector contracts that are coming up for rebid, and fills campaigns with personalized drafts that a person approves. This plugin connects Claude to Lakewave and adds four skills that teach Claude how to use it well.

![Lakewave](./icon.png)

## What you get

**The Lakewave connector** (`https://app.lakewave.ai/mcp`), with eleven tools:

| Tool | What it does | Cost |
| --- | --- | --- |
| `account` | Plan, credit balance, prices and limits | Free |
| `find_people`, `get_job` | Verified people by role at named companies | 4 credits per verified person |
| `verify_emails` | Verdicts for up to 25 addresses | 1 credit per valid or invalid verdict |
| `verify_list`, `get_list` | Verdicts for lists up to 5,000 addresses | 1 credit per valid or invalid verdict |
| `email_format` | A company's email convention and candidate addresses | Free |
| `my_contacts` | Search contacts you already have in Lakewave | Free |
| `contracts_ending` | Public-sector contracts ending inside a window | Free |
| `create_campaign`, `get_campaign` | A campaign with a draft for the best person at each company | 4 per verified person plus 1 per draft |

**Skills**

- `prospect-accounts`: find and verify decision makers at named accounts, reusing contacts you already paid for and checking the budget first.
- `contract-rebids`: find state, local and education contracts that are ending, then the buyers to contact.
- `clean-email-list`: verify a few addresses or a whole list and split it into keep, drop and handle with care.
- `campaign-drafts`: build a campaign whose drafts wait in Lakewave for your approval.

## Setup

1. Install the plugin from the Claude directory. In Claude Code you can also install it straight from this repository:
   ```
   /plugin install lakewave --marketplace taylorsec/lakewave-plugin
   ```
2. When Claude first uses Lakewave it opens a Lakewave sign-in. Sign in (or create a free account) and approve the connection. Campaign creation is off unless you tick it.
3. Ask, for example: "Find the IT directors at these eight accounts in Texas and verify them."

Each connection appears in the Lakewave app under Integrations, where you can set a daily credit cap or disconnect it.

## What this plugin runs and sends

- It runs no code on your computer. It contains instructions (skills) and one connector address.
- Tool calls go only to `https://app.lakewave.ai/mcp`, over HTTPS, authorized by the sign-in you approve. What is sent is what the tool needs: company names, role titles, email addresses to verify, search filters and campaign details.
- Lakewave never sends email from these tools. Drafts wait in the Lakewave app for a person to approve and schedule them.
- Credits are charged to your Lakewave account at the prices above.

## Privacy

Lakewave processes the data sent by these tools to deliver the results you ask for, and keeps search results and verified contacts in your Lakewave account so you are not charged twice for the same person. Lakewave does not sell your data. Read the full policy, including retention, third parties and how to delete your data, at https://lakewave.ai/privacy.

## Support

support@lakewave.ai, or https://lakewave.ai/agents/ for documentation.

## License

MIT, see [LICENSE](./LICENSE).
