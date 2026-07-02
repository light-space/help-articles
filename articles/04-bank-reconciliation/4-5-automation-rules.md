# Reconciliation Automation Rules

Reconciliation automation rules control how Light matches bank transactions to accounting entries. This article explains how to create and manage these rules.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Rule Types

Light includes two types of rules:

**System Rules** - Built-in rules created by Light that match common scenarios. They cannot be modified or deleted.

**User Rules** - Custom rules you create for your specific business scenarios.

Light's system rules are:
- **Match by document number** - Matches based on invoice or document numbers found in the bank transaction reference
- **Match by amount and description** - Finds matches where both the amount and transaction description align with a ledger entry
- **Register payment for open invoice receivables** - Matches incoming bank transactions to open customer invoices and registers the payment
- **Register payment for open invoice payables** - Matches outgoing bank transactions to open vendor bills and registers the payment
- **Create Journal Entry for card balance funding transactions** - Recognizes transfers that fund a card balance account
- **Match by bank transaction end to end id** - Uses end-to-end payment references (common in SEPA and wire transfers)
- **Match by amount and date** - Matches a transaction when exactly one ledger entry has the same amount and date

## Creating Custom Rules

Create custom matching rules for specific needs:

1. Go to **Accounting → Bank reconciliation** and open the **Rules** tab
2. Click **+ Create rule**
3. Enter the rule **Name**
4. In the **When** field, describe in natural language when the rule should apply (e.g., "When the transaction reference contains 'RENT'")
5. Select the **Action** to perform when the rule matches
6. Fill in the **Details** for the entry the rule creates (business partner, GL account, description, tax code, etc.)
7. Click **Validate & Save**

Light parses your natural-language description into structured matching conditions. Rules are evaluated in order, and the first matching rule applies.

You can also create a rule directly from an unmatched transaction using **Convert to rule** on the reconciliation view, which pre-fills the rule based on the selected transaction.

## Rule Conditions

Conditions are generated from your natural-language **When** description. They can reference the following bank transaction fields:

- **Amount** - The transaction amount
- **Original amount** - The amount in the original currency, for converted transactions
- **Fees** - Transaction fees
- **Date** - The transaction date
- **Reference** - The transaction reference/description text
- **Bank account** - The ledger bank account the transaction belongs to

Supported comparisons are equals, not equals, greater than (or equal), less than (or equal), and—for reference text—contains.

Conditions are combined with AND/OR logic for complex scenarios.

## Rule Actions

Each rule specifies an action—what to create and match when the conditions are met:

**Match with Journal Entry** - Create and match a journal entry with:
- A specific GL account, description, tax code, and accrual settings
- An optional business partner
- Custom property values

**Match with Customer Credit** - For customer payments recorded as customer credits:
- Specify the product and optional tax code
- Optionally link a specific customer

**Match with Credit Note** - For vendor credits that offset AP:
- Specify the description and optional tax code
- Optionally link a specific vendor

Matching payments to open AR or AP invoices is handled automatically by the built-in system rules, so you don't need a custom rule for that.

## Example Rules

**Rule: International Wire Transfers**
- When: Amount is greater than $50,000 and the reference contains "Wire"
- Action: Match with Journal Entry to International Receivables account

**Rule: Daily Stripe Deposits**
- When: Reference contains "Stripe"
- Action: Match with Journal Entry to Stripe Clearing account

**Rule: Vendor Refunds**
- When: Reference contains a specific vendor name
- Action: Match with Credit Note

## Rule Order and Priority

Rules run in a fixed order: system rules first, then custom rules in the order they were created. Each new custom rule is added at the end of the list.

A transaction stops evaluation once a matching rule is found, so:

- Each transaction is matched at most once
- Earlier rules take precedence over later ones

Write specific conditions in your rules to prevent a broad rule from matching transactions it shouldn't.

## Reviewing a Rule Before Saving

When you create or edit a rule, Light parses your natural-language description and shows the resulting conditions so you can verify them before saving. Review the parsed conditions carefully—if they don't reflect your intent, refine the wording of the **When** description and validate again.

This prevents the rule from incorrectly matching unintended transactions.

## Archiving Rules

To remove a custom rule:

1. Find the rule in the **Rules** tab
2. Click **Archive**
3. The rule stops applying and is removed from the active list

System rules cannot be archived or modified.

## Rule Statistics

The rules table shows usage information for each rule:

- **Runs** - How many times the rule has matched and been applied
- **Last run** - When the rule last applied

Use this to review your rules—if a rule never runs, consider refining or archiving it.

## Conflict Resolution

If multiple rules could match the same transaction:

- **First rule wins** - The first matching rule (by order) applies
- **No double-matching** - Each transaction is matched at most once
- **Manual override** - You can undo an auto-match and manually match differently

## Reference Number Matching

The built-in **Match by document number** system rule matches document numbers found in the bank transaction reference to accounting documents:

**Invoice number** - Matches bank transaction reference to an invoice number

**Document number** - Matches other document numbers appearing in the reference text

When the bank description contains the document number, the system can automatically identify the matching entry.

## Vendor/Customer Specific Rules

Some rules apply only to specific business partners:

1. Create a rule whose **When** description identifies the partner's transactions (e.g., "reference contains 'ACME'")
2. In the rule's **Details**, set the business partner and the GL account to use
3. Repeat for other vendors or customers needing specific treatment

This is useful for business partners with unique payment patterns or GL accounts.

## Audit Trail of Matches

Track which rule matched each transaction:

1. Go to **Accounting → Bank reconciliation**, open the bank account, and click the **Matched** tab
2. View matched transactions and see how they were matched
3. If a match made by a rule was incorrect, undo the match, and refine or archive the rule

This helps identify problematic rules.

## Best Practices

- **Start simple** - Begin with a few core rules before adding complexity
- **Review parsed conditions** - Always check the conditions Light generates from your description before saving
- **Monitor effectiveness** - Review rule run counts regularly
- **Write specific conditions** - Prevent overly-broad rules from matching unintended transactions
- **Document rules** - Use descriptive names explaining the rule's purpose
- **Review quarterly** - As business patterns change, update rules
- **Archive old rules** - Clean up rules that are no longer needed

## Related Articles

- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Resolving discrepancies](/mnt/help-articles/articles/04-bank-reconciliation/4-6-resolving-discrepancies.md)
- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
