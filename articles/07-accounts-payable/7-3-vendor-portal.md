# Vendor Portal and Magic Links

Light's vendor portal allows vendors to submit invoices directly, reducing manual data entry and improving invoice accuracy. Magic links simplify access without requiring vendor account creation.

[Open in Light →](https://app.light.inc/vendors)

## Understanding the Vendor Portal

The vendor portal is a secure, vendor-facing interface where suppliers can:

- Submit invoices directly (PDF, image, or manual entry)
- View invoice status and payment information
- Check payment history
- Update banking and contact information
- Access automatic payment reminders

Portal access is controlled via magic links (one-time or reusable tokens) rather than usernames/passwords.

## Magic Links Overview

Magic links are authentication tokens that allow vendor access without account creation:

- **One-time links**: Single-use, expire after first use
- **Reusable links**: Multiple uses, expire after set period (30, 60, 90 days)
- **Permanent links**: Never expire but can be revoked at any time

Use one-time links for one-off payments; use reusable for ongoing vendors.

## Creating a Magic Link for a Vendor

### One-Time Link (Single Use)

1. Open the vendor
2. Navigate to **Portal Access**
3. Click **Create Magic Link**
4. Select **Link Type**: One-Time
5. Click **Create**
6. Copy the generated link
7. Email to vendor with portal instructions
8. Link is valid for 48 hours or until used

### Reusable Link

1. Open the vendor
2. Navigate to **Portal Access**
3. Click **Create Magic Link**
4. Select **Link Type**: Reusable
5. Set **Expiration Period**: 30, 60, 90 days, or custom
6. Click **Create**
7. Copy the link
8. Email to vendor with instructions

Vendor can use this link unlimited times until expiration.

> Good to know: Vendors can bookmark a reusable link in their browser for convenience. They don't need to receive a new link each time.

## Sending Portal Invitations

Automatically send portal invitations to vendors:

1. Navigate to **Vendors**
2. Select vendors to invite (using checkboxes)
3. Click **Bulk Actions** > **Send Portal Invite**
4. Choose **Link Type** (one-time or reusable)
5. Customize the **invitation email** (optional)
6. Set **expiration** for reusable links
7. Click **Send**

Light generates unique magic links for each vendor and emails with portal instructions.

## Vendor Portal Features

### Invoice Submission

Vendors submit invoices through multiple methods:

**Upload PDF or Image:**
1. Click **Submit Invoice**
2. Choose **Upload File**
3. Select PDF, image file (JPG, PNG)
4. Light's AI automatically extracts invoice data
5. Review and correct extracted information
6. Click **Submit**

**Manual Entry:**
1. Click **Submit Invoice**
2. Choose **Manual Entry**
3. Enter invoice details:
   - Invoice number and date
   - Amount and currency
   - Description
   - Line items (optional)

4. Click **Submit**

**Email Submission:**
1. Vendor sends invoice to portal email address
2. Portal automatically captures and extracts data
3. Vendor receives confirmation email with link to review

### Invoice Status Tracking

Vendors can track submitted invoices:

1. In portal, click **My Invoices**
2. View all submitted invoices with status:
   - **Received**: Invoice submitted, awaiting entry
   - **In Approval**: Bill created and being approved
   - **Approved**: Ready to pay
   - **Paid**: Payment sent
   - **Archived**: Historical invoice

3. Click an invoice to see timeline of actions

### Payment Information

Vendors can view payment details:

1. Click **Payment History**
2. View all payments received:
   - Payment date and amount
   - Payment reference number
   - Payment method
   - Currency

3. Optionally, download **payment statements** for their records

## Configuring Portal Settings

### Portal Branding

Customize the portal appearance:

1. Navigate to **Settings** > **Vendor Portal**
2. Upload **Company Logo** (optional)
3. Customize **Portal Name** (e.g., "Light Vendor Portal")
4. Set **Color Scheme**: Primary and secondary colors
5. Add **Welcome Message**: Introduction text
6. Click **Save**

Portal displays your branding, not Light's.

### Portal Permissions

Control what vendors can do:

1. Open vendor settings
2. Navigate to **Portal Permissions**
3. Enable/disable:
   - **Submit Invoices**: Allow invoice submission
   - **View Invoices**: Allow viewing submitted invoices
   - **View Payments**: Allow viewing payment history
   - **Update Banking**: Allow vendors to change banking details
   - **Download Statements**: Allow statement downloads

4. Click **Save**

Different vendors can have different permissions.

## Two-Factor Authentication

Enable additional security for portal access:

1. Navigate to **Settings** > **Portal Security**
2. Enable **Two-Factor Authentication**
3. Choose method:
   - **Email**: OTP sent to vendor email
   - **SMS**: OTP sent to vendor phone (if available)

4. Set **OTP Validity**: How long code is valid (5-15 minutes)
5. Click **Save**

Vendors receive second authentication code when accessing portal with magic link.

## Revoking Portal Access

Remove or expire a vendor's portal access:

1. Open the vendor
2. Navigate to **Portal Access**
3. Find the magic link
4. Click **Revoke Link**
5. Link is immediately disabled
6. Vendor can no longer access portal

Use this when:
- Vendor relationship ends
- Reusable link has expired
- Security concern

## Portal Analytics

Monitor vendor portal adoption:

1. Navigate to **Reports** > **Vendor Portal Usage**
2. View metrics:
   - **Active Vendors**: Using portal monthly
   - **Invoices Submitted**: Via portal vs. other methods
   - **Time to Invoice**: Days from submission to payment
   - **Data Quality**: AI extraction accuracy by vendor

3. Filter by vendor or time period
4. Export usage data for reporting

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [AI-driven invoice data extraction](/articles/07-accounts-payable/7-5-ai-invoice-extraction.md)
