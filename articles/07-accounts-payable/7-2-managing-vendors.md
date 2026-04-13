# Adding and Managing Vendors

Vendor management in Light is the foundation of AP. This article covers creating vendors, configuring banking details, managing entity assignments, and tracking vendor status.

[Open in Light →](https://app.light.inc/vendors)

## Creating a Vendor

1. Navigate to **Spend management → Vendors**
2. Click **+ Create vendor**
3. Choose one of two creation modes:

---

### Option A — Customer Request

Send the vendor a portal link so they fill in their own information.

Required fields:
- **Vendor name**
- **Country**
- **Entity** (one or more)
- **Vendor email** (portal invitation is sent here)

Optional:
- **CC email** — copies an additional contact on the invitation

Once submitted, the vendor receives a link to complete their business and banking details directly in the Light vendor portal.

---

### Option B — Manual Entry

Fill in the vendor's information yourself via a 3-step form.

**Step 1 – Business**

| Field | Required |
|---|---|
| Name | ✅ |
| Country | ✅ |
| Website | — |
| Description | — |
| VAT number | — |
| Phone number | — |
| Address (street, city, state, ZIP) | — |
| Email | — |
| Custom properties | — |

**Step 2 – Payment**

Banking fields adapt based on the selected **bank country**:

| Bank country | Fields shown |
|---|---|
| United States | Routing number (9 digits) + Account number |
| United Kingdom | IBAN + Sort code + Account number |
| Sweden | IBAN + Clearing code + Account number + Bankgiro/Plusgiro |
| Denmark / Norway | IBAN + Clearing/bank code + Account number |
| Most EU countries | IBAN only |
| Australia | BSB code + Account number |
| Canada | Transit number + Account number |

Additional optional fields: BIC/SWIFT, bank name, bank address.

**Step 3 – Accounting**

| Field | Required |
|---|---|
| Entity assignment (one or more) | ✅ |
| Default entity | — |
| Default GL account | — |
| Default tax code | — |
| Default from account (payment bank account) | — |
| Cost center | — |
| Approvers | — |

Click **Create** to save.

---

## Vendor Statuses

| Status | Description |
|---|---|
| **Onboarding** | Vendor has been invited but hasn't completed their information yet |
| **In review** | Vendor's information has been submitted and is awaiting approval |
| **Active** | Vendor is approved and available to receive bills |
| **Rejected** | Vendor was reviewed and rejected |

The vendor list defaults to showing **Onboarding**, **In review**, and **Active** vendors.

---

## Banking Details and Change Requests

When bank details are updated — either by you or through a vendor portal submission — the change goes through an approval flow before taking effect.

While a change is pending you'll see two tabs on the vendor:
- **Awaiting approval** — shows the proposed new banking details
- **Current details** — shows the existing banking details still in use

---

## Entity Assignment

A vendor can be assigned to one or more company entities. For each default entity you can configure:

- **Default GL account** — pre-fills coding on bills from this vendor
- **Default tax code** — pre-fills tax on bills from this vendor
- **Default from account** — the company bank account used to pay this vendor
- **Cost center** — optional default cost center

---

## Approvers

Approvers can be assigned to a vendor in the **Accounting** step during creation, or edited later. Assigned approvers are required to sign off on bills or changes from that vendor based on your organization's approval workflow.

---

## Vendor Details Tabs

Once a vendor is created, opening it shows the following tabs:

| Tab | Visible when |
|---|---|
| **Accounting Documents** | Vendor status is **Active** |
| **Tasks** | Always |
| **Attachments** | Always |
| **Onboarding** | During onboarding flow |

---

## Downloading Account Statements

Generate and download statements showing your transaction history with a vendor.

1. Navigate to **Spend management → Vendors**
2. Select a vendor
3. Click **Download account statement**
4. Apply filters:
   - **Period**: Select a date range (optional — if specified, the period appears on the statement)
   - **Entity**: Filter by entity (optional)

5. Click **Download**

Statement behavior:
- **Single entity**: The entity name appears on the statement
- **Currency requirement**: All selected transactions must be in the same currency — if currencies differ, an error is shown

---

## Related Articles

- [AP overview](/articles/07-accounts-payable/7-1-ap-overview.md)
- [Vendor portal and magic links](/articles/07-accounts-payable/7-3-vendor-portal.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
