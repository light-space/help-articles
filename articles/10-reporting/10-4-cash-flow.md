# Cash Flow Statement

The Cash Flow Statement shows how cash moved into, out of, and between different activities of your business over a period. While the P&L shows profit or loss, the cash flow statement shows actual cash movements. Understanding cash flow is critical because profitable companies can still fail if they don't manage cash effectively.

[Open in Light →](https://app.light.inc/ledger-reports)

## Cash flow statement structure

The statement organizes cash flows into three sections:

**Operating activities**: Cash generated from core business operations:
- Cash received from customers
- Cash paid to suppliers and employees
- Interest paid
- Taxes paid

This shows whether operations generate sufficient cash to fund the business.

**Investing activities**: Cash used to buy or sell long-term assets:
- Purchase of fixed assets (equipment, buildings)
- Sale of fixed assets
- Investment acquisitions or disposals
- Loan originations or repayments to third parties

This shows capital expenditure and investment strategy.

**Financing activities**: Cash from or used for financing the business:
- Proceeds from debt issuance
- Debt repayments
- Equity issuance (share sales)
- Dividend payments
- Share repurchases

This shows how you fund your business.

The statement begins with cash at period start, adds/subtracts changes from three activity categories, and ends with cash at period end. The ending cash matches the cash balance on your balance sheet.

> Good to know: A profitable company can have negative cash flow if it collects receivables slowly or invests heavily in assets.

## Accessing the cash flow statement in Light

Generate your cash flow statement:

1. Navigate to **Planning & Reports → Reports**
2. Select period (month, quarter, or year)
3. Select entities to include (single entity or consolidated)
4. Select currency (transaction, local, or group)
5. Click **Generate**

Light displays the cash flow statement organized by operating, investing, and financing activities.

## Operating cash flow

Operating cash flow shows cash generated from your core business:

**Reconciliation method** (most common):

Start with net income from P&L. Net income is accrual-based, so adjust for non-cash items:

- Add back depreciation (non-cash expense)
- Add back amortization (non-cash expense)
- Add back loss on asset disposal
- Subtract gain on asset disposal
- Adjust for changes in working capital:
  - Increase in receivables = cash outflow (more time to collect)
  - Decrease in receivables = cash inflow (faster collection)
  - Increase in inventory = cash outflow (more inventory purchased)
  - Decrease in inventory = cash inflow (inventory sold)
  - Increase in payables = cash inflow (more time to pay)
  - Decrease in payables = cash outflow (earlier payment)

Light automatically calculates these adjustments from your ledger.

**Direct method** (less common):

Directly sum all cash inflows and outflows from operations without starting from net income.

> Tip: Operating cash flow should generally be positive and greater than net income. If operating cash flow is negative, investigate why.

## Investing cash flow

Investing cash flow shows capital expenditures and asset sales:

**Cash outflows**:
- Capital expenditures (CapEx): Purchases of fixed assets
- Long-term investments
- Loans provided to customers or related parties

**Cash inflows**:
- Proceeds from asset sales
- Repayment of loans provided
- Sale of investments

Calculate free cash flow = Operating Cash Flow - Capital Expenditures.

This shows cash available for debt repayment and dividends.

## Financing cash flow

Financing cash flow shows how you raise and deploy capital:

**Cash inflows**:
- Proceeds from debt issuance (new loans)
- Proceeds from equity issuance (share sales)
- Contributions from owners

**Cash outflows**:
- Debt repayments (principal only, not interest)
- Dividend payments
- Share repurchases
- Owner distributions

This shows how your capital structure evolves.

## Cash flow analysis

Key metrics from the cash flow statement:

**Operating cash flow ratio** = Operating Cash Flow ÷ Current Liabilities

Shows ability to pay short-term obligations from operations. A ratio > 1 indicates strong operational liquidity.

**Free cash flow** = Operating Cash Flow - Capital Expenditures

Shows cash available after necessary reinvestment. Used for debt repayment, dividends, and acquisitions.

**Cash conversion rate** = Operating Cash Flow ÷ Net Income

Shows what percentage of profit is converted to cash. >100% indicates working capital efficiency.

**Capital expenditure ratio** = Capital Expenditures ÷ Revenue

Shows investment intensity relative to sales.

Light can calculate these metrics automatically.

## Multi-period cash flow analysis

Compare cash flow to prior periods:

1. Navigate to **Planning & Reports → Reports**
2. Select periods to compare (current, prior year)
3. Light displays cash flows side-by-side with changes
4. Click any line to drill into transactions

This identifies cash flow trends and movements.

## Working capital analysis

The cash flow statement reveals working capital dynamics:

**Operating working capital** = Current Assets - Current Liabilities

Tie up in inventory, receivables, and payables.

**Cash conversion cycle** = Days Inventory Outstanding + Days Sales Outstanding - Days Payable Outstanding

Shows how long cash is tied up in operations. Shorter cycles are better.

Light can calculate these metrics from balance sheet and transaction data.

## Capital expenditure forecasting

Use historical CapEx to forecast future needs:

1. Navigate to **Planning & Reports → Reports**
2. View CapEx by category (equipment, buildings, vehicles)
3. Identify replacement cycles
4. Project future CapEx needs
5. Plan for financing

This supports budgeting and strategic planning.

## Multi-entity cash flow

For organizations with multiple entities:

- Generate cash flow for each subsidiary
- Generate consolidated cash flow combining all entities
- Eliminate inter-company cash flows
- Analyze cash generation by entity

Light automatically handles these consolidation mechanics.

## Multi-currency cash flow

Report cash flow in different currencies:

1. Navigate to **Planning & Reports → Reports**
2. Select **Currency**: Transaction, Local, or Group
3. Light displays amounts in your selected currency

For multinational companies:
- Each subsidiary's cash flow in its local currency
- Consolidated cash flow in group currency
- Light translates using average exchange rates for the period

## Cash position and liquidity

Monitor your cash position:

1. Navigate to **Planning & Reports → Reports**
2. View cash balance by account
3. Identify cash in restricted accounts
4. Project future cash positions based on committed obligations
5. Plan for cash shortfalls or surpluses

Light integrates with your bank accounts for real-time cash visibility.

## Dividend coverage

Assess your ability to pay dividends:

**Dividend coverage ratio** = Operating Cash Flow ÷ Dividends Paid

Shows how many times over you can fund dividends from operations. >2.0x is generally healthy.

Light calculates this automatically when you track dividend payments.

## Debt service coverage

For borrowers, lenders evaluate your ability to service debt:

**Debt service coverage ratio** = Operating Cash Flow ÷ Debt Service

(Debt service = principal + interest payments)

Light calculates this automatically when you track debt payments.

## Tax payment analysis

Understand your tax cash outflows:

1. Navigate to **Planning & Reports → Reports**
2. View tax payments made during the period
3. Compare to tax expense on P&L (may differ due to timing)
4. Estimate future tax payments

This supports cash forecasting and tax planning.

## Cash flow footnotes

Comprehensive cash flow reporting includes footnotes:

1. **Accounting policies**: Method used (direct vs. reconciliation)
2. **Significant changes**: Explanations for material movements
3. **Non-cash activities**: Significant non-cash transactions (stock issuance, asset exchange)
4. **Restrictions on cash**: Restrictions or conditions on cash use

Light maintains a footnote library. Attach relevant footnotes to your cash flow.

## Exporting cash flow statement

Export cash flow for external distribution:

1. Generate the cash flow statement
2. Click **Export**
3. Select format: PDF, Excel, or CSV
4. Light generates formatted output

The cash flow statement maintains your company branding in PDF format.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Balance sheet](10-2-balance-sheet.md)
- [Profit and loss](10-3-profit-loss.md)
- [Trial balance](10-5-trial-balance.md)
- [Custom reports and filters](10-9-custom-reports.md)
