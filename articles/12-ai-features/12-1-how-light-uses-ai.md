# How Light Uses AI

Light integrates AI throughout the platform to automate financial workflows, reduce manual data entry, and provide intelligent insights. This article explains where AI is applied and what capabilities it enables across your financial operations.

[Open in Light →](https://app.light.inc/dashboard)

## AI Across Light

Light leverages advanced AI models (Google Gemini and OpenAI) through a unified GenAI framework that provides intelligent automation across multiple financial processes.

### Document Parsing and Data Extraction

When you upload invoices, bills, receipts, or other financial documents, Light's AI-powered parsing engine automatically extracts key financial data. The system uses optical character recognition (OCR) combined with large language models to read document content, even from images and PDFs. Extracted data includes vendor names, invoice amounts, dates, line items, account codes, and tax information.

This eliminates manual typing and reduces the risk of data entry errors. The AI learns from corrections you make, improving accuracy over time.

### Receipt Capture and Categorization

Mobile receipt uploads are processed by Light's AI engine to automatically capture spending details. The system extracts the vendor name, transaction amount, currency, purchase date, and line items. Light's AI then assigns appropriate expense categories and tax codes based on the merchant type and spending pattern.

### Invoice and Bill Processing

The AI parsing module uses GenAI function handlers to extract structured data from uploaded invoices. Beyond basic amounts and dates, the system can identify multiple line items within a single invoice, extract custom fields, and recognize payment terms. This is especially useful for processing bulk invoices from regular vendors.

### Data Cleaning and Validation

Light's AI cleans and validates financial data in real time. The system detects anomalies, flags potential errors, and suggests corrections. Examples include identifying duplicate entries, catching inconsistent vendor names, and flagging amounts that fall outside normal spending patterns for a user or department.

### Reconciliation Assistance

The bank reconciliation engine is powered partly by AI. Light suggests transaction matches based on amounts, dates, and reference patterns. The AI learns from your previous reconciliation decisions to improve future suggestions, making the reconciliation process faster over time.

### Natural Language Queries in Slack

Through Light's Slack integration, you can ask natural language questions about your finances using @Light. Ask questions like "What did we spend on travel last month?" or "Show me payables by vendor." Light processes your question using AI and returns relevant reports and data without requiring you to navigate the UI.

> Good to know: The Slack integration processes your questions using the same AI models that power other Light features, maintaining the same security and privacy standards across the platform.

## How Light Manages AI

Light uses a modular AI architecture:

- **GenAI Integration**: Provides a unified interface supporting multiple AI providers (Google Gemini, OpenAI, Groq)
- **AI Parsing Module**: Handles document parsing and data extraction with specialized handlers for different document types
- **AI Commons**: Manages AI configuration, prompts, threads, and conversation history
- **Provider Flexibility**: You can configure which AI models Light uses, depending on your privacy and performance preferences

The platform routes requests intelligently between providers based on capability requirements and your configuration settings.

## AI Privacy and Control

Light processes financial documents using AI in a secure manner:

- All documents are encrypted during transmission and storage
- AI processing respects your data isolation requirements
- You control which AI providers are enabled in your instance
- Processing is logged and auditable

The AI learns patterns from your data to provide better categorization and matching suggestions, but your financial data is never used to train public AI models.

## Where AI Saves You Time

To put it in practical terms, here are some common tasks where AI makes a measurable difference:

- **Bill processing**: A finance team processing 200 invoices per month can expect AI extraction to handle roughly 80-90% of data entry automatically, reducing manual work from hours to minutes of review.
- **Expense reports**: Employees submit a photo of a receipt and the AI fills in vendor, amount, category, and tax code — typically within seconds.
- **Month-end reconciliation**: AI-suggested matches can reduce reconciliation time significantly by surfacing high-confidence matches first, letting your team focus on the exceptions.
- **Ad hoc reporting**: Instead of navigating reports and applying filters, a quick Slack message to @Light gets you the answer in natural language.

> Tip: Start by letting AI handle the high-volume, repetitive tasks (receipt processing, invoice data entry) and then expand to reconciliation and reporting as your team gets comfortable with the suggestions.

## Related Articles

- [AI-Powered Data Cleaning and Accuracy](12-2-ai-data-cleaning.md)
- [AI Invoice Data Extraction](12-3-ai-invoice-extraction.md)
- [AI Receipt Capture and Categorization](12-4-ai-receipt-categorization.md)
- [Natural Language Q&A in Slack](12-5-ai-slack-qa.md)
- [AI-Assisted Reconciliation](12-6-ai-reconciliation.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
