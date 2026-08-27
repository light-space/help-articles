# US Sales Tax Integration (AvaTax & Sphere)

> **What is this page about:** How Light calculates US sales tax through AvaTax (Avalara) or Sphere, depending on which provider your entity is set up with, what each provider does, what Light sends it, how to get set up, and where to look when the tax looks wrong.

Light calculates US sales tax through one of two providers, AvaTax (Avalara) or Sphere, depending on which one your entity is set up with. This article covers what each provider does, what Light sends it, how to get set up, and where to look when the tax looks wrong.

[Open in Light →](https://app.light.inc/settings/integrations)

## On this page

- Which tax engine your invoices use
- What works the same on every engine
- AvaTax (Avalara)
- Sphere
- AvaTax and Sphere side by side

---

# 1. Which tax engine your invoices use

Every AR document in Light is calculated by exactly one tax engine. Light picks it for you when the document is created, based on the entity and the customer:

1. **AvaTax**, if the entity is activated for AvaTax and the customer's tax address is in the United States.
2. **Sphere**, if the entity is activated for Sphere. There's no country condition here, so a Sphere entity calculates tax for customers anywhere.
3. **Light**, our own tax engine, used when neither of the above applies.

If an entity somehow ends up activated for both providers, AvaTax wins for US customers.

> 💡 **Good to know:** if an entity hasn't been activated yet, its documents quietly fall back to Light's own tax engine. You won't see an error. You'll see tax calculated by a different engine than you expected. So check which engine the document is using before you start digging into the amount.

# 2. What works the same on every engine

This section applies whichever provider you're on. The provider sections below only add to it or contradict it. They don't repeat it.

## The GL account your tax posts to

Neither provider knows anything about your chart of accounts. They just return a tax amount. So Light needs you to tell it which ledger account that tax should land in. You choose the account per company entity, and Light links it during setup.

1. Decide which GL account should hold collected sales tax for the entity. Usually a sales tax liability account.
2. Give that account to Light during setup. We link it as the entity's **default sales tax account**.
3. From then on, every tax line Light posts for an AvaTax or Sphere document goes to that account.

> ⚠️ **If this account isn't set, your documents won't post.** You'll get: *"Default SALES tax account is not configured for this entity. Please contact your system administrator to set it up."* This is the most common thing that trips up a newly activated entity, so check the account is linked before you raise the first invoice.

Worth knowing how this differs from Light's own tax engine. There, each Light tax code carries its own posting rules, so tax can land in different accounts depending on the code. AvaTax and Sphere documents don't carry a Light tax code at all, so there's one default account per entity instead.

## Customer address

Both providers work from the customer's address. Light uses the **shipping address**, and falls back to the **billing address** if there isn't one. Neither provider can return sensible tax without it.

AvaTax also gets your own entity address as the ship-from location, because US sourcing rules depend on where the sale originates. Keep your entity address up to date.

## When tax recalculates

Light calls the provider again whenever something tax-relevant changes on the document: the line amount, quantity, product, tax code, the customer, the company entity, or the tax-inclusive setting. Editing a description or a cost centre won't trigger anything.

## How a document's tax engine is set

The tax engine isn't something you switch in the UI. Light fixes it when the document is created, based on the entity and customer (see section 1). If the engine is AvaTax or Sphere, each line's tax-code field renders as read-only, since AvaTax and Sphere already carry their own codes. If the engine is Light, the tax-code field on each line stays editable and only accepts Light's own tax codes.

## Draft, post and archive

While a document is in draft, Light asks the provider for tax and shows it to you. Posting is what makes it permanent in Light: the tax line gets written to your ledger against the default sales tax account. What each provider records at that point is different, so see the provider sections.

## Reporting

Posted invoices, customer credits and their ledger entries stay available in Light whichever provider you use. Go to **Planning & Reports → Reports** to report on revenue and tax accounts in your ledger.

---

# 3. AvaTax (Avalara)

## Setting up AvaTax

AvaTax runs against **your own Avalara account**. Light connects to it using credentials you give us.

1. Set up your Avalara account and AvaTax subscription with Avalara.
2. In Avalara, generate an **account ID** and a **license key**.
3. Send both to your Light contact through an agreed secure channel. We store them against your company and use them for every AvaTax call.
4. Tell us which of your entities should calculate tax with AvaTax.
5. Give us the GL account for collected sales tax (see section 2).
6. We map each entity to its Avalara company code and activate it.

> 🔒 **There's no field in Light for your Avalara credentials.** They live in Light's secure configuration rather than the product interface, and they're specific to your company. They're never shared with other Light customers. So send them across rather than hunting for a screen to paste them into.

## Entity mapping

Each Light entity maps to one AvaTax company profile. Light creates the mapping and activates it. To add or change one, contact Light support.

An entity can also be deactivated. Its new documents then fall back to Light's own tax engine. Anything already posted keeps the engine it was calculated with.

## AvaTax tax codes

AvaTax classifies items using Avalara tax codes. You set these on your products in Light:

1. Go to **Products**.
2. For each product, set **Default tax code**. To use an Avalara code, open the **Enter Avatax Code** dialog and enter it there.
3. When you add that product to a line on an AvaTax document, Light applies the product's code to the line.

On AvaTax documents each line shows its Avalara code as a read-only badge, so the code always follows the product. To change the code on a line, update the product's **Default tax code** and add the product again.

> 💡 **Using the API?** You can set the AvaTax code directly on invoice, contract and customer credit lines through Light's API, where it overrides the product default. The read-only badge is a property of the interface, not of the integration itself.

## What Light sends to AvaTax

For each document, Light sends:

- The customer's ship-to address, plus your entity's address as the ship-from
- The customer code, which is **Light's internal customer ID**. This matters for exemptions, see below.
- The customer's VAT number, where one is recorded
- Each line: description, quantity, amount, AvaTax tax code, and the product's Avalara product code

AvaTax works out the applicable jurisdictions, the rates and the tax per line, then returns the amounts to Light.

## Drafts, posting and voiding

> 💡 While an invoice is in draft, Light asks AvaTax for a tax preview without creating a permanent record. When you post it, Light creates and commits the transaction in AvaTax under the invoice's document number. If you archive a posted invoice, Light voids the matching AvaTax transaction as part of the reversal. That runs as a background job, so it isn't instant.

## Returns and refunds

When you issue a customer credit, Light calculates tax through AvaTax exactly as it does for invoices. On posting, it commits the credit to AvaTax as a return transaction, AvaTax records the reversal, and your tax liability drops accordingly. You don't need to reverse anything by hand.

## Customer exemption certificates

Exemption certificates live in your Avalara account, not in Light.

1. The customer gives you a certificate.
2. Record it against the customer in Avalara.
3. Light sends the customer code with every transaction. It doesn't send any exemption information.
4. AvaTax matches that customer code against the certificate on file and returns zero tax.

> ⚠️ **The customer code Light sends is the customer's internal Light ID.** Not their name, and not your own customer number. The certificate in Avalara has to be filed against that exact value or the match won't happen. This is the usual reason an exemption doesn't apply.

## Nexus, filing and remittance

You configure nexus in your Avalara account, not in Light. Add each state where you have nexus along with its effective date, and AvaTax will include those states in the calculations it returns.

Filing works from the transactions Light commits to AvaTax. In Avalara, AvaTax totals the tax owed per jurisdiction. Use Avalara's returns services to prepare and file, and to remit if you want them to. Keep track of each state's filing frequency and deadline and file on its schedule.

Avalara also holds the audit record: transactions, returns filed, payments made, and certificates on file. You can export audit packages from Avalara for your tax advisors.

Avalara can help you assess nexus in new states too, using your transaction data by state, so you can see whether an economic nexus threshold has been crossed before deciding to register.

## Troubleshooting AvaTax

| Symptom | What to check |
|---|---|
| Tax not calculating | The customer address is complete, nexus is configured for that state in Avalara, and AvaTax codes are assigned to the line items. |
| Wrong tax rate | The ship-to address (shipping, or billing if there isn't one), your entity's own address which sets the ship-from, state nexus in Avalara, and the line's AvaTax code. |
| Document won't post | Whether the entity's default sales tax account is linked. See section 2. |
| Exemption not applying | The certificate is current in Avalara and recorded against the customer's Light customer ID. |
| Connection failed | Contact Light support so we can check the stored credentials and your AvaTax account status. |
| Filing errors | Review the return detail in Avalara, fix any address or item coding issues, and re-file through Avalara. |

---

# 4. Sphere

Sphere works differently from AvaTax in one way that shapes everything below. **Light only ever asks Sphere to calculate tax.** It doesn't report posted invoices, credits or archived documents. Sphere gets your transaction data through its own connection to Light, which is why setup has two halves.

## Setting up Sphere

### Part 1: connect Light to Sphere (data sync)

This is what lets Sphere see your products and billing data.

1. In Sphere, click **Connect** on the Light tile.
2. In Light, go to **Settings → API keys** and generate an API key with the **Admin** role.
3. Paste that key into Sphere.
4. Your products will show up in Sphere shortly afterwards.

### Part 2: let Light calculate tax through Sphere

1. In Sphere, open the Light integration card and choose **Generate API key** to create a **Sphere Tax API key**.
2. Copy it straight away. Sphere only shows it once.
3. Send it to your Light contact. We store it against the specific entity that should use Sphere.
4. In Sphere, enable **Tax Calculations** for every region you're subscribed to.
5. Give us the GL account for collected sales tax (see section 2).
6. We create the entity record and activate it.

> 🔑 **Two keys, pointing in opposite directions.** The Light API key lets Sphere read from Light. The Sphere Tax API key lets Light call Sphere. They aren't interchangeable, and each one gets configured in the other product.

> ⚠️ Tax only routes to Sphere after step 6. Until the entity is activated, your documents get calculated by Light's own tax engine, which gives you a plausible looking but wrong answer rather than an error. So hold off on issuing invoices for the entity until we confirm it's active.

## Assigning tax codes

**There are no Sphere tax codes in Light.** Your products sync across to Sphere, and you assign each one a tax code in Sphere's **Products** tab. Light identifies each line by its product, and Sphere applies the code you set there.

Setting a Light tax code or an AvaTax code on a Sphere document is rejected.

> ⚠️ **Every line on a Sphere document needs a product.** Sphere can't classify a line without one, so a line with no product will block the calculation.

## What Light sends to Sphere

For each calculation, Light sends:

- The customer's address. **City, postal code and country are required.** State and street are optional.
- The customer's ID and tax ID (VAT number), where recorded
- Each line: the product, the amount, and whether the amount already includes tax
- The document currency

Sphere returns the tax per line, along with the rate, jurisdiction and tax type it applied.

> 💡 **If your Sphere account has a tax-inclusive rule**, say "prices are tax-inclusive outside the US and Canada", Sphere applies that rule and tells Light how it read the amount. Light goes with Sphere's answer. So changing that rule in Sphere will change the net amounts Light shows you, without anything changing in Light.

## Drafts, posting and returns

Sphere gets called the same way at every stage. There's no separate preview and commit. Posting an invoice writes the tax to your ledger in Light but **sends nothing to Sphere**. Same when you archive a document, and same for customer credits: the credit's tax is calculated through Sphere, and Light doesn't reverse anything on Sphere's side.

Sphere picks these transactions up through its own data sync instead, and that's what its reporting and filing are based on.

## Monitoring, registration, filing and remittance

These all happen in Sphere, using the data Sphere syncs from Light. Light doesn't drive any of them.

- **Monitoring** tracks your exposure by region against physical and economic nexus thresholds, and flags regions as approaching or breached.
- **Registration** lets you register in a region through Sphere.
- **Filing and remittance** covers your returns and payments for regions you've enabled.

See Sphere's own documentation for how each of these works.

> 💡 **Sphere isn't limited to the United States.** It returns sales tax, VAT, GST and other tax types depending on the region, and Light applies whatever Sphere sends back.

## Troubleshooting Sphere

| Message or symptom | What to do |
|---|---|
| Customer address is missing | Set the customer's shipping or billing address. |
| Customer city is missing | Sphere needs a city. Add it to the customer's address. |
| Customer zipcode is missing | Sphere needs a postal code. Add it to the customer's address. |
| Product is missing on the line | Every line needs a product. Add one. |
| Amount is missing on the line | Set the line amount. |
| Currency is not set | Set the document currency. |
| Tax calculated by the wrong engine | The entity isn't activated for Sphere yet. Contact Light support. |
| Document won't post | Whether the entity's default sales tax account is linked. See section 2. |
| Tax is zero or looks wrong for a region | Check that Tax Calculations is enabled for that region in Sphere, and that the product has a tax code in Sphere. |

---

# 5. AvaTax and Sphere side by side

| | AvaTax | Sphere |
|---|---|---|
| Used for | US customers of an activated entity | All customers of an activated entity |
| Credentials you provide | Avalara account ID and license key | Sphere Tax API key, plus a Light API key you give to Sphere |
| Tax codes | Set on products in Light | Set on products in Sphere |
| GL account for tax | Default sales tax account per entity | Default sales tax account per entity |
| What posting sends | A committed transaction | Nothing |
| What archiving sends | A void | Nothing |
| Credit notes | Committed as a return | Calculated only |
| How the provider sees your transactions | From what Light commits | From its own sync with Light |
| Nexus and registration | In your Avalara account | Sphere Monitoring and Registration |
| Filing and remittance | Avalara returns services | Sphere filing and remittance |
| Exemption certificates | Held in Avalara, matched on customer code | - |
