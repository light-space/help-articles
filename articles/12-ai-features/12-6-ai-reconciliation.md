# AI-Assisted Reconciliation

Light combines a deterministic, rule-based matching engine with targeted AI assistance to speed up bank reconciliation. This article explains what the matching engine does, where AI actually helps, and how to use both effectively.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Overview

Bank reconciliation matches transactions from your bank with entries in your accounting system. In Light, the matching itself is done by a deterministic rules engine — a fixed set of system rules plus any custom rules you create. AI plays three specific supporting roles:

1. **Parsing bank transaction metadata** — extracting structured data (document identifiers, fees, original amounts, end-to-end payment IDs) from raw bank transaction references so the matching rules have clean data to work with.
2. **Creating custom rules from natural language** — you describe a rule in plain language, and AI converts it into structured matching conditions.
3. **Suggesting rules from transactions** — when you convert an unmatched transaction into a rule, AI suggests the rule description based on the transaction's details.

Matches found by the engine are applied directly — matched transactions move to the **Matched** tab. There is no suggestion queue, confidence score, or accept/reject step; if a match made by a rule is incorrect, you can undo it and match manually.

## How Matching Works

When you click **Auto reconcile** (or after a bank import completes), Light evaluates each unmatched bank transaction against the active matching rules, in order, until one produces a match. The built-in system rules are:

- **Match by document number** - Matches based on invoice or document numbers found in the bank transaction reference
- **Match by amount and description** - Finds matches where both the amount and transaction description align with a ledger entry
- **Register payment for open invoice receivables** - Matches incoming bank transactions to open customer invoices and registers the payment
- **Register payment for open invoice payables** - Matches outgoing bank transactions to open vendor bills and registers the payment
- **Create Journal Entry for card balance funding transactions** - Recognizes transfers that fund a card balance account
- **Match by bank transaction end to end id** - Uses end-to-end payment references (common in SEPA and wire transfers)
- **Match by amount and date** - Matches a transaction when exactly one ledger entry has the same amount and date

These rules are deterministic: the same transaction and ledger data always produce the same result. The engine is deliberately conservative — for example, amount-based rules only match when exactly one candidate entry qualifies, so an ambiguous transaction stays unmatched for you to review rather than being matched incorrectly.

See [Automated bank reconciliation](../04-bank-reconciliation/4-4-automated-reconciliation.md) for the full reconciliation workflow.

## AI Transaction Metadata Parsing

Bank transaction references are often messy — a single text field may contain an invoice number, a payment reference, fees, and an original currency amount. When transactions are imported, Light's AI parses each transaction's reference text and extracts:

- **Identifiers** — invoice numbers, document numbers, and payment references
- **Fees** — transaction fees embedded in the reference
- **Original amount** — the amount in the original currency, for converted transactions
- **End-to-end ID** — the payment's end-to-end reference

The extracted values are validated with sanity checks against the transaction's actual amount before being stored. The matching rules then use this structured metadata — for example, **Match by document number** looks up the extracted identifiers against your invoice and document numbers.

This is where AI adds accuracy: it turns unstructured bank data into structured fields, while the matching decision itself remains rule-based and predictable.

## Creating Rules with Natural Language

Custom matching rules are defined in natural language, and Light's AI converts your description into structured conditions:

1. Go to **Accounting → Bank reconciliation** and open the **Rules** tab
2. Click **+ Create rule**
3. Enter the rule **Name**
4. In the **When** field, describe in plain language when the rule should apply (e.g., "When the transaction reference contains 'RENT'")
5. Select the **Action** to perform when the rule matches (e.g., create and match a journal entry)
6. Fill in the **Details** for the entry the rule creates (business partner, GL account, description, tax code, etc.)
7. Click **Validate & Save**

Light parses your description into conditions on fields like amount, date, reference, and bank account. The parsed conditions are shown to you before saving — always review them to confirm they reflect your intent, and refine the wording if they don't.

Once saved, the rule runs deterministically during auto reconcile — the AI is only involved when the rule is created or edited, not each time it runs.

See [Reconciliation automation rules](../04-bank-reconciliation/4-5-automation-rules.md) for full details on conditions and actions.

## Convert to Rule

When you find an unmatched transaction that will recur (rent, payroll, subscriptions), you can turn it into a rule directly:

1. On the **Unmatched** tab, select the bank transaction
2. Click **Convert to rule**
3. Light's AI suggests a rule description based on the transaction's details
4. Review and adjust the suggestion, then validate and save

Similar future transactions are then handled automatically during auto reconcile.

## Manual Matching

For transactions the rules couldn't match:

1. On the **Unmatched** tab, select one or more bank transactions on the left panel
2. Select the matching ledger entry (or entries) on the right panel
3. Check that the **Difference** indicator shows 0.00
4. Click **Match** to confirm

Manual matches are recorded like any other match. Light does not learn matching behavior from your manual decisions — to automate a recurring pattern, use **Convert to rule** or create a custom rule.

## Clearing Open Invoices

The **Register payment for open invoice** system rules handle bank transactions that pay outstanding invoices:

1. During auto reconcile, the engine looks up open customer invoices or vendor bills using the identifiers parsed from the bank transaction
2. When a matching open invoice is found, Light registers the payment and reconciles it against the bank transaction in one step
3. The invoice is marked as paid and the match appears on the **Matched** tab

## Exception Handling

Sometimes transactions don't match:

- **Timing differences**: Bank has cleared a transaction not yet posted in accounting. Mark for next month.
- **Bank fees**: Unexpected bank charges. Create a journal entry to record the fee.
- **Currency differences**: Multi-currency payments may have rounding. Review and manually match.
- **Fraud/Error**: Transactions that don't belong. Investigate and contact your bank if needed.

> Tip: Use Light's reconciliation reports to identify reconciliation exceptions and trends. This helps identify process improvements.

## Best Practices

- **Run Auto reconcile first** — let the rules engine handle the straightforward matches, then focus on the exceptions
- **Use consistent reference numbering** — the document number rule works best when your invoice numbers appear in bank transaction references
- **Review parsed rule conditions** — always check the conditions Light generates from your natural-language description before saving
- **Reconcile regularly** — weekly or monthly reconciliation keeps the unmatched queue manageable

## Related Articles

- [How Light uses AI](12-1-how-light-uses-ai.md)
- [Automated bank reconciliation](../04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Reconciliation automation rules](../04-bank-reconciliation/4-5-automation-rules.md)
