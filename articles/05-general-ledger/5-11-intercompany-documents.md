# Intercompany Documents

Intercompany documents record transactions between entities in your corporate group. This article explains how to configure intercompany accounts and create intercompany journal entries.

[Open in Light →](https://app.light.inc/journal-entries)

## What Are Intercompany Transactions?

Intercompany transactions are financial activities between entities within the same corporate group:

**Examples:**
- Parent company loans cash to subsidiary
- Subsidiary sells products to another subsidiary
- Division A charges Division B for shared services
- Entity A transfers assets to Entity B

These transactions don't go outside the group, so they're eliminated during consolidation.

## Setting Up Intercompany Configuration

Before creating intercompany journal entries, configure which accounts are used for intercompany postings.

1. Go to **Accounting → Chart of accounts**
2. Open the **Intercompany config** section
3. Click **+ Add configuration**
4. Fill in the fields:

| Field | Description |
|---|---|
| **From account code** | Start of the account code range this rule applies to |
| **To account code** | End of the account code range |
| **Debit intercompany account** | Account used for debit-side intercompany postings |
| **Credit intercompany account** | Account used for credit-side intercompany postings |
| **Eliminate source line** | Toggle on to mark the source line for elimination during consolidation (defaults to on) |

At least one of debit or credit intercompany account must be set. You can click any existing config row to edit it.

## Creating an Intercompany Journal Entry

1. Go to **Accounting → Journal entries**
2. Click **+ Create journal entry** and select the intercompany type
3. Fill in the header fields:

| Field | Required |
|---|---|
| **Currency** | ✅ |
| **Description** | — |
| **Posting date** | — |
| **Valuation date** | — |
| Custom properties | — |

4. Configure the **FROM line** (source entity):
   - **Entity** — the originating company entity
   - **Account** — the GL account
   - **Eliminate** — whether this line is eliminated at consolidation (Yes / No)
   - **Description** — optional line note
   - **Tax code** — optional
   - **Debit / Credit amount**

5. Configure one or more **TO lines** (receiving entities) with the same fields. Use **+ Add line** to add more TO lines.

6. Review the **Net impact** panel (bottom of the form) — shows a real-time preview of the net effect per entity and account as you enter amounts.

7. Click **Save** to keep as Draft, or **Post** to finalise.

> **Good to know:** Debit and credit totals are shown at the bottom of the lines table. The entry must balance before it can be posted.

## Statuses

| Status | Description |
|---|---|
| **Draft** | Saved but not yet posted. Still editable, can be deleted. |
| **Posted** | Finalised and reflected in the GL. Read-only. |

## Net Impact Preview

While a journal entry is in **Draft**, the **Net impact** panel updates in real time as you edit lines. It shows the net effect of the transaction per entity and account before you commit.

After posting, the panel shows the actual posted net impact. The tooltip reads:
> *"Displays the net effect of intercompany transactions. These are reversed via elimination entries to ensure accurate reporting, while this view highlights their original impact."*

## Entry Detail Tabs

When viewing an intercompany journal entry, three tabs are available on the right panel:

| Tab | Contents |
|---|---|
| **Activity** | Audit log of all changes to the entry |
| **Documents** | Attachments linked to the entry |
| **Postings** | The individual GL postings generated (visible after posting) |

## Filtering the Journal Entries List

The intercompany journal entries list can be filtered by:

- **Posting date** (defaults to current quarter)
- **Valuation date**
- **Currency**
- **Status** (Draft / Posted)

Free-text search is also available.

## Elimination and Consolidation

The **Eliminate** field on each line and the **Eliminate source line** toggle in intercompany config determine which lines are flagged for elimination when producing consolidated statements.

At consolidation:
- Lines marked for elimination are excluded from the consolidated GL
- Intercompany receivables and payables offset each other
- Only external transactions remain in consolidated output

Entity-level GL reports still show intercompany amounts in full.

## Regulatory and Tax Context

**GAAP / IFRS:**
- Intercompany transactions are eliminated in consolidated statements
- Entity-level statements still show intercompany amounts
- Intercompany profits may be deferred (upstream/downstream sales)

**Tax:**
- Intercompany transactions must be at arm's-length prices
- Transfer pricing regulations apply to significant intercompany amounts
- Documentation required for tax authorities

## Best Practices

- **Standardise accounts** — use consistent intercompany account naming across entities
- **Set up config first** — configure account ranges before creating entries so elimination flags apply correctly
- **Reconcile monthly** — ensure intercompany balances across entities agree
- **Review net impact** — use the preview panel to verify the effect before posting
- **Document the purpose** — use the description field and attachments to record the business reason

## Related Articles

- [Multi-entity ledger management](/articles/05-general-ledger/5-6-multi-entity-ledger.md)
- [Creating manual journal entries](/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [FX revaluations](/articles/05-general-ledger/5-10-fx-revaluations.md)
