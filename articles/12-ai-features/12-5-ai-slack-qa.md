# Natural Language Q&A in Slack

Light integrates with Slack to let you ask financial questions in plain language using @Light. Get reports, check balances, and access financial insights without leaving Slack.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

The Light Slack integration brings financial data into your team's communication workflow. You can ask questions about spending, payables, receivables, and other financial metrics directly in Slack, and Light responds with relevant data and insights.

## How It Works

Light's AI processes your natural language questions and translates them into queries against your financial data. The system understands context like time periods, departments, and expense categories from how you phrase your questions.

## Getting Started

### Installation

1. Go to Light's Settings or Integration menu
2. Select **Slack Integration**
3. Click **Connect to Slack**
4. Authorize Light to access your Slack workspace
5. Light creates a user account in your Slack workspace

### Basic Usage

Once Light is installed in your Slack workspace:

1. Mention @Light in any Slack channel or direct message
2. Ask your financial question in plain language
3. Light processes your question and responds with the answer
4. Light's response includes relevant data tables, charts, or summaries

## Example Questions

You can ask Light questions like:

- "What did we spend on travel last month?"
- "Show me top vendors by spending in Q4"
- "How much do we owe to Acme Corp?"
- "What's our current cash balance?"
- "Give me a summary of overdue invoices"
- "How much was spent on office supplies this quarter?"
- "Which departments exceeded budget?"

Light understands variations of these questions and responds intelligently.

## Question Types

### Spending and Expenses

- "How much did we spend on [category]?"
- "Top vendors this month"
- "Expenses by department"
- "Travel spend for [employee name]"

### Payables and Receivables

- "What invoices are outstanding?"
- "How much do we owe [vendor]?"
- "Show me overdue bills"
- "When are payments due?"

### Cash and Liquidity

- "What's our cash balance?"
- "Upcoming cash obligations"
- "Days of cash on hand"

### Reports and Summaries

- "Monthly spending summary"
- "Budget vs actual"
- "Reconciliation status"
- "Open items by category"

> Good to know: Light understands context. If you ask "Show me last month's spending" in February, Light knows you mean January. If you ask "Travel spend" without a time period, Light shows you the current month by default.

## Permissions and Access

Light respects your access controls:

- You can only see financial data you have permission to view
- Questions about restricted departments or entities will be declined
- Confidential financial information requires appropriate access levels

> Tip: Use direct messages with @Light for sensitive questions. This keeps financial queries private from your channel history.

## Understanding Light's Responses

Light's responses typically include:

- **Summary**: A brief answer to your question
- **Data Table**: Detailed line-by-line data if relevant
- **Chart**: Visual representation if helpful for analysis
- **Clarifications**: Questions if Light needs to clarify what you asked

## Limitations

Some questions cannot be answered through Slack:

- Highly complex analyses requiring multiple steps
- Multi-page reports
- Questions requiring interactive drill-down
- Real-time data not yet synced to Light

For these, Light suggests accessing Light's web interface for a fuller analysis.

## Privacy and Security

Your Slack conversations with Light are:

- Encrypted in transit
- Logged for audit purposes
- Not shared with external services
- Subject to the same security standards as Light's main platform

Sensitive questions can be asked in direct messages for extra privacy.

## Troubleshooting

### Light Doesn't Respond

- Verify Light is installed in your Slack workspace
- Ensure you have access to the financial data you're asking about
- Try rephrasing your question more simply

### Incorrect Answers

- Light may have misunderstood your question. Try rephrasing it.
- Provide more context (specific time periods, departments, entities)
- Use specific category names rather than vague terms

### Access Denied

- You may not have permission to view the data you asked about
- Contact your Light administrator to request access

## Related Articles

- How Light uses AI
- AI-assisted reconciliation
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
