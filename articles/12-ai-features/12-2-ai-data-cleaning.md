# AI-Powered Data Cleaning

Light's AI engine continuously cleans, validates, and improves the quality of your financial data. This article explains how AI identifies errors and suggests corrections to keep your records accurate.

[Open in Light →](https://app.light.inc/dashboard)

## How AI Data Cleaning Works

As data enters Light through various sources—manual entry, imports, bank feeds, or document uploads—the AI validation layer processes it to detect quality issues. The system uses pattern recognition and business rules to identify anomalies that might indicate errors.

### Error Detection

Light's AI automatically detects common data quality issues:

- **Duplicate entries**: The system recognizes when the same transaction or vendor appears multiple times with slight variations (e.g., "Acme Inc" vs "Acme Inc.")
- **Format inconsistencies**: Catches mismatched currency formats, date inconsistencies, or malformed reference numbers
- **Outlier amounts**: Flags transactions that deviate significantly from typical spending patterns
- **Incomplete records**: Identifies missing required fields like vendor names, amounts, or account codes
- **Invalid vendor data**: Detects vendor names that don't match known merchants or databases

### Correction Suggestions

When AI detects a potential error, it presents you with suggested corrections. For example:

- For duplicate vendor entries, Light suggests merging related records
- For formatting issues, Light proposes the corrected format
- For categorization mismatches, Light suggests the appropriate expense category
- For missing data, Light may auto-populate based on similar historical records

> Tip: You can review and approve AI suggestions before they're applied. This gives you control while still benefiting from automation.

## Data Validation Rules

Light's AI operates within a set of business validation rules:

- Amounts must fall within reasonable ranges for transaction types
- Currency codes must be valid and match the company's operational currencies
- Dates must be logical (transaction dates cannot be in the future)
- Vendor names must follow consistent formatting
- Account codes must exist in your chart of accounts

If data violates these rules, AI flags it for review with a clear explanation of the issue.

## Continuous Improvement

The AI learns from corrections you make. When you reject a suggestion or manually fix an error, Light uses that feedback to improve future validation. Over time, the system becomes more accurate at detecting issues specific to your company's data patterns and terminology.

## Manual Override

You maintain full control over your data. You can:

- Accept all AI suggestions
- Selectively approve or reject individual suggestions
- Manually enter corrections without following AI suggestions
- Disable specific types of validation if they don't apply to your workflows

## Related Articles

- How Light uses AI
- AI invoice data extraction
- AI receipt capture and categorization
