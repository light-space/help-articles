# AI Receipt Categorization

Light's AI automatically categorizes expenses and assigns them to GL accounts based on receipt content and merchant information. Suggestions are based on your company's reimbursement categories, and you can guide the AI by adding context to each category.

[Open in Light →](https://app.light.inc/expenses)

## How AI Categorization Works

When you submit a receipt, Light's AI:

1. **Analyzes Receipt Content**: Reads merchant name, line items, amounts, date, and location
2. **Identifies Merchant**: Extracts the merchant name and website domain, and enriches recognized merchants with a clean display name and logo
3. **Predicts Category**: Matches the expense to one of your company's reimbursement categories, using each category's context and your user context (country, user groups, cost center)
4. **Assigns GL Account and Tax Code**: The selected category determines the GL account (and tax code, if one is set on the category)
5. **Explains Its Work**: Records reasoning and the document location for each extracted value
6. **Leaves Uncertain Fields Blank**: If the AI can't confidently determine a value, it leaves the field empty for you to fill in

> Good to know: The AI only extracts information that is explicitly present on the receipt. If it can't confidently find a value, it leaves the field blank rather than guessing.

## Spending Categories

Expense categories in Light are your company's **reimbursement categories**, configured at **Settings (gear icon) → Reimbursement category**. Each category defines:

- **Label**: The category name shown to employees (e.g., "Travel", "Meals & Dining")
- **GL account**: Where expenses in this category post
- **Tax code** (optional): The tax code applied to expenses in this category
- **Context** (optional): A description that guides the AI when matching receipts to this category
- **Entities**: Which company entities the category applies to

In addition to the category, the AI assigns **spending tags** that describe the expense content — covering areas such as travel, meals, IT hardware, software subscriptions, training, and more. A single expense can have multiple tags when it spans categories.

Your company can create custom categories tailored to your business.

## AI Category Suggestions

### Review Suggested Category

After you upload a receipt, Light parses it and pre-fills a draft expense with the suggested category, along with the merchant, amount, date, and description.

Review the suggestion:

- **Looks right**: Submit the expense as-is
- **Wrong category**: Change to the correct category before submitting

### Overriding Suggestions

If Light categorizes incorrectly:

1. Open the draft expense and edit the category field
2. Browse or search available categories
3. Select the correct category
4. To improve future suggestions, add guidance to the category's **Context** field at **Settings (gear icon) → Reimbursement category**

## GL Account and Tax Code Mapping

Each reimbursement category maps to a single GL account and, optionally, a tax code. For example:

- Travel → 6100 Travel Expenses
- Meals → 6200 Meals & Entertainment

When you categorize an expense:

1. Light automatically assigns the GL account based on the category
2. GL account shows on the expense record
3. Finance team can see which account the expense will post to
4. You can override the GL account on the expense line if needed

## Merchant Recognition

Light's AI extracts the merchant name and website domain directly from the receipt. When a domain is found, Light enriches the merchant with a clean display name and logo.

If the merchant can't be determined from the receipt, the field is left blank and you can fill it in manually.

## Guiding the AI

Light's AI doesn't retrain itself on individual corrections. Instead, you steer it explicitly:

1. **Category context**: Describe what belongs in each category at **Settings (gear icon) → Reimbursement category**. The AI uses this context every time it matches a receipt to a category.
2. **Company AI instructions**: Company-level custom instructions for the AI assistant are applied whenever a receipt is parsed.
3. **User context**: The AI considers the submitter's country, user groups, and cost center when interpreting receipts and matching categories.

## Custom Categories

### Creating Custom Categories

For company-specific needs:

1. Navigate to **Settings (gear icon)** → **Reimbursement category**
2. Create a new category and enter:
   - **Label**: The category name (e.g., "Contractor Services")
   - **GL account**: Where expenses post
   - **Tax code** (optional): Tax code applied to expenses in this category
   - **Context** (optional): What's included — the AI uses this when categorizing
   - **Entities**: Which company entities the category applies to

3. The AI includes the new category the next time it parses a receipt

### Custom Category Examples

- **Software Subscriptions**: Monthly SaaS tools
- **Contractor Payments**: 1099 contractors and freelancers
- **Client Reimbursements**: Amounts to reimburse clients
- **Equipment Maintenance**: Repairs and service contracts

Add categories that match your business.

## When the AI Is Unsure

Light's AI must justify every value it extracts — each field includes its reasoning and where on the document the value was found. If the AI can't do that confidently, it leaves the field blank instead of guessing.

- **Field filled in**: The value was clearly present on the receipt — review and submit
- **Field left blank**: The AI couldn't confidently determine the value — you provide it manually

This applies to the category as well: if no category is a good match, none is suggested and you select one yourself.

## Policy Checks on Submission

When you submit an expense report, the **Expense submission** workflow runs an AI agent review against your company's policies (configured at **Settings (gear icon) → Guardrails → Policies**):

- **Compliant**: The expense report is approved automatically
- **Non-compliant**: The expense report is sent to the inbox for manual review

See [Expense policies and spending limits](/articles/08-expense-management/8-13-expense-policies.md) for how to configure policies.

## Categorization Analytics

Track categorization patterns:

1. Navigate to **Reports**
2. View:
   - **Total spending** by category
   - **Trend**: Is category increasing/decreasing
   - **Top merchants**: Who employees buy from most

3. Filter by:
   - Employee
   - Department
   - Time period
   - Category

Use to understand spending patterns and improve policies.

## Improving Accuracy

Tips for better AI categorization:

### Providing Clear Receipts

- **Good receipt photos**: Merchant name and items clear
- **Details visible**: Itemized breakdown (not just total)
- **Non-blurry**: Clear, legible text

Light extracts better information from clear receipts.

### Adding Category Context

1. Go to **Settings (gear icon)** → **Reimbursement category**
2. Add or refine the **Context** on each category:
   - "Client dinners and entertainment with external guests"
   - "Conference and training registrations"
   - "Software and SaaS subscriptions"

3. The AI uses this context on every receipt it parses
4. Categorization improves across the whole company

## Handling Edge Cases

Some expenses don't fit standard categories:

**Multi-Category Expenses**:
- Lunch with supplies shopping (Meals + Office Supplies)
- Light lets you split across line items
- Each line can have its own category and GL account

**One-Time Unusual Expenses**:
- Once-off payment not fitting standard categories
- Choose the closest category, or ask an admin to create a custom one

## Related Articles

- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [Expense policies and spending limits](/articles/08-expense-management/8-13-expense-policies.md)
- [Expense reports and analytics](/articles/08-expense-management/8-14-expense-reports.md)
