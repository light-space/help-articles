# How Light Uses AI

Light integrates AI throughout the platform to automate financial workflows, reduce manual data entry, and provide intelligent insights. This article explains where AI is applied and what capabilities it enables across your financial operations.

[Open in Light →](https://app.light.inc/dashboard)

## AI Across Light

Light leverages a combination of its own proprietary fine-tuned models and advanced third-party foundation models (OpenAI GPT, Google Gemini, and Anthropic Claude via AWS Bedrock) through a unified GenAI framework that provides intelligent automation across multiple financial processes.

### Document Parsing and Data Extraction

When you upload invoices, bills, receipts, or other financial documents, Light's AI-powered parsing engine automatically extracts key financial data. The system uses optical character recognition (OCR) combined with large language models to read document content, even from images and PDFs. Extracted data includes vendor names, invoice amounts, dates, line items, account codes, and tax information.

This eliminates manual typing and reduces the risk of data entry errors. All extracted values remain fully editable, so you can review and correct them before anything is posted.

### Receipt Capture and Categorization

Mobile receipt uploads are processed by Light's AI engine to automatically capture spending details. The system extracts the vendor name, transaction amount, currency, purchase date, and line items. Light's AI then assigns appropriate expense categories and tax codes based on the merchant type and spending pattern.

### Invoice and Bill Processing

The AI parsing module uses GenAI function handlers to extract structured data from uploaded invoices. Beyond basic amounts and dates, the system can identify multiple line items within a single invoice, extract custom fields, and recognize payment terms. This is especially useful for processing bulk invoices from regular vendors.

### Data Cleaning and Validation

Light validates and enriches financial data as it enters the system. Uploaded documents that are not valid bills are detected by AI before they enter your payables workflow, and duplicate bills are automatically flagged based on vendor and document number. AI is also used to enrich vendor and bank details from parsed documents.

### Reconciliation Assistance

The bank reconciliation engine is powered partly by AI. Light's AI parses bank transaction descriptions into structured metadata (such as invoice references and counterparty details), and matching rules then use that metadata — together with amounts, dates, and references — to suggest matches. You can also create reconciliation automation rules by describing them in plain language, and AI converts your description into structured rule conditions.

### Natural Language Queries in Slack

Through Light's Slack integration, you can ask natural language questions about your finances using @Light. Ask questions like "What did we spend on travel last month?" or "Show me payables by vendor." Light processes your question using AI and returns relevant reports and data without requiring you to navigate the UI.

> Good to know: The Slack integration processes your questions using the same AI models that power other Light features, maintaining the same security and privacy standards across the platform.

## How Light Manages AI

Light uses a modular AI architecture:

- **GenAI Integration**: Provides a unified interface supporting Light's proprietary models alongside multiple third-party AI providers (OpenAI, Google, and AWS Bedrock)
- **AI Parsing Module**: Handles document parsing and data extraction with specialized handlers for different document types
- **AI Commons**: Manages AI configuration, prompts, threads, and conversation history
- **Per-feature model selection**: Light selects the model for each feature independently — proprietary or third-party — so every use case runs on the model best suited to it

The platform routes each request to the model configured by Light for that specific use case, whether that is one of Light's proprietary models or a third-party foundation model.

## AI Privacy and Control

Light processes financial documents using AI in a secure manner:

- All documents are encrypted during transmission and storage
- AI processing respects your data isolation requirements
- Light manages which AI providers and models are used for each feature
- Processing is logged and auditable

Light's AI features run on a combination of models. Light uses data to fine-tune its own **proprietary models and LLMs**, improving the accuracy of AI-assisted features over time — these fine-tuned models are owned and operated by Light. For some features, Light additionally uses foundation models provided by third-party services (OpenAI, Google, and Anthropic via AWS Bedrock), which remain the property of those providers. Light owns its fine-tuned models along with the application-level logic, integrations, orchestration, and product features built around the platform.

Customer data is **never** used by third parties for model training or fine-tuning. Data sent to third-party AI providers is used only for runtime inference to deliver AI-assisted features — those providers do not train or fine-tune their models on your data.

### Data used in AI processing

Runtime AI processing may use customer-provided data such as:

- Bills, invoices, and receipts
- Contracts and company policies
- Vendor and customer master data
- Company entity details
- User-entered prompts or workflow context

This data is used to deliver AI-assisted product features such as parsing, prefilling, and summarization, and to fine-tune Light's proprietary models. It is never used by third parties for training or fine-tuning.

## AI Governance and Human Oversight

Light uses AI in a **supporting, non-decision-making** capacity. AI outputs are advisory only and do not produce legally or financially binding outcomes without human review. All AI-generated suggestions — from extracted invoice fields to reconciliation matches — are subject to human review and override before they take effect.

Light has assessed its AI functionality as **Limited Risk** under the EU AI Act. Light's use cases are assistive and non-high-risk, emphasizing transparency, human oversight, security, and accountability.

### Alignment with OECD AI Principles

Light's approach to AI aligns with the [OECD AI Principles](https://oecd.ai/en/ai-principles), emphasizing:

- **Human oversight** — all AI outputs are subject to human review and approval
- **Transparency** — AI-assisted features are clearly identified and explainable
- **Security and robustness** — AI processing follows the same encryption and data isolation standards as the rest of the platform
- **Accountability** — AI usage is logged and auditable
- **Fairness** — AI is used in limited-risk, assistive use cases that do not produce automated decisions

## Where AI Saves You Time

To put it in practical terms, here are some common tasks where AI makes a measurable difference:

- **Bill processing**: A finance team processing 200 invoices per month can expect AI extraction to handle roughly 80-90% of data entry automatically, reducing manual work from hours to minutes of review.
- **Expense reports**: Employees submit a photo of a receipt and the AI fills in vendor, amount, category, and tax code — typically within seconds.
- **Month-end reconciliation**: Automated matching can reduce reconciliation time significantly by handling transactions that meet your matching rules, letting your team focus on the exceptions.
- **Ad hoc reporting**: Instead of navigating reports and applying filters, a quick Slack message to @Light gets you the answer in natural language.

> Tip: Start by letting AI handle the high-volume, repetitive tasks (receipt processing, invoice data entry) and then expand to reconciliation and reporting as your team gets comfortable with the suggestions.

## Related Articles

- [AI-Powered Data Cleaning and Accuracy](12-2-ai-data-cleaning.md)
- [AI Invoice Data Extraction](12-3-ai-invoice-extraction.md)
- [AI Receipt Capture and Categorization](12-4-ai-receipt-categorization.md)
- [Natural Language Q&A in Slack](12-5-ai-slack-qa.md)
- [AI-Assisted Reconciliation](12-6-ai-reconciliation.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
