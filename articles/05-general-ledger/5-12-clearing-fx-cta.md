# Clearing, FX Gain/Loss, and CTA

Clearing (matching) transactions and recording foreign exchange impacts are critical accounting processes. This article explains how clearing works, how FX gains and losses are recorded, and how cumulative translation adjustment (CTA) is handled.

[Open in Light →](https://app.light.inc/ledger-transactions)


## Clearing Explained

Clearing is matching two GL entries to show they've been settled:

**AP Example:**
- Invoice Payable posts: Debit Expense, Credit AP
- When paid, Payment posts: Debit AP, Credit Cash
- Both are matched/cleared to show the invoice has been paid

**AR Example:**
- Invoice Receivable posts: Debit AR, Credit Sales
- When customer pays, Payment posts: Debit Cash, Credit AR
- Both matched/cleared to show the invoice has been collected

Clearing links the entries without modifying them—both remain as originally posted.

## Clearing Workflow

Typical clearing process:

1. **Transaction posts** - Document creates GL entries
2. **Clearing happens** - Second entry matches the first
3. **Both marked cleared** - System shows they've been matched
4. **Audit trail** - Records who cleared and when

For example:
- Invoice created and posted to GL
- Bank processes payment
- User matches invoice to payment (manually or auto)
- Both marked as cleared

## Partial Clearing

When amounts don't match exactly:

**Scenario:**
- Invoice for $10,000
- Two partial payments: $7,000 and $3,000

**Clearing:**
1. First payment clears $7,000 of the invoice
2. Invoice status becomes "Partially Cleared"
3. Second payment clears remaining $3,000
4. Invoice status becomes "Cleared"

GL shows all three entries linked together.

## Clearing with FX Adjustments

When clearing involves FX differences:

**Scenario:**
- AR Invoice posted: 100,000 EUR at rate 1.20 = 120,000 USD
- Customer payment received: 100,000 EUR at rate 1.18 = 118,000 USD
- FX loss: 2,000 USD

**GL entries:**
1. Invoice posts: Debit AR $120,000, Credit Sales $120,000
2. FX revaluation: Debit FX Loss $2,000, Credit AR $2,000 (GL now $118,000)
3. Payment received: Debit Cash $118,000, Credit AR $118,000
4. AR now shows zero; amounts are cleared

Or, without revaluation:
1. Invoice posts: $120,000
2. Payment posts: $118,000
3. Clearing shows match at $118,000 with $2,000 FX loss recorded in clearing entry

## Realized vs. Unrealized FX Gains/Loss

**Unrealized FX Gain/Loss**
- Occurs when unsettled foreign currency item revalues
- Example: AR in EUR revalues due to rate change
- Flows to P&L (or OCI under IFRS)
- Reversed if rate changes again before settlement

**Realized FX Gain/Loss**
- Occurs when foreign currency transaction finally settles
- Example: Receive EUR cash at different rate than invoice posting
- Final, actual gain or loss
- Not reversed (it's real)

Most FX transactions have both unrealized (during holding period) and realized (at settlement) components.

## FX Clearing Entry

When clearing foreign currency items:

**Entry for realized FX gain/loss:**
- Debit/Credit: Cash account (actual amount received)
- Debit/Credit: AR/AP account (to adjust for FX)
- Debit/Credit: FX Realized Gain/Loss account (the difference)

This entry records:
- How much cash actually came in
- The FX impact vs. original posting
- The cleared status of the documents

## CTA (Cumulative Translation Adjustment)

CTA arises when translating foreign subsidiary GL:

**Scenario:**
- Subsidiary in UK operates in GBP
- Parent in US reports in USD
- UK subsidiary assets: 1,000,000 GBP
- Convert at start of year: 1.30 USD/GBP = 1,300,000 USD posted
- At year-end: 1.28 USD/GBP = 1,280,000 USD actual
- CTA: 20,000 USD loss (GBP weakened)

**GL entry for CTA:**
- Debit: CTA account (equity)
- Credit: Asset account (to reduce from 1,300,000 to 1,280,000)

CTA is part of equity and flows through Other Comprehensive Income (OCI).

## CTA Reversal

When a CTA item settles or is disposed:

**Scenario:**
- Subsidiary sold to third party
- UK assets previously had CTA of (20,000) USD loss
- Upon sale, CTA is realized
- Entry: Debit Gain on Sale, Credit CTA (reversal)
- Gain on Sale now includes the CTA

When you sell/liquidate a subsidiary, its CTA flows to realized gains/losses.

## Deferred Tax on FX

FX gains and losses have tax implications:

**Taxable FX Gains/Loss:**
- Most jurisdictions tax realized FX gains/losses
- Unrealized gains typically not taxed until realized

**Deferred Tax Accounting:**
- If financial statement shows FX loss but tax doesn't recognize it yet
- Create deferred tax asset

Example:
- Financial: FX loss of $10,000 (reduces pre-tax income)
- Tax: No deduction allowed until paid (deferred)
- Create deferred tax asset: Debit Deferred Tax Asset, Credit Tax Expense

## Netting FX Positions

For companies with natural hedges:

**Scenario:**
- AP in EUR: owe 100,000 EUR
- AR in EUR: owed 80,000 EUR
- Net position: owe 20,000 EUR (10% of exposure)

**Treatment:**
- Don't separately revalue; net them out
- Only the net position gets revaluation entry
- Reduces GL volatility and more accurately reflects economic position

This requires specific account structure and clearing logic.

## Hedging and Clearing

For hedged FX positions:

**Example:** Forward contract hedge
- AR in EUR for 100,000 EUR at rate 1.20 (posted as 120,000 USD)
- Forward contract locked at 1.18
- Customer pays at 1.19

**Result:**
- AR realized loss: 1.20 to 1.19 = 1,000 USD loss
- Forward contract realized gain: 1.18 to 1.19 = 1,000 USD gain
- Net: Zero FX impact (hedge worked)

Hedge accounting matches the gains and losses for net zero impact.

## Clearing Discrepancies

Sometimes clearing amounts don't match:

**Possible reasons:**
- Bank fees reduced payment
- Rounding differences
- Partial payment
- Data entry error

**Resolution:**
1. Identify reason for discrepancy
2. Create FX or other adjustment if legitimate
3. Clear the matched amount
4. Record remaining as pending or excluded

## Automatic Clearing

Light can automatically clear matching items:

**Rules trigger clearing when:**
- Bank transaction amount = Invoice amount
- Dates are within tolerance
- Accounts match
- Reference numbers match

Automatic clearing saves manual work but requires proper GL setup and matching rules.

## Reporting FX and Clearing

**Income Statement:**
- Realized FX gains and losses as line item
- Separately from operating results

**Balance Sheet:**
- OCI or Equity section shows unrealized FX gains/losses
- CTA shown separately in equity

**Cash Flow:**
- Actual cash impacts of FX (realized gains/losses)
- Not unrealized (they're non-cash)

**Notes:**
- Explain FX policy
- Discuss hedging strategies
- Show FX impact by currency

## Best Practices

- **Match frequently** - Daily or weekly prevents large backlogs
- **Document basis** - Note why amounts don't match exactly
- **Monitor CTA** - Track CTA balance for foreign operations
- **Understand policy** - Know whether you accrue or defer FX
- **Test hedges** - For hedged positions, verify effectiveness
- **Reconcile currencies** - Each currency should reconcile separately
- **Report clearly** - Separately show FX impacts in reports
- **Plan for volatility** - Budget for FX impacts in forecasting

## Related Articles

- [FX revaluations](/mnt/help-articles/articles/05-general-ledger/5-10-fx-revaluations.md)
- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
- [Multi-entity ledger management](/mnt/help-articles/articles/05-general-ledger/5-6-multi-entity-ledger.md)
- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
