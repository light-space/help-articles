# Reconciliation Automation Rules

Reconciliation automation rules control how Light matches bank transactions to accounting entries. This article explains how to create and manage these rules.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Rule Types

Light includes two types of rules:

**System Rules** - Built-in rules that match common scenarios. You can enable/disable but not modify them.

**User Rules** - Custom rules you create for your specific business scenarios.

System rules typically handle:
- Open invoice matching (AR invoices)
- Open payable matching (AP invoices)
- End-to-end payment matching (payment creation through posting)
- Reference number matching (invoice/check numbers)
- Amount and date matching (fuzzy matching with tolerance)

## Creating Custom Rules

Create custom matching rules for specific needs:

1. Go to **Accounting > Bank reconciliation** to manage automation rules
2. Click **Create Rule**
3. Enter rule **name** and **description**
4. Define the rule's **matching criteria and action**
5. Set the **order** (when to apply relative to other rules)
6. Click **Save**

Rules are evaluated in order (lowest order number first), and the first matching rule applies.

## Rule Conditions

Rules use conditions to determine which transactions they apply to:

**Amount Conditions:**
- Exact amount
- Amount range
- Amount above/below threshold

**Date Conditions:**
- Specific date
- Date range
- Days since transaction

**Reference Conditions:**
- Contains specific text
- Starts with or ends with
- Invoice/check number match

**Transaction Type:**
- Debit (withdrawal)
- Credit (deposit)
- Both

Conditions are combined with AND/OR logic for complex scenarios.

## Rule Actions

Each rule specifies an action—what to match to:

**Match with Journal Entry** - Match to general ledger journal entries with:
- Specific ledger accounts
- Custom property values
- Amount and date criteria

**Match with Customer Credit** - For customer payments that offset AR invoices:
- Specify customer or all customers
- Link to customer credit GL accounts

**Match with Credit Note** - For vendor credit memos that offset AP invoices:
- Specify vendor or all vendors
- Link to credit note GL accounts

**Match with Open Invoice** - For payments that match specific invoices:
- Match to unpaid AR or AP invoices
- Use reference number if available

## Example Rules

**Rule: International Wire Transfers**
- Condition: Amount > $50,000 AND Description contains "Wire"
- Action: Match with Journal Entry to International Receivables account
- Order: 1

**Rule: Daily Stripe Deposits**
- Condition: Description contains "Stripe" AND Date = Today
- Action: Match with Journal Entry to Stripe Clearing account
- Order: 2

**Rule: Vendor Checks**
- Condition: Description contains "Check" OR Reference matches invoice number
- Action: Match with Credit Note
- Order: 3

**Rule: Customer ACH Deposits**
- Condition: Amount between $1-$100,000 AND Debit/Credit = Credit
- Action: Match with Open Invoice (AR)
- Order: 4

## Rule Order and Priority

Rules are applied in ascending order by their order number:

- **Order 1** - Most specific rules (exact amounts, specific vendors)
- **Order 2-5** - Medium specificity rules
- **Order 10+** - Catch-all rules (any amount, all vendors)

A transaction stops evaluation once a matching rule is found. To prevent overlapping:

- Put most specific rules first (lower order number)
- Put broad catch-all rules last (higher order number)

For example, if you have "Wire transfers" and "All transactions," put the wire rule first.

## Testing Rules

Before activating a rule, test it:

1. Go to **Accounting > Bank reconciliation** to manage automation rules
2. Find the rule and click **Test**
3. Select or create test transactions
4. View which transactions match the rule
5. Verify the matching is correct

Testing prevents the rule from incorrectly matching unintended transactions.

## Disabling and Archiving Rules

You can disable rules without deleting them:

1. Find the rule in the list
2. Click **Disable** (system rules) or **Deactivate** (custom rules)
3. The rule stops applying but remains for reference

To permanently remove:

1. Click **Archive**
2. The rule is hidden but can be restored if needed

## Rule Statistics

View rule usage and effectiveness:

1. Go to **Accounting → Bank reconciliation → Rule Statistics**
2. View for each rule:
   - **Runs** - How many times the rule has been evaluated
   - **Matches** - How many transactions were matched
   - **Success rate** - % of transactions correctly matched
   - **Last run** - When the rule last applied

Use statistics to optimize your rules—if a rule never matches, consider disabling it.

## Conflict Resolution

If multiple rules could match the same transaction:

- **First rule wins** - The first matching rule (by order) applies
- **No double-matching** - Each transaction is matched at most once
- **Manual override** - You can clear an auto-match and manually match differently

If you find rules conflicting, adjust the order so the more specific rule comes first.

## Amount Tolerance

For rules with amount fuzzy-matching:

**Exact match** - Amounts must be identical

**Rounding tolerance** - Allow differences up to $0.01 (for rounding)

**Fee tolerance** - Allow differences up to stated fee amount (for bank fees)

**Percentage tolerance** - Allow difference up to X% of amount

For example, a rule might allow FX transactions to differ by 2% due to conversion rates.

## Reference Number Matching

Many rules use reference number matching:

**Invoice number** - Matches bank transaction reference to invoice number in GL

**Check number** - For check payments, matches check number in bank feed to GL

**External reference** - Custom reference field you define

When the bank description contains the invoice/check number, the system can automatically identify the matching GL entry.

## Vendor/Customer Specific Rules

Some rules apply only to specific business partners:

1. Create the rule with condition: "Vendor ID = [specific vendor]"
2. Match to that vendor's GL accounts
3. Repeat for other vendors needing specific treatment

This is useful for vendors with unique payment patterns or GL accounts.

## Recurring vs. One-Time Rules

**Recurring rules** - Apply continuously (e.g., monthly rent payment)

**One-time rules** - Apply once for a specific period (e.g., special project)

Set an expiration date on one-time rules so they stop applying automatically.

## Audit Trail of Matches

Track which rule matched each transaction:

1. Go to **Accounting → Bank reconciliation → Cleared Transactions**
2. View matched transactions and see which rule matched them
3. If a match was made by rule X but was incorrect, disable rule X and manually match

This helps identify problematic rules.

## Best Practices

- **Start simple** - Begin with 3-5 core rules before adding complexity
- **Test before deployment** - Always test rules on sample data
- **Monitor effectiveness** - Review rule statistics monthly
- **Keep specific rules first** - Prevent overly-broad rules from matching unintended transactions
- **Document rules** - Use descriptive names and notes explaining the rule's purpose
- **Review quarterly** - As business patterns change, update rules
- **Archive old rules** - Clean up rules that are no longer needed

## Related Articles

- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Resolving discrepancies](/mnt/help-articles/articles/04-bank-reconciliation/4-6-resolving-discrepancies.md)
- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
