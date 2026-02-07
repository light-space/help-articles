# Bank Integrations Overview

Bank integrations connect your financial institution accounts directly to Light, automatically syncing transactions for cash management and reconciliation. Rather than manually entering deposits and payments, bank feeds provide real-time visibility and streamlined reconciliation.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

Bank integrations provide:

- **Transaction feeds**: Automatic daily or real-time transaction downloads
- **Multi-currency accounts**: Support for accounts in different currencies
- **Balance updates**: Real-time account balance visibility
- **Reconciliation support**: Transaction matching and reconciliation
- **Multi-bank support**: Connect accounts from multiple financial institutions
- **Cash forecasting**: Use transaction data for cash planning

This automates cash posting and reconciliation.

## Supported banks

Light supports connections with:

- **Major banks**: Chase, Bank of America, Citibank, Wells Fargo (US)
- **International banks**: HSBC, Barclays, Santander, ING, Deutsche Bank
- **Online banks**: Revolut, Wise, N26
- **Business platforms**: Stripe, Airwallex, Square, PayPal
- **Via aggregators**: Plaid (covers 12,000+ institutions)

If your bank isn't directly supported, use Plaid to connect.

## Setting up a bank connection

To connect a bank account:

1. Navigate to **Settings (gear icon) > Bank Connections**
2. Click **Connect Bank**
3. Search for your bank name
4. Click your bank (you're redirected to the bank's secure login)
5. Sign in to your online banking (Light never sees your password)
6. Authorize Light to access account information
7. Select which accounts to connect
8. Confirm connection is active in Light

Light then begins receiving daily transaction feeds.

## Transaction feed frequency

Configure how often Light receives updates:

1. Navigate to **Settings > Bank Connections > [Bank] > Sync Settings**
2. Select frequency:
   - **Real-time**: Updates throughout the day (if bank supports)
   - **Daily**: Once daily (typical end-of-business)
   - **Weekly**: Once weekly (sufficient for some users)
3. Select time for scheduled syncs (if not real-time)
4. Save

Real-time is ideal for cash visibility; daily is sufficient for most reconciliation needs.

## Transaction matching and posting

When bank transactions sync:

1. Light receives transaction detail: date, amount, description, counterparty
2. Light attempts to match to existing GL transactions:
   - For AR: Match to customer payment to invoice
   - For AP: Match to vendor payment to bill
   - For other: Match to journal entry
3. If match found: Transaction status updates to "Matched"
4. If no match: Transaction appears as "Unmatched" pending review
5. You can manually match unmatched items

Light uses amount, date, and description for matching.

## Bank reconciliation

Reconcile GL accounts to bank statements:

1. Navigate to **Ledger > Bank Reconciliation**
2. Select bank account
3. Light displays:
   - GL balance (from Light ledger)
   - Bank statement balance (from bank feed)
   - Outstanding items (in Light but not on statement, or vice versa)
4. Identify reconciling items:
   - Pending deposits (recorded in Light, not yet at bank)
   - Outstanding checks (recorded in Light, not yet cleared)
   - Bank fees (on statement, not yet recorded in Light)
5. Complete reconciliation
6. Mark as "Reconciled"

Monthly reconciliation is standard practice.

> Good to know: Bank reconciliation confirms GL accuracy and identifies discrepancies early.

## Bank fee handling

Banks charge monthly service fees, NSF fees, etc:

1. Bank fee appears on bank statement
2. Light bank feed syncs the fee
3. Light prompts you to record the GL entry
4. You accept the fee and specify GL account (bank charges/fees)
5. Light posts automatically

This ensures bank fees don't cause reconciliation discrepancies.

## Handling deposits in transit

When you deposit a check or transfer:

1. You create a GL entry recording the deposit
2. Bank takes 1-2 days to post
3. Bank transaction appears in next day's feed
4. Light reconciliation shows item as "Pending" until bank posts
5. Once bank posts, mark as "Cleared"

Light tracks pending items separately until cleared.

## Outstanding check management

When you write a check:

1. You create a GL entry recording the payment
2. Check is outstanding (issued but not yet cleared)
3. Bank shows as pending withdrawal
4. When recipient cashes check, bank posts the withdrawal
5. Light reconciliation matches to your GL entry
6. Check moves from outstanding to cleared

Light maintains outstanding item tracking.

## Multi-currency bank accounts

For accounts in different currencies:

1. Connect accounts in each currency
2. Light maintains separate GL accounts per currency
3. Bank feed syncs in account currency
4. Light shows balances in each currency
5. FX translation happens only in consolidation

This preserves currency perspective.

## Cash position reporting

Monitor cash across all accounts:

1. Navigate to **Planning & Reports → Reports**
2. View:
   - Balance in each bank account (by currency)
   - Total cash across all accounts
   - Recent activity in each account
   - Forecast based on pending transactions
3. Real-time visibility into liquidity

This supports cash management and forecasting.

## Handling transfers between accounts

When you transfer between your own accounts:

1. You create GL entries showing withdrawal from one account and deposit to another
2. Bank feeds show both transactions
3. Light recognizes as transfer (eliminates in reporting, doesn't double-count)
4. Reconciliation shows transfer matches between accounts

Light prevents double-counting internal transfers.

## Troubleshooting bank connections

**Connection failed**: Re-authorize with your bank, verify online banking credentials, check if bank requires additional authentication.

**Transactions not syncing**: Check sync status in Light, verify bank account is configured for export, contact bank if feed not updating.

**Duplicate transactions**: Verify bank feed isn't importing duplicates (some banks send corrected and original), check Light matching to prevent double-posting.

**Missing transactions**: Check date range of feed, verify transaction hasn't been filtered out, contact bank if transaction should have appeared.

**Reconciliation discrepancies**: Review GL entries vs. bank statement, identify timing differences (pending items), verify all fees are recorded.

## Bank feed limitations

Be aware of bank feed limitations:

- Most banks provide 90-365 days of history (older data may not be available)
- Some smaller transactions may be batched/grouped
- Holiday processing may delay posting by 1-2 days
- Wire transfers show in some banks, not others

Document your bank's specific feed format.

## Exporting bank reconciliation

Archive reconciliation records:

1. Complete reconciliation in Light
2. Click **Export**
3. Download as PDF or Excel
4. Includes GL balance, bank balance, reconciling items
5. Sign and archive

This creates evidence of reconciliation for auditors.

## Multi-bank aggregation

For organizations with accounts at multiple banks:

1. Connect all bank accounts in Light
2. Light receives feeds from all banks
3. Cash Position report shows consolidated cash across banks
4. Each account reconciled separately
5. Consolidated cash visibility

This consolidates multi-bank cash management.

## Fraud and exception detection

Light can flag unusual transactions:

1. Unusually large transaction (configure threshold)
2. Transaction outside normal hours (configure expected transaction times)
3. Transactions to new counterparties
4. Unusual frequency of similar transactions

Configure exception alerts in bank connection settings.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Stripe integration](11-6-stripe.md)
- [Airwallex integration](11-7-airwallex.md)
- [Cash flow statement](../10-reporting/10-4-cash-flow.md)
