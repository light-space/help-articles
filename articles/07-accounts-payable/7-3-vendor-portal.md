# Vendor Portal

The vendor portal lets vendors fill in their own business and banking information directly, instead of you typing it in for them. Vendors access the portal via a unique link sent by email.

## When the Portal Is Used

When you create a vendor via the **Customer Request** mode (see [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)), Light emails the vendor a portal link. The vendor opens the link in their browser and completes the form themselves — no Light account required.

The portal can also be reused to request updated banking information from an existing vendor.

## What Vendors Can Do in the Portal

The portal exposes three sections:

| Section | Contents |
|---|---|
| **Business Information** | Vendor name, country, address, VAT, website, description, contact details |
| **Payment Information** | Bank country and the country-specific banking fields (IBAN, routing number, account number, BIC/SWIFT, etc.) |
| **Attachments** | Supporting documents (e.g., bank statement, registration certificate) |

Vendors must complete **both** Business Information and Payment Information before they can submit.

## Portal Status Tracking

Each portal invitation moves through these statuses:

| Status | Meaning |
|---|---|
| **Sent** | Invitation email sent; vendor hasn't opened the link yet |
| **Opened** | Vendor has opened the portal |
| **Completed** | Vendor has submitted both required sections |

Each section (Business Information, Payment Information) also tracks completion individually inside the portal.

## After Submission

When the vendor submits, their details flow back to Light:
- The vendor record is populated with the submitted information
- Banking changes go through the standard banking-approval flow before becoming the vendor's active details (see [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md))

## Related Articles

- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [AP overview](/articles/07-accounts-payable/7-1-ap-overview.md)
