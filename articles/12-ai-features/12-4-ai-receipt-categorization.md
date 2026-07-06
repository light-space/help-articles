# AI Receipt Capture and Categorization

Light's AI engine processes receipt uploads to automatically capture spending details and assign expense categories. This article explains how to capture receipts and how Light categorizes them.

[Open in Light →](https://app.light.inc/expenses)

## Overview

Light's mobile app and web interface make it easy to capture receipts on the go. Upload a photo or PDF, and Light's AI extracts the spending details, categorizes the expense, and prepares it for reimbursement or ledger recording.

## What Light Extracts from Receipts

When you upload a receipt, Light's AI parsing engine captures:

- **Vendor/Merchant Name**: Who you spent money with (e.g., Starbucks, United Airlines), plus the merchant's website domain when visible on the receipt
- **Transaction Amount**: The total gross amount paid (including taxes) and the original currency
- **Date**: When the purchase was made
- **Location**: The city and country of the purchase
- **Descriptions**: A detailed description of the receipt contents (including individual items when the receipt is itemized) and a concise summary of the expense purpose
- **Category and Spending Tags**: A suggested reimbursement category and spending tags describing the expense content

The AI only extracts information that is explicitly present on the receipt. If it can't confidently determine a value, it leaves the field blank for you to fill in. Light stores this information and links it to your user profile for easy tracking.

## Automatic Expense Categorization

Light's AI automatically suggests an expense category based on the receipt content. The categorization system:

- Matches the expense to one of your company's **reimbursement categories**, configured at **Settings (gear icon) → Reimbursement category**
- Uses each category's **Context** description and your user context (country, user groups, cost center) to pick the best match
- Analyzes the receipt contents to determine the true nature of the expense
- Applies the GL account (and tax code, if one is set) defined on the selected category

For example, if you upload a receipt from a restaurant and your company has a "Meals & Dining" category, Light suggests that category. If no category is a good match, none is suggested and you select one yourself.

> Good to know: Light extracts the merchant name and website domain directly from the receipt. When a domain is found, Light enriches the merchant with a clean display name and logo — so recognition works whether you're spending locally or while traveling.

## How to Upload Receipts

### Mobile App

1. Open the Light mobile app
2. Tap the **Camera** or **Upload** icon
3. Take a photo of the receipt or select one from your phone's photos
4. Light processes the receipt automatically
5. Review the extracted data
6. Click **Save** to record the expense

### Web Interface

1. Navigate to the **Expenses** page
2. Click **Upload Receipt**
3. Select a receipt image or PDF from your computer
4. Light processes and displays the extracted data
5. Review the information
6. Click **Confirm** to save

## Reviewing and Correcting Categorization

After Light extracts the receipt data:

1. Review the captured amount, date, and vendor name
2. Check the assigned expense category
3. If the category is incorrect, click to change it
4. Select the appropriate category from the list or search for it
5. Click **Save**

Light doesn't retrain itself on individual corrections. To improve future suggestions for similar expenses, add guidance to the category's **Context** field at **Settings (gear icon) → Reimbursement category** — the AI uses this context every time it parses a receipt.

## Receipt Quality Tips

To ensure Light accurately captures receipt data:

- Take clear, well-lit photos of receipts
- Ensure the entire receipt is visible in the frame
- Avoid glare or shadows on the receipt
- Hold the camera steady to minimize blur
- Include the top, middle, and bottom of the receipt

Receipts with blurry text, extreme angles, or poor lighting may require manual entry.

## Tax Code Assignment

Tax codes come from your company's reimbursement categories. Each category, configured at **Settings (gear icon) → Reimbursement category**, maps to a GL account and, optionally, a tax code.

When Light assigns a category to your receipt, the tax code set on that category is applied to the expense. This helps ensure accurate tax reporting and expense deductions.

## Guiding the AI

Light's AI parses each receipt independently — it doesn't remember previous receipts or build vendor-specific rules. Instead, you steer it explicitly:

- **Category context**: Describe what belongs in each category at **Settings (gear icon) → Reimbursement category**
- **Company AI instructions**: Company-level custom instructions for the AI assistant are applied whenever a receipt is parsed
- **User context**: The AI considers the submitter's country, user groups, and cost center when interpreting receipts and matching categories

> Tip: Batch upload receipts from a trip or week. Light processes each one automatically, making expense review easier.

## Related Articles

- How Light uses AI
- AI-powered data cleaning
- AI invoice data extraction
