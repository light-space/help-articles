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
2. Payment received: Debit Cash $118,000, Credit AR $118,000
3. Clearing posts an FX adjustment automatically: Debit FX loss $2,000, Credit AR $2,000
4. AR now shows zero; the invoice and payment are cleared

The realized FX gain or loss is always calculated against the original posting rate of the invoice. Any period-end revaluation booked in the meantime uses the separate unrealized FX gain/loss account and does not change the realized amount recognized at clearing — see [FX revaluations](/mnt/help-articles/articles/05-general-ledger/5-10-fx-revaluations.md).

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

**Payment entry:**
- Debit/Credit: Cash account (actual amount received or paid)
- Debit/Credit: AR/AP account (at the payment-date rate)

**FX adjustment entry (posted automatically with the clearing):**
- Debit: FX loss account, or Credit: FX gain account (the difference vs. the original posting rate)
- Offsetting line on the AR/AP account

The FX adjustment is a separate ledger transaction linked to the clearing event, so together the entries record:
- How much cash actually came in or went out
- The FX impact vs. original posting
- The cleared status of the documents

Sub-unit rounding differences from converting between transaction, local, and group currency are posted to a dedicated rounding account so the entries stay balanced in all three currencies.

## CTA (Cumulative Translation Adjustment)

CTA captures translation differences between an entity's local (functional) currency and the group (presentation) currency. At clearing, Light posts a CTA adjustment when the group-currency difference on the cleared item is not fully explained by the local-currency FX gain or loss translated to group currency.

**Scenario:**
- An invoice and its payment clear with a given FX difference in local currency
- The local-to-group rate moved between posting and clearing
- The remaining group-currency difference is posted to CTA

**GL entry for CTA:**
- Debit/Credit: Currency translation adjustment account (system account)
- Offsetting line on the AR/AP account

A CTA line always carries a nil local-currency amount — it adjusts only the group-currency balance, because it represents a translation-only difference. CTA is part of equity and flows through Other Comprehensive Income (OCI). CTA is also generated at period-end revaluation for accounts carried at the closing rate — see [FX revaluations](/mnt/help-articles/articles/05-general-ledger/5-10-fx-revaluations.md).

## Reversing a Clearing

If documents were cleared in error, the clearing can be reversed:

- Reversing a clearing also reverses the FX and CTA adjustment transactions that were posted with it
- The cleared documents return to **Posted** (or stay **Partially cleared** if other clearings remain)
- The original entries are never modified — reversals are posted as offsetting transactions, preserving the audit trail

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
2. For bank fees, select **Bank fees** as the deviation reason — Light automatically creates a Bank fees journal entry for the difference
3. FX and rounding differences are calculated and posted automatically as part of the clearing
4. For partial payments, clear the matched amount — the document stays **Partially cleared** until the remainder is settled

## Automatic Clearing

Light can automatically clear matching items:

**Rules trigger clearing when:**
- An identifier extracted from the bank transaction matches an open invoice number
- The payment's end-to-end ID or reference matches a posted document
- Amount and date, or amount and description, match a ledger transaction

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
