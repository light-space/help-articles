# Invoice Templates

Invoice templates control the appearance and content of invoices sent to customers. Light allows you to create custom branded templates for different customer types or business units.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Understanding Template Structure

Invoice templates define:

- **Header**: Company logo, name, and contact information
- **Color Scheme**: Brand colors and styling
- **Layout**: Where line items, totals, and notes appear
- **Static Content**: Company address, tax ID, bank details
- **Dynamic Content**: Customer info, invoice details, payment terms
- **Footer**: Terms and conditions, legal notices

## Creating a Template

1. Navigate to **Invoice Templates** in AR settings
2. Click **Create Template**
3. Enter a **Template Name** (e.g., "Standard B2B", "Government Agencies")
4. Choose a **Base Template** to start from (blank or copy existing)
5. Click **Create**

## Customizing Template Design

### Logo and Header

1. Open the template
2. Navigate to **Design**
3. Click **Upload Logo**
4. Select a company logo (PNG, JPG, up to 2MB)
5. Adjust the logo **Size** and **Position**
6. Enter the **Company Name** as it should appear
7. Click **Save**

> Good to know: Light automatically detects and removes backgrounds from logos to ensure they look clean on any invoice background.

### Colors and Styling

1. In the **Design** section, find **Color Settings**
2. Set your brand colors:
   - **Primary Color**: Accent color for headers and highlights
   - **Secondary Color**: Supporting color for backgrounds
   - **Text Color**: Primary text color
   - **Accent Color**: For key amounts and totals

3. Preview changes in real-time
4. Click **Save**

### Layout Configuration

1. Open the template
2. Navigate to **Layout**
3. Choose from layout presets or customize:
   - **Standard**: Traditional invoice layout
   - **Compact**: Condensed format for simple invoices
   - **Detailed**: Extended layout with more space for notes

4. Drag sections to reorder (if custom layout enabled)
5. Click **Save**

## Configuring Content Sections

### Header Section

Set what appears in the invoice header:

1. Navigate to **Content** > **Header**
2. Enable/disable:
   - Company name and logo
   - Invoice number
   - Invoice date
   - PO number (if applicable)

3. Customize the header text
4. Click **Save**

### Line Item Section

Control what displays for each product line:

1. Go to **Content** > **Line Items**
2. Choose which columns to display:
   - Description
   - SKU
   - Quantity
   - Unit Price
   - Discount
   - Tax
   - Line Total

3. Set column order and widths
4. Click **Save**

### Footer Section

Add terms, legal text, and instructions:

1. Navigate to **Content** > **Footer**
2. Add standard footer text such as:
   - Payment terms
   - Return policy
   - Legal disclaimers
   - Contact information

3. Optionally, include dynamic fields (e.g., {{CompanyPhone}}, {{DueDate}})
4. Click **Save**

## Payment Information Display

Configure how payment instructions appear:

1. Open the template
2. Navigate to **Payment Information**
3. Choose which payment methods to display:
   - Bank transfer details
   - Check mailing address
   - Credit card payment portal
   - ACH information

4. Set the display order
5. Click **Save**

Payment details are populated from the invoice's payment instructions when sent.

## Multi-Language Templates

Create templates for different customer languages:

1. Click **Create Template** and select **Language**
2. Choose the template language (English, Spanish, German, French, etc.)
3. Customize text content in that language
4. Assign the template to customer(s) with that language preference

Light automatically selects the correct template when generating invoices.

## Using Templates

Assign templates when creating invoices:

1. Open or create an invoice
2. Navigate to **Template**
3. Select from available templates
4. Preview the invoice in the selected template
5. Click **Use Template**

## Template Versioning

Templates maintain version history:

1. Open a template
2. Navigate to **Versions**
3. View all previous versions with creation dates
4. Click **Revert** to restore a previous version
5. Add a reason for the revert

Published templates are read-only; create a new version to make changes.

## Related Articles

- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Sending invoices and payment reminders](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
