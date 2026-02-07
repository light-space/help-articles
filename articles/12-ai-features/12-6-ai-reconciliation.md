# AI-Assisted Reconciliation

Light's AI engine helps match bank transactions with accounting entries, speeding up the reconciliation process. This article explains how AI-assisted reconciliation works and how to use it effectively.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

Bank reconciliation matches transactions from your bank with entries in your accounting system. Light's AI automates much of this work by suggesting matches based on amounts, dates, reference patterns, and historical precedent.

## How AI Matching Works

Light's AI uses multiple matching strategies to identify which bank transactions correspond to which accounting entries:

### Amount-Based Matching

The system recognizes when a bank transaction amount matches the total of one or more accounting entries. For example, if a bank credit of $5,000 matches the total of three invoices being paid ($2,000 + $2,500 + $500), Light suggests this group as a match.

### Date-Based Matching

Light considers transaction dates and posting dates. Accounting entries may post before the corresponding bank transaction clears. The AI accounts for typical clearing delays and suggests matches even when dates are off by a few days.

### Reference Pattern Matching

The system analyzes reference numbers, invoice numbers, and payment IDs. If an accounting entry contains a reference number that appears in the bank transaction description, Light recognizes this as a strong match indicator.

### Historical Learning

Light learns from your previous reconciliations. When you confirm a match:

- Light notes the pattern that led to the match
- Future transactions following similar patterns are matched automatically
- The system becomes more accurate at predicting your reconciliation behavior

> Good to know: AI matching considers your company's typical payment behavior. If you always batch-pay invoices, the AI learns this and suggests batch matches accordingly.

## Automated Reconciliation Rules

Beyond real-time suggestions, Light supports automated reconciliation rules:

### System Rules

Light includes pre-configured rules that work for most companies:

- **Match by invoice number**: If bank descriptions contain invoice numbers, auto-match to the corresponding accounting entries
- **Match open invoices**: Automatically match bank transactions to outstanding vendor invoices
- **Exact amount matches**: Auto-reconcile when amounts match exactly with minimal date variance

### Custom Rules

You can create custom rules for your specific scenarios:

1. Navigate to **Reconciliation Settings**
2. Click **Create Automation Rule**
3. Define the rule criteria (amount ranges, vendor, account, etc.)
4. Light applies the rule to unmatched transactions

### AI-Powered Rules

For advanced scenarios, you can describe a rule in natural language and let Light's AI generate the matching logic:

1. Click **Create AI Rule**
2. Describe your rule in plain language (e.g., "Match expense reports where the amount and date are within 1 day")
3. Light's AI parses your description and creates the matching logic
4. The rule runs automatically on unmatched transactions

## Using AI Match Suggestions

### Reviewing Suggestions

1. Navigate to **Bank Reconciliation** for your account
2. Light displays unmatched bank transactions with suggested matches
3. Each suggestion shows the matched accounting entries and a confidence score
4. Review the details to verify the suggestion is correct

### Accepting Suggestions

To accept a suggested match:

1. Click the suggestion to expand details
2. Verify the amounts, dates, and references align
3. Click **Accept and Reconcile**
4. Light creates the reconciliation and marks both items as matched

### Rejecting Suggestions

If a suggestion is incorrect:

1. Click **Reject** or skip to the next suggestion
2. Light removes this suggestion and notes your feedback
3. The AI learns from your rejection to avoid similar suggestions

### Manual Matching

For transactions Light couldn't match:

1. Click **Manual Match**
2. Search or browse accounting entries to find the right match
3. Select the entries and click **Confirm Match**
4. Light records the match and learns the pattern

## Reconciliation Workflow

A typical reconciliation session using AI:

1. **Review**: Look at unmatched transactions and AI suggestions
2. **Accept**: Quickly accept high-confidence matches (typically 80%+ accuracy)
3. **Review**: Carefully review lower-confidence suggestions
4. **Manual Match**: For remaining items, manually find matches or mark as unmatched
5. **Document**: Note any timing differences or exceptions for your records

## Improving AI Accuracy

AI reconciliation accuracy improves when you:

- Confirm matches that are correct (even if manually entered)
- Reject suggestions that are wrong
- Use consistent reference numbering in your accounting entries
- Include meaningful descriptions in bank transactions (when possible)
- Reconcile regularly (monthly or weekly) rather than in large batches

## Clearing Invoices with AI

Light's AI can also help when reconciling against unpaid invoices:

1. The system identifies outstanding invoices matching bank transactions
2. Light suggests clearing (marking invoices as paid) and reconciling in one step
3. You review the suggestions and confirm
4. Light creates the accounting entries and matches them to the bank transaction

## Exception Handling

Sometimes transactions don't match:

- **Timing differences**: Bank has cleared a transaction not yet posted in accounting. Mark for next month.
- **Bank fees**: Unexpected bank charges. Create a journal entry to record the fee.
- **Currency differences**: Multi-currency payments may have rounding. Review and manually match.
- **Fraud/Error**: Transactions that don't belong. Investigate and contact your bank if needed.

> Tip: Use Light's reconciliation reports to identify reconciliation exceptions and trends. This helps identify process improvements.

## Related Articles

- How Light uses AI
- Bank reconciliation basics
- Common reconciliation issues
