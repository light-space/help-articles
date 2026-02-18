# Help Articles Repository

This repository contains all help center articles for [Light](https://light.inc), an AI-native financial platform for multinational companies.

## Repository Structure

```
articles/
├── 01-getting-started/       (8 articles)
├── 02-organization-setup/    (9 articles)
├── 03-user-management/       (6 articles)
├── 04-bank-reconciliation/   (8 articles)
├── 05-general-ledger/        (12 articles)
├── 06-accounts-receivable/   (12 articles)
├── 07-accounts-payable/      (13 articles)
├── 08-expense-management/    (14 articles)
├── 09-revenue-compliance/    (9 articles)
├── 10-reporting/             (13 articles)
├── 11-integrations/          (16 articles)
├── 12-ai-features/           (7 articles)
├── 13-security/              (5 articles)
├── 14-troubleshooting/       (5 articles)
├── 15-employee/              (24 articles)
help-article-hierarchy.md     (master table of contents)
article-mapping.md            (mapping to existing help.light.inc articles)
```

## Article Format

Each article is a Markdown file following this format:
- H1 title
- Brief intro paragraph
- Deep link: `[Open in Light →](https://app.light.inc/relevant-path)`
- Content sections with H2 headings
- Related Articles section at the bottom

## Navigation Paths (Sidebar Labels)

When referencing how to navigate to a page in the Light app, always use the correct sidebar labels:

**Personal section:**
- Home → /dashboard
- Tasks → /user-tasks
- Expenses → /expenses
- Cards → /user-cards

**Revenue & Invoicing:**
- Sales invoices → /invoice-receivables
- Customer credits → /customer-credits
- Contracts → /contracts
- Products → /products
- Customers → /customers

**Spend management:**
- Bills → /payables
- Credit entries → /credit-entries
- Reimbursements → /reimbursements
- Cards → /cards
- Purchase orders → /procurement/purchase-orders
- Vendors → /vendors

**Accounting:**
- Releases → /releases
- Transactions → /ledger-transactions
- Journal entries → /journal-entries
- Accounting documents → /accounting-documents
- Bank reconciliation → /bank-reconciliation
- Chart of accounts → /accounting/ledger-accounts
- Accounting periods → /accounting/accounting-periods
- Tax codes → /accounting/ledger-tax-codes

**Planning & Reports:**
- Reports → /ledger-reports
- Budget → /budget

**Business partners:**
- Users → /users

**Settings:** Always reference as "Settings (gear icon)"

## Writing Style

- Professional but clear tone
- Use bold for UI element names (e.g., **Auto reconcile**, **+ Create sales invoice**)
- Use `→` for navigation paths (e.g., "Accounting → Journal entries")
- Button names always start with "+" when they are create buttons (e.g., "+ Create vendor")
- Include deep links as `[Page Name](https://app.light.inc/path)` when referencing other pages
- Status badges: Draft (orange), Open (green/yellow), Posted (green), Cleared (green), Void (red/pink)

## Workflow

Push updates directly to the `main` branch.

When making changes (e.g., triggered via a GitHub issue like `@claude update the article about GL accounts`):

1. Find the relevant article(s) based on the topic described
2. Make targeted edits — don't rewrite articles from scratch unless specifically asked
3. Ensure navigation paths, button names, and UI terminology stay consistent with the conventions above
4. If creating a new article, follow the numbering convention (section-number-slug.md) and add it to `help-article-hierarchy.md`
5. Commit and push directly to `main`

## Article Index

The file `help-article-hierarchy.md` in the repo root is the master table of contents with links to every article. Keep it up to date when adding or renaming articles.
