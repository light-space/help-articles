# Fixed Assets

Light treats fixed assets as a specialized form of accounting release. There is no separate "fixed asset" module — assets, their cost, additions, depreciation schedule, and remaining book value are all managed through the **Releases** framework using a **Fixed Asset** release template.

[Open in Light →](https://app.light.inc/releases)

## How fixed assets work in Light

A fixed asset in Light is a posted document line (a journal entry, AP bill, or AR sales invoice line) that has a **Fixed Asset** release template applied to it. When the document posts:

1. Light capitalizes the line amount to the **additions account** defined on the template (the asset account on the balance sheet).
2. Light schedules depreciation entries from the **contra account** (the depreciation/accumulated depreciation account on the template) to the expense account on the line, according to the template's method and duration.
3. The asset appears in the fixed asset register and continues posting depreciation each period until the schedule is complete.

This means the same engine that handles prepayments and deferred revenue also handles fixed assets — you just pick a different template type. See [Configuring releases](9-2-configuring-releases.md) and [Deferred entries](../05-general-ledger/5-5-deferred-entries.md) for the underlying mechanics.

## The fixed asset register

The fixed asset register lives at [**Accounting → Releases**](https://app.light.inc/releases). To view only fixed assets, filter the page by **Fixed asset** type.

For each asset you can see:

- Cost (original capitalized amount)
- Accumulated depreciation to date
- Remaining book value
- Depreciation method and remaining periods
- Source document (the JE, bill, or invoice that created the asset)
- Posted and pending release entries

Open a row to view the full depreciation schedule and book value chart. This view is the audit-ready supporting subledger for the fixed asset accounts on the balance sheet.

## Setting up a Fixed Asset release template

Before entering assets, configure at least one Fixed Asset template. Templates are reusable — most organizations create one per asset class (e.g., "5-Year Furniture", "3-Year Laptops", "10-Year Buildings").

1. Navigate to [**Accounting → Release templates**](https://app.light.inc/release-templates)
2. Click **+ New**
3. Set **Type** to **Fixed asset**
4. Fill in:
   - **Name** — descriptive (e.g., "5-Year Straight-Line — Furniture")
   - **Method** — **Straight line with partial adjustment** or **Reducing balance**
   - **Additions account** — the balance sheet asset account where the cost is capitalized (required for Fixed asset templates)
   - **Contra account** — the accumulated depreciation account (the contra-asset account that depreciation credits against)
   - **Default Duration (months)** — useful life in months (e.g., 60 for 5 years)
   - **Initial Amount Percentage** — for straight-line, the percentage applied in the first period
   - **Reducing Rate Percentage** — for reducing balance, the rate applied each period
5. Click **Create**

> Tip: Use descriptive template names that include duration and asset class. This makes the template list easy to scan when entering assets later.

## Entering a fixed asset

Fixed assets can be entered from any of three document types, depending on how the asset was acquired:

| Acquisition | Document type |
|---|---|
| Purchased from a vendor | AP bill |
| Sold/transferred to a customer entity | AR sales invoice |
| Capitalized internally, transferred, or migrated from a legacy system | Manual journal entry |

In each case, the workflow is the same: enter the document line as you normally would, but apply a **Fixed Asset** release template on the line.

### From an AP bill

1. Open or create an AP bill in **Spend management → Bills**
2. On the line item:
   - **Description** — describe the asset
   - **Amount** — the capitalized cost
   - **GL Account** — the depreciation **expense** account (where depreciation will ultimately post)
   - **Template** — pick the Fixed Asset release template, then set start and end dates
3. Save and post the bill

When posted, Light creates the AP liability for the full amount, capitalizes the cost to the additions account on the template, and begins posting depreciation entries on schedule.

### From a manual journal entry

Use a journal entry when there is no vendor invoice — for example, migrating opening fixed assets from a legacy system, capitalizing internally developed assets, or recording a transfer.

1. Navigate to **Accounting → Journal entries** and create a new JE
2. On the asset line, set the GL Account to the depreciation expense account and apply a **Fixed Asset** release template with the appropriate start and end dates
3. Balance the entry against the offsetting account (cash, suspense, intercompany, etc.)
4. Post the entry

### From an AR sales invoice

Used for inter-entity transfers or sales where the asset is being recognized on the receiving entity. The line behavior mirrors the bill flow — apply the Fixed Asset template via the **Accrual template** field on the invoice line.

## Example: $12,000 office furniture purchase

To record office furniture purchased from a vendor for $12,000, depreciated straight-line over 5 years:

**Bill line:**

| Field | Value |
|-------|-------|
| Description | Office furniture |
| Amount | $12,000 |
| GL Account | 500500 — Office Furniture (depreciation expense) |
| Template | "5-Year Furniture" (Fixed Asset, 60 months, straight-line) |

**Initial posting (when the bill is posted):**
- Dr 800800 — Furniture and Assets $12,000 (additions account)
- Cr Accounts Payable $12,000

**Monthly depreciation (repeated 60 times):**
- Dr 500500 — Office Furniture $200 (expense)
- Cr 800800 — Accumulated Depreciation — Furniture $200

After 60 months, the asset has $0 remaining book value and the depreciation schedule is complete.

## Migrating an existing fixed asset register

Light does not support direct import of a fixed asset register from a legacy system. To migrate:

1. For each asset in the legacy register, calculate the **remaining net book value** as of the cutover date (cost minus accumulated depreciation already posted in the legacy system)
2. Create a manual journal entry per asset (or one consolidated JE per asset class) that:
   - Debits the line with the **remaining net book value** as the amount
   - Sets the GL Account to the depreciation expense account
   - Applies a **Fixed Asset** release template whose duration equals the **remaining useful life** at cutover
3. Post the entry

This recreates the asset in Light's register at its current book value and resumes depreciation over the remaining useful life. Verify the register at [**Accounting → Releases**](https://app.light.inc/releases) (filtered by **Fixed asset** type) matches the legacy register before going live. See [Go-live readiness](../01-getting-started/1-8-go-live-readiness.md) for the broader cutover sequence.

## Adjustments, disposals, and impairments

Once a release has posted entries, you cannot delete it — Light's ledger is immutable. To handle changes:

- **Adjustments to useful life or amount**: Edit the release; Light creates new release entries that net against future scheduled entries
- **Disposals**: Post a manual journal entry that writes off remaining book value (Dr accumulated depreciation, Dr loss on disposal, Cr the additions account) and stop further depreciation by ending the release at the disposal date
- **Impairments**: Post a manual journal entry recognizing the impairment loss against the additions account, then adjust the release schedule to depreciate the new lower book value over the remaining useful life

For full transactional control over complex scenarios, see [Manual journal entries](../05-general-ledger/5-4-manual-journal-entries.md).

## Multi-currency considerations

Fixed Asset release templates honor the multi-currency rules of the underlying release framework. Cost is capitalized at the transaction-date FX rate, and depreciation entries post at the rate appropriate to your accounting policy (transaction, local, or group). FX revaluation of fixed asset balances follows the standard FX revaluation process — see [FX revaluations](../05-general-ledger/5-10-fx-revaluations.md).

## Reporting

The fixed asset section of the balance sheet summarizes capitalized cost and accumulated depreciation across all fixed asset accounts. For per-asset detail behind those balances, use the fixed asset register at [**Accounting → Releases**](https://app.light.inc/releases) filtered by **Fixed asset** type.

For audit support, the register is the supporting subledger that should reconcile to the fixed asset and accumulated depreciation accounts on the trial balance — see [Audit-ready record keeping](9-9-audit-ready-records.md) and [Trial balance](../10-reporting/10-5-trial-balance.md).

## Related articles

- [Configuring releases: depreciation, prepayments, deferred revenue](9-2-configuring-releases.md)
- [Accruals, prepayments, deferred revenue, and depreciation](9-3-accruals-prepayments.md)
- [Deferred entries (accruals and deferrals)](../05-general-ledger/5-5-deferred-entries.md)
- [Balance sheet](../10-reporting/10-2-balance-sheet.md)
- [Go-live readiness and minimum viable setup](../01-getting-started/1-8-go-live-readiness.md)
