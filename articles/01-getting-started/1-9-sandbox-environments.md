# Sandbox environments

A sandbox is a completely separate, isolated copy of the Light application where you can safely test features, run demos, or experiment with settings — without affecting your production data.

[Open in Light →](https://app.light.inc/settings/sandboxes)

## What is a sandbox?

Think of a sandbox like a practice mode: everything looks and works like the real thing, but nothing you do there touches your live environment. Each sandbox gets its own company, its own users, and its own data.

You can create multiple sandboxes from one production account — for example, one per prospect, partner, or testing scenario.

## Creating a sandbox

### Step 1: Request a sandbox

From your production Light account, navigate to **Settings (gear icon) → Sandboxes** and click **+ Create sandbox**. Fill in the details:

- **Company information** — company and entity name, address, city, zip code, country, VAT number, website, and description
- **Users** — the people who should have access, with their name and email
- **Personal message** (optional) — a custom note included in the invite email

### Step 2: The sandbox gets provisioned

Behind the scenes, Light creates a brand-new company in the sandbox environment:

- A new company is set up with the name you provided
- Email addresses for invoices, receipts, and contracts are automatically generated (e.g., `your-company-<unique-id>@invoices.sandbox.light.inc`)
- A company entity is created with the address and VAT number you entered
- The base currency is automatically chosen based on the country (e.g., USD for US, GBP for UK, DKK for Denmark, EUR for EU)
- All listed users are created as admins in the sandbox company

### Step 3: Users get invited

Once the sandbox is ready, each user receives an invite email with:

- The name of the person who set up the sandbox
- The company name and any personal message
- A link to log in at `https://app.sandbox.light.inc`

## Sandbox statuses

| Status | What it means |
| --- | --- |
| Pending | The sandbox is being set up. Usually takes just a few seconds. |
| Active | Ready to use. Users can log in and start working. |
| Failed | Something went wrong during setup. The error is logged for the team to investigate. |
| Deactivated | The sandbox has been shut down. It can no longer be accessed. |

## Managing sandboxes

### Updating a sandbox

You can update an existing sandbox at any time:

- Change the company name, address, or other details
- Add new users — they'll be created in the sandbox automatically
- Remove users — anyone not in the updated list will be deactivated
- Update existing users' information (matched by email address)

### Resetting a sandbox

An active sandbox can be reset at any time — wiping its data back to a clean state or re-seeding it with the standard demo dataset. Resetting only affects the sandbox; production is never touched.

### Deactivating a sandbox

When you no longer need a sandbox, you can deactivate it. This archives the sandbox company so it can no longer be accessed. This action does not affect your production environment in any way.

### Viewing your sandboxes

You can see all sandbox environments your company has created, along with their status, creation date, who created them, and the company details.

## Frequently asked questions

### Does the sandbox automatically pull through all data from production?

**Not automatically.** The sandbox never syncs with production on an ongoing basis. What the sandbox contains depends on the option chosen when it is created:

- **Empty (default)** — a brand-new company with a blank slate: no customers or vendors, no bank accounts, no pre-populated chart of accounts, and no invoices, bills, transactions, or historical data
- **Demo data** — the sandbox is seeded with a standard demo dataset so it feels like a working company from day one
- **A copy of your own production data** — the sandbox is loaded with data from your own production company, either the full history or only a recent window of posted transactional data. A sandbox can only be seeded with your own company's data — never another company's

In every case this is a one-time load at creation: afterwards, no data flows between production and the sandbox. If you need additional test data, it must be entered or imported manually within the sandbox environment.

### Do users need to be created separately in sandbox, or do production users automatically have access?

**Users must be created separately.** Production users do not automatically have access to the sandbox.

Here's how it works:

- When you create a sandbox, you provide a list of users (name and email) as part of the setup
- These users are created as new accounts in the sandbox environment — they are completely independent from your production users
- Each user receives an invite email with a link to log in at the sandbox URL (`app.sandbox.light.inc`)
- Sandbox users have their own login credentials, separate from production
- All sandbox users are created as Company Admins by default

To add more users later, you can update the sandbox and include the new users in the list. To remove users, simply leave them out of the updated list — they will be deactivated.

In short: the person creating the sandbox decides exactly who gets access. There is no automatic bridge between production user accounts and sandbox user accounts.

### Can customers use sandbox for testing while we wipe and reload production with historical data?

**Yes.** The sandbox environment is completely independent from production. They run on entirely separate infrastructure:

- **Separate databases** — sandbox and production have their own databases in different AWS accounts
- **Separate storage** — files, documents, and attachments are stored in separate S3 buckets
- **Separate message queues** — all background processing runs independently
- **No shared state** — there is zero overlap between sandbox and production data

This means:

- Wiping or reloading production data has no impact on sandbox environments
- Sandbox users can continue working normally during any production maintenance
- Conversely, anything done in sandbox (creating test invoices, deleting test vendors, etc.) has no impact on production

The only connection between the two is a small tracking record in production that remembers which sandboxes were created and their current status. This is purely bookkeeping — no actual sandbox data flows back to production.

## Security

Sandbox environments are secured at multiple levels:

- **Access control** — only Company Admins in production (or Light staff) can create, update, reset, or deactivate sandboxes
- **Signed communication** — all requests between production and the sandbox environment are cryptographically signed to prevent unauthorized access
- **Isolation** — the sandbox runs in its own AWS account with its own infrastructure. There is no way for sandbox data to leak into production or vice versa
- **Data seeding limits** — a sandbox can only be seeded with data from its own production company; cross-company seeding is not permitted

## Quick reference

| Question | Answer |
| --- | --- |
| Does sandbox copy production data? | Not by default — starts empty, with optional demo data or a one-time copy of your own production data |
| Are production users automatically in sandbox? | No — users are created fresh |
| Can I use sandbox during production maintenance? | Yes — fully independent |
| How many sandboxes can I create? | No hard limit — create as many as needed |
| What currency does the sandbox use? | Based on the country you choose (US = USD, UK = GBP, etc.) |
| How do sandbox users log in? | Via invite email link to `app.sandbox.light.inc` |
| Can I add/remove users after creation? | Yes — update the sandbox with the new user list |
| Does deactivating a sandbox affect production? | No — production is never affected |

## Related articles

- [Go-live readiness and minimum viable setup](1-8-go-live-readiness.md)
- [Quick-start checklist for new customers](1-7-quick-start-checklist.md)
- [Data import and migration tools](../11-integrations/11-13-data-import.md)
- [Cutover fundamentals and execution steps](../11-integrations/11-16-cutover.md)
