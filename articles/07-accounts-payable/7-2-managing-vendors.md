# Adding and Managing Vendors

Vendor management in Light is the foundation of AP. This article covers creating vendors, updating vendor information, and managing vendor hierarchies and approvers.

[Open in Light →](https://app.light.inc/vendors)

## Creating a Vendor

1. Navigate to **Spend management → Vendors**
2. Click **+ Create vendor**
3. Enter required information:
   - **Vendor Name**: Company or individual name
   - **Email**: Primary contact email
   - **Vendor Status**: Active or Inactive

4. Add optional details:
   - **Description**: Notes about the vendor
   - **Website**: Vendor's website URL
   - **Phone Number**: Contact phone
   - **Country**: Vendor location
   - **Address**: Street, city, state, postal code

5. Click **Create**

## Vendor Tax Information

Configure tax details for correct bill treatment:

1. Open the vendor
2. Navigate to **Tax Information**
3. Enter:
   - **VAT Number**: EU VAT ID (if applicable)
   - **Business Registration Number**: Company registration ID
   - **Tax Classification**: If available (affects 1099 reporting)

4. Optionally, mark vendor for **1099 reporting** (US contractors only)
5. Click **Save**

> Good to know: Accurate tax information ensures correct GL coding and tax reporting compliance.

## Banking Information

Add vendor banking details for payments:

1. Open the vendor
2. Navigate to **Banking Details**
3. Choose **Bank Account Type**:
   - **Domestic Account**: Local bank account (account number/routing)
   - **International Account**: IBAN/SWIFT for cross-border payments
   - **ACH Account**: US ACH payments
   - **Check**: Mailing address for check payments

4. For bank accounts, enter:
   - **Bank Name** and **Country**
   - **Account Number** (or IBAN)
   - **Bank Code** (or BIC/SWIFT)
   - Optionally, **Secondary Account** (if vendor has multiple)

5. For checks, enter **Mailing Address**
6. Click **Save**

## Payment Preferences

Configure how this vendor prefers to be paid:

1. Open the vendor
2. Navigate to **Payment Preferences**
3. Set:
   - **Preferred Payment Method** (bank transfer, check, ACH, virtual card)
   - **Payment Terms** (Net 30, Net 60, etc.)
   - **Currency**: Default payment currency
   - **Minimum Payment Amount**: Only pay if amount exceeds threshold
   - **Scheduled Payment Days**: Best days to pay (e.g., "Mid-month")

4. Click **Save**

Light uses these preferences when scheduling payments.

## Vendor Contacts

Manage multiple contact people at the vendor:

1. Open the vendor
2. Navigate to **Contacts**
3. Click **Add Contact**
4. Enter:
   - **Contact Name**
   - **Email Address**
   - **Phone Number** (optional)
   - **Role**: (e.g., Accounts Payable, Sales, Support)
   - **Primary Contact**: Toggle if this is the main contact

5. Click **Save**

When sending bills or payment reminders, Light uses the primary contact by default.

## Entity Assignment

Assign vendors to specific company entities:

1. Open the vendor
2. Navigate to **Entity Assignment**
3. Click **Assign to Entity**
4. Select one or more entities
5. Optionally, set **Entity-Specific Details**:
   - Different default GL account per entity
   - Entity-specific payment terms
   - Entity-specific contact

6. Click **Assign**

If a vendor is assigned to multiple entities, you'll see their bills grouped by entity.

## Vendor Approval Hierarchy

Configure who must approve bills from this vendor:

1. Open the vendor
2. Navigate to **Approval Settings**
3. Click **Add Approver**
4. Select the **User** or **Role**
5. Set the **Approval Level** (1, 2, 3, etc.)
6. Set **Approval Limit**: Bills up to this amount don't require approval; above require this user
7. Click **Add**

Repeat for each approval level.

Example:
- Level 1: Manager (approves bills under $5,000)
- Level 2: Finance Lead (approves $5,000-$50,000)
- Level 3: CFO (approves over $50,000)

## Spending Limits

Set maximum spending authority per vendor:

1. Open the vendor
2. Navigate to **Spending Limits**
3. Set:
   - **Annual Spending Limit**: Max total spending per year
   - **Monthly Spending Limit**: Max per month
   - **Single Transaction Limit**: Max per single bill
   - **Rolling Limit**: 30-day or other period

4. Optionally, set **Notification Threshold** (alert at 80% of limit)
5. Click **Save**

Light prevents bill posting if limits are exceeded.

## Vendor Status and Archiving

Manage vendor lifecycle:

**Vendor Statuses:**
- **ACTIVE**: Can receive bills and make payments
- **INACTIVE**: Cannot receive new bills; historical bills remain
- **PENDING**: Awaiting approval before becoming active

To archive a vendor:

1. Open the vendor
2. Click **Archive**
3. Optionally, set **Archive Reason** (moved, merged, etc.)
4. Archived vendors:
   - No longer appear in active vendor lists
   - Remain accessible for historical billing
   - Can be reactivated by clicking **Activate**

## Custom Properties

Add vendor-specific custom fields:

1. Open the vendor
2. Navigate to **Custom Properties**
3. Click **Add Property**
4. Select property group and label
5. Enter value
6. Click **Save**

Use custom properties for procurement coding, department tracking, or vendor classification.

## Bulk Vendor Operations

Manage many vendors at once:

1. Navigate to **Vendors**
2. Click **Bulk Actions**
3. Select vendors using checkboxes
4. Choose action:
   - **Update Entity Assignment**: Add/remove entities
   - **Update Payment Method**: Change preferred method
   - **Archive**: Deactivate multiple vendors
   - **Update Custom Properties**: Bulk update a field

5. Review changes and confirm

## Related Articles

- [AP overview](/articles/07-accounts-payable/7-1-ap-overview.md)
- [Vendor portal and magic links](/articles/07-accounts-payable/7-3-vendor-portal.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
