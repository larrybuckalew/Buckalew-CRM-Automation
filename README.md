# Insurance Agency n8n Workflows

6 production-ready n8n workflows for Buckalew Financial Services (Medicare & Insurance Agency).

## Workflows

| # | File | Purpose | Trigger |
|---|------|---------|---------|
| 1 | `01-lead-capture-lifecycle.json` | Website form → GHL contact, lead scoring, agent alerts | Form submission (polls every hour) |
| 2 | `02-medicare-aep-enrollment.json` | Medicare Annual Enrollment outreach to eligible clients | Sept-Jan, 1st of month |
| 3 | `03-birthday-medicare-milestone.json` | Birthday greetings + Medicare milestone outreach (turning 65) | Daily at 9 AM |
| 4 | `04-lead-reengagement.json` | Re-engage dormant leads (45/60/90 day intervals) | Weekly Mondays |
| 5 | `05-quote-request-automation.json` | Process quote form submissions, create GHL contact, schedule follow-up | Every 15 minutes |
| 6 | `06-social-media-automation.json` | Auto-generate & post insurance content to X/LinkedIn | Daily 9AM/12PM/5PM |

## Setup Instructions

### 1. Create n8n Environment Variables

In n8n Settings → Variables, create these:

| Name | Value |
|------|-------|
| `GHL_API_KEY` | `pit-b1bda1f2-e64d-43dc-a089-6a2ef2c8b88f` |
| `TELEGRAM_BOT_TOKEN` | `5138472763:AAE4AJdomyuolR2LbIJQIBmVO2d8-FQ4n-s` |
| `TELEGRAM_CHAT_ID` | `5273258651` |
| `EMAIL_FROM` | `larry.buckalew@gmail.com` |
| `AGENT_USER_ID` | Your GHL user ID |
| `X_BEARER_TOKEN` | X API bearer token |
| `LINKEDIN_ACCESS_TOKEN` | LinkedIn OAuth access token |

### 2. Update Form IDs

In workflow files 01 and 05, replace `YOUR_FORM_ID_HERE` with your actual GHL Form ID.

### 3. Import Workflows

1. Open n8n → Settings → Import from JSON
2. Paste the contents of each `.json` file
3. Activate each workflow

## Key Features

- **Lead Scoring**: Auto-scores leads 0-100 based on age (50-75 preferred), licensed state, coverage intent
- **Telegram Alerts**: Every new lead triggers a Telegram notification to 5273258651
- **GHL CRM**: All contacts created/updated in GoHighLevel (Location: GXAzp8lTmMJ93EPLDBmW)
- **Compliance**: Licensed states FL, TX, CA, NC, SC, MI displayed in all emails
- **Medicare AEP**: Automated outreach Sept-Jan for Annual Enrollment Period
- **Milestone Tracking**: Identifies contacts turning 65 in next 60 days

## Tags Used in GHL

- `High Value Lead` / `Standard Lead` — based on lead score
- `Medicare` / `Life Insurance` / `Health Insurance` / `Final Expense` — by coverage type
- `AEP Contacted` — contacted during Annual Enrollment Period
- `Birthday Nurture` / `Medicare Milestone` — birthday workflow
- `Re-engagement Attempt 1/2/3` — re-engagement funnel
- `Quote Request` — from quote form
- Licensed state abbreviation (FL, TX, CA, NC, SC, MI)

## License

© 2026 Buckalew Financial Services | W248767 | Licensed in FL, TX, CA, NC, SC, MI
