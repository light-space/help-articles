# Multi-Currency Payments

Each bill in Light carries its own currency, independent of the company entity's functional currency or the bank account the payment is made from. Light handles FX conversion in the background based on the bill currency, the paying bank account, and the payment date.

[Open in Light →](https://app.light.inc/payables)

## How Currency Is Set on a Bill

- A bill's **currency** is captured when the bill is created (from the uploaded document, vendor default, or manual entry)
- The currency is shown in the bill header and in the bills list
- The amount on the bill is in the bill currency

## How Payment Currency Works

When a bill is paid:
- The payment is always sent in the **bill currency** — the vendor receives the amount stated on the bill
- The **From account** (the company bank account on the bill) determines the currency your account is debited in
- If the bill currency matches the bank account currency, the account is debited at face value
- If the bill currency differs from the bank account currency, the bank or payment provider converts the amount at execution, and Light books the actual debited amount in the account currency

The FX conversion happens automatically when the payment is executed — there is no manual FX rate override in the payment entry dialog. For accounting conversions (and when a bill is marked as paid manually without an executed payment), Light applies its exchange rate for the payment date: ECB reference rates by default, with any company- or entity-level exchange rate overrides taking precedence.

## Bills Listed in Multiple Currencies

The Bills list shows the bill amount in its native currency. Filters and totals can be applied across currencies; multi-currency totals reflect each currency separately.

## Bank Accounts and Currencies

Each company bank account is denominated in a specific currency (see **Settings → Bank accounts**). To pay vendors in a particular currency without FX conversion, set up a bank account in that currency and select it as the **From account** on bills in that currency.

## FX Gain / Loss Posting

When a bill in one currency is paid from a bank account in another currency, the difference between the bill's posted value and its value on the payment date creates a realized FX gain or loss. This is posted automatically by Light's accounting engine when the payment clears the bill, to the system FX gain and FX loss accounts.

For period-end FX revaluation across open AP balances, see the FX revaluation tools in the accounting module.

## Related Articles

- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Multi-entity AP](/articles/07-accounts-payable/7-12-multi-entity-ap.md)
