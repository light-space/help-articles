# Automated Bank Reconciliation

Light can automatically match bank transactions to accounting entries, dramatically reducing manual reconciliation work. This article explains how automated reconciliation works and how to use it.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## The Reconciliation Interface

When you open **Accounting → Bank reconciliation**, you see two tabs at the top of the page:

- **Accounts** — Lists all connected bank accounts with their entity, currency, bank balance, and sync status.
- **Rules** — Shows the matching rules that control how transactions are reconciled (both system rules and custom rules you create).

From this page you can also click **+ Connect bank** to add a new bank connection or **+ Create rule** to add a custom matching rule.

## Opening an Account for Reconciliation

Click any bank account row on the **Accounts** tab to open its reconciliation view. The reconciliation view shows the account name at the top (e.g., "BANK USD") with a dropdown to switch between accounts, and three tabs:

- **Unmatched** — Bank transactions and ledger entries that have not yet been reconciled.
- **Matched** — Transactions that have already been successfully reconciled.
- **Excluded** — Transactions intentionally excluded from reconciliation.

## The Unmatched Tab

The **Unmatched** tab is a split-panel layout where you do most of your reconciliation work.

A filter bar at the top lets you narrow transactions by date (e.g., "Transactions before 07 Feb 2026") and apply additional filters.

**Left panel — Bank transactions**: Shows imported bank transactions with columns for Date, Transaction name, Reference, and Amount. Each row has a checkbox for selection. The bottom of the panel shows the total count and balance of unmatched bank transactions. Above the table you can see the sync status (e.g., "Completed") and when the account was last synced (e.g., "3 hours ago Synced"). The panel also includes import/export icons and a search bar.

**Right panel — Ledger transactions**: Shows accounting entries available for matching. You can toggle between **Open transactions** (unmatched ledger entries available for reconciliation) and **Closed transactions** (already matched or closed entries). Columns include Date, Transaction ID, Description, and Amount. This panel also has an export icon and search bar.

**Action bar**: Between the filter bar and the panels, you'll find the key reconciliation actions:

- **Auto reconcile** — Runs the matching engine to automatically find and propose matches based on your reconciliation rules.
- **Exclude** — Removes selected transactions from the reconciliation process (useful for bank fees, pending items, or transactions you want to handle separately).
- **Convert to rule** — Creates a new matching rule based on the selected transaction, so similar future transactions are handled automatically.
- **Difference** — Displays the running difference between your selected bank transaction(s) and selected ledger transaction(s). When nothing is selected, the difference shows 0.00. As you select items, the value updates dynamically.
- **Match** — Confirms the selected bank and ledger transactions as a reconciled pair. This button is enabled when you have selections on both sides.

## How to Manually Match Transactions

To manually reconcile a bank transaction with a ledger entry:

1. Go to **Accounting → Bank reconciliation** and click the bank account you want to reconcile.
2. On the **Unmatched** tab, select one or more bank transactions on the left panel by checking their checkboxes.
3. Switch the right panel to **Open transactions** to see available ledger entries.
4. Select the matching ledger entry (or entries) on the right panel.
5. Check the **Difference** indicator — when the amounts balance, the difference shows 0.00.
6. Click **Match** to confirm the reconciliation.

The matched transactions move from the **Unmatched** tab to the **Matched** tab.

> Good to know: You can match multiple bank transactions to a single ledger entry or vice versa. The Difference indicator helps you verify that the selected items balance before confirming.

## Running Auto Reconcile

Instead of matching transactions one by one, you can let Light's matching engine do the work:

1. Go to **Accounting → Bank reconciliation** and click into a bank account.
2. On the **Unmatched** tab, click **Auto reconcile**.
3. Light applies your reconciliation rules (both system and custom) to find matches.
4. Matched transactions are moved to the **Matched** tab automatically.

Auto reconcile uses the rules defined on the **Rules** tab (see below) to determine matches. It processes rules in order, and each unmatched bank transaction is tested against the rules until a match is found.

## Understanding Reconciliation Rules

Reconciliation rules control how Light matches bank transactions to ledger entries. You can view and manage rules by clicking the **Rules** tab on the main Bank reconciliation page.

The rules table shows:

- **Name** — The rule's descriptive name.
- **Trigger** — What condition activates the rule.
- **Action** — What the rule does when triggered.
- **Created by** — Whether the rule is a system default ("Light") or user-created.
- **Runs** — How many times the rule has been applied.

### System Rules

Light includes several built-in rules that handle common matching scenarios:

- **Register payment for open invoices** — Matches bank deposits and payments to outstanding customer and vendor invoices.
- **Create Journal Entry for card transactions** — Automatically creates and matches journal entries for corporate card transactions.
- **Match by bank transaction end-to-end reference** — Uses end-to-end payment references (common in SEPA and wire transfers) to find matches.
- **Match by document number** — Matches based on invoice or document numbers found in the bank transaction reference.
- **Match by amount and description** — Finds matches where both the amount and transaction description align with a ledger entry.
- **Match by amount and date** — Matches transactions where the amount and date closely correspond to a ledger entry.

System rules are created by Light and cannot be deleted, but you can create additional custom rules that run alongside them.

## Creating Custom Matching Rules

To create a rule for a specific matching scenario:

1. Go to **Accounting → Bank reconciliation**.
2. Click **+ Create rule** (or go to the **Rules** tab and click the button there).
3. In the **Add rule** panel, fill in:
   - **Name** — A descriptive name for your rule.
   - **When** — Natural language instructions describing when this rule should apply. For example: "When bank transaction reference contains 'RENT' and year is 2025" or "When transaction name includes 'Payroll'".
   - **Action** — Select what happens when the rule matches. The default is "Create and match with a journal entry."
   - **Details** — Specify the business partner and line-item details for the journal entry that gets created, including GL account, description, accrual, tax code, cost center, country, geography, and project code.
4. Click **Validate & Save** to save the rule.

You can also create rules directly from the reconciliation view by selecting an unmatched transaction and clicking **Convert to rule**. This pre-fills the rule based on the selected transaction's details.

> Good to know: Custom rules are especially useful for recurring transactions like rent, insurance, subscriptions, or payroll — transactions that follow a consistent pattern every month.

## The Matched Tab

The **Matched** tab shows all transactions that have been successfully reconciled. Each row displays:

- **Transaction** — A clickable transaction ID with a document type prefix (e.g., CC/ for credit card, BP/ for bank payment, JE/ for journal entry).
- **Name** — The transaction or business partner name.
- **Description** — Details about the transaction.
- **Date** — When the transaction occurred.

You can use the **Add filter** option and the export button to narrow down or download matched transactions. Click any transaction ID to view its full details.

## The Excluded Tab

The **Excluded** tab lists transactions that have been intentionally removed from the reconciliation process. Each row shows the Date, Type, Transaction name, and Amount.

Common reasons to exclude a transaction:

- **Pending transactions** that haven't fully cleared yet.
- **Duplicate entries** that shouldn't be matched.
- **Bank fees or charges** that need to be handled through a separate journal entry process.

To exclude a transaction, select it on the **Unmatched** tab and click **Exclude**. Excluded transactions can be moved back to the unmatched queue if needed.

## Unmatched Transactions

Transactions that remain on the **Unmatched** tab after running auto reconcile may need manual attention. Common reasons include:

- **No corresponding ledger entry** — The bank shows a transaction but no matching accounting entry exists yet. You may need to create a journal entry or wait for the entry to be posted.
- **Amount mismatch** — Slight differences due to rounding, bank fees, or partial payments can prevent automatic matching.
- **Timing differences** — The bank may record a transaction a few days before or after the ledger entry is posted.
- **Missing or incorrect references** — If the bank transaction doesn't include a recognizable invoice or document number, reference-based rules won't match.

To resolve unmatched items, review them individually, create or adjust the corresponding ledger entries, and then manually match or re-run auto reconcile.

## FX Reconciliation

For multi-currency bank accounts, the reconciliation view works the same way. Bank transactions in foreign currencies are displayed in the account's currency, and the matching engine compares converted amounts when looking for matches. Any FX gains or losses resulting from rate differences between the bank transaction date and the ledger entry date are calculated automatically.

## Best Practices

- **Reconcile frequently** — Daily or weekly reconciliation prevents large backlogs and makes it easier to investigate unmatched items while the details are fresh.
- **Use Auto reconcile first** — Let the matching engine handle the straightforward matches, then focus your time on the exceptions.
- **Create rules for recurring transactions** — Set up custom rules for predictable payments like rent, subscriptions, and payroll to eliminate repetitive manual matching.
- **Review excluded items periodically** — Check the Excluded tab to make sure items haven't been sitting there longer than intended.
- **Use Convert to rule** — When you manually match a transaction that will recur, click "Convert to rule" to automate it going forward.

## Related Articles

- [Reconciliation automation rules](/mnt/help-articles/articles/04-bank-reconciliation/4-5-automation-rules.md)
- [Resolving discrepancies](/mnt/help-articles/articles/04-bank-reconciliation/4-6-resolving-discrepancies.md)
- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
