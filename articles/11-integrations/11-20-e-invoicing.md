# E-Invoicing - Knowledge and Setup

## 1. Overview

E-invoicing in Light enables businesses to send and receive legally compliant electronic invoices across multiple international networks and tax authorities.

Light supports a dual-provider architecture routing invoices through either Avalara or Invopop (in-development).

### 1.1 What is E-Invoicing

Electronic invoicing (e-invoicing) is the structured, digital exchange of invoice data between buyers and suppliers in a format recognized by tax authorities. Unlike PDF invoices, e-invoices are structured XML documents transmitted through certified networks such as:

- **Peppol**
  - Peppol (Pan-European Public Procurement OnLine) is a free, open network for electronic business document exchange, and the primary network Light supports via Avalara.
  - **Standardized format:** Uses UBL (Universal Business Language) XML
  - **Network operators:** Documents are routed through certified Peppol Access Points
  - **Global coverage:** 40+ countries and expanding, see country table in Section 1.3
  - **Mandatory in many jurisdictions:** EU countries and others require Peppol for B2B and B2G invoicing
  - **Free to join:** No licensing fees for network participation
- **SDI** (Italy)
- **KSeF** (Poland)
- **PDP** (France)
- etc

### 1.2 Why E-Invoicing Matters

- **Legal compliance:** Many countries mandate e-invoicing for B2B and B2G transactions
- **Reduced manual work:** Automated invoice delivery replaces manual processes
- **Faster payments:** Structured data enables faster bank reconciliation
- **Fewer rejections:** Validated invoices reduce errors before submission to tax authorities
- **International expansion:** Enables Light customers to operate across borders compliantly

### 1.3 Country-Specific Requirements

| Country | Network | Supported by Light | Provider | Mandate Scope | Mandate Status |
|---|---|---|---|---|---|
| Argentina | AFIP (Factura Electrónica) | N/A | N/A | B2G, B2B, B2C | Active |
| Australia | Peppol (PINT A-NZ) | Peppol | Avalara | B2G | Active |
| Austria | Peppol | Peppol | Avalara | B2G | Active |
| Belgium | Peppol | Peppol | Avalara | B2G | Active |
| Brazil | NF-e / NFS-e (SEFAZ) | N/A | N/A | B2G, B2B, B2C | Active |
| Canada | None | None | None | None | None |
| Chile | SII (Factura Electrónica) | N/A | N/A | B2G, B2B, B2C | Active |
| China | Golden Tax System (Fapiao) | N/A | N/A | B2G, B2B, B2C | Active |
| Colombia | DIAN | N/A | N/A | B2G, B2B, B2C | Active |
| Costa Rica | Ministerio de Hacienda | N/A | N/A | B2G, B2B, B2C | Active |
| Croatia | Fiscalization / Peppol | Peppol | Avalara | B2G | Active |
| Cyprus | Peppol | Peppol | Avalara | None | — |
| Czechia | Peppol | Peppol | Avalara | B2G | Active |
| Denmark | Nemhandel, Peppol | Peppol, Nemhandel | Avalara | B2G | Active |
| Ecuador | SRI | N/A | N/A | B2G, B2B, B2C | Active |
| Egypt | ETA (E-Invoice) | N/A | N/A | B2G, B2B | Active |
| Estonia | Peppol | Peppol | Avalara | B2G | Active |
| Finland | Peppol, Finvoice | Peppol (Live), Finvoice (Planned) | Avalara (Peppol), Finvoice (Invopop) | B2G | Active |
| France | Factur-X / ChorusPro / PDP, Peppol | Peppol | Avalara | B2G (B2B upcoming) | B2G Active, B2B Upcoming |
| Germany | XRechnung / ZUGFeRD, Peppol | Peppol (Live), ZUGFeRD (Planned) | Avalara (Peppol), ZUGFeRD (Invopop) | B2G (B2B upcoming) | B2G Active, B2B Upcoming |
| Greece | MyDATA (AADE), Peppol | Peppol (Live), AADE (Planned) | Avalara (Peppol), AADE (Invopop) | B2G, B2B, B2C | Active |
| Hungary | RTIR (Online Számla) | N/A | N/A | B2G, B2B | Active |
| India | IRP (e-Invoice) | N/A | N/A | B2G, B2B | Active |
| Indonesia | e-Faktur (DGT) | N/A | N/A | B2G, B2B, B2C | Active |
| Ireland | Peppol | Peppol | Avalara | B2G | Active |
| Israel | None | None | None | None | None |
| Italy | SDI / Scontrino | SDI | Avalara | B2G, B2B, B2C | Active |
| Japan | Peppol JP PINT | Peppol | Avalara | B2G | Active |
| Jordan | ISTD | N/A | N/A | B2G, B2B | Active |
| Kenya | eTIMS (KRA) | N/A | N/A | B2G, B2B | Active |
| Luxembourg | Peppol | Peppol | Avalara | B2G | Active |
| Macao | None | None | None | None | None |
| Malaysia | MyInvois (LHDN) | N/A | N/A | B2G, B2B, B2C | Upcoming |
| Malta | Peppol | Peppol | Avalara | B2G | Active |
| Mexico | CFDI (SAT) | N/A | N/A | B2G, B2B, B2C | Active |
| Morocco | DGI | N/A | N/A | B2G | Upcoming |
| Netherlands | Peppol | Peppol | Avalara | B2G | Active |
| New Zealand | Peppol (PINT A-NZ) | Peppol | Avalara | B2G | Active |
| Nigeria | FIRS | N/A | N/A | B2G, B2B | Upcoming |
| Norway | Peppol | Peppol | Avalara | B2G | Active |
| Pakistan | FBR | N/A | N/A | B2G, B2B | Active |
| Peru | SUNAT | N/A | N/A | B2G, B2B, B2C | Active |
| Philippines | None | None | None | None | None |
| Poland | Peppol, KSeF | Peppol | Avalara | B2G (B2B KSeF upcoming) | B2G Active, B2B Upcoming |
| Portugal | QR/ATCUD, Peppol | Peppol | Avalara | B2G, B2B, B2C | Active |
| Romania | RO e-Factura | N/A | N/A | B2G, B2B, B2C | Active |
| Saudi Arabia | ZATCA (Fatoora) | N/A | N/A | B2G, B2B, B2C | Active |
| Singapore | Peppol, InvoiceNow | Peppol | Avalara | B2B | Upcoming |
| South Africa | None | None | None | None | None |
| South Korea | e-Tax Invoice (NTS) | N/A | N/A | B2G, B2B | Active |
| Spain | VeriFactu, TicketBAI, Facturae, SII, Peppol | Peppol | Avalara | B2G | Active |
| Sweden | Peppol | Peppol | Avalara | B2G | Active |
| Switzerland | SwissDIGIN, Factur-X, ZUGFeRD, Peppol | Peppol | Avalara | B2G | Active |
| Taiwan | e-Invoice (MoF) | N/A | N/A | B2G, B2B, B2C | Active |
| Thailand | e-Tax Invoice & Receipt (RD) | N/A | N/A | B2G, B2B | Active |
| Tunisia | El Fatoura | N/A | N/A | B2G, B2B, B2C | Active |
| Turkey | e-Fatura / e-Arşiv | N/A | N/A | B2G, B2B, B2C | Active |
| UAE | UBL ZATCA | N/A | N/A | B2G, B2B | Upcoming |
| UK | Peppol | Peppol | Avalara | B2G | Active |
| US | DBNAlliance | N/A | N/A | Upcoming | Upcoming |
| Uruguay | DGI (e-CF) | N/A | N/A | B2G, B2B, B2C | Active |
| Vietnam | e-Invoice (GDT) | N/A | N/A | B2G, B2B, B2C | Active |

### 1.4 E-Invoicing Directory

- **Peppol:** https://directory.peppol.eu/public/locale-en_US/menuitem-search
- **Nemhandel:** https://registration.nemhandel.dk/NemHandelRegisterWeb/public/participant/info
- **SDI:** n/a

### 1.5 E-Invoicing Identifier & Validation Format

This section helps Implementation Managers and customers provide the correct e-invoicing identifiers when setting up entities and customers in Light.

#### Peppol

A Peppol ID always follows this format:

```
<ICD Code>:<Identifier Value>
```

**Example:** `0007:5566778899` → Swedish Org Number

The ICD code (4-digit prefix) identifies the **type** of business identifier being used. The value after the colon is the actual business identifier — never include country prefixes or spaces.

✅ **Valid:** `0192:999888777`
❌ **Invalid:** `INVALIDID`, `192:999888777`, `0192-999888777`

**Peppol Schemes by Country**

| Country | Business Registration No | VAT Format | Example VAT | IDC | Example Peppol IDs |
|---|---|---|---|---|---|
| Australia | ABN (11 digits) | 11 digits, no prefix | 51824753556 | 0151 (ABN), 0088 (GLN) | `0151:51824753556` / `0088:1234567890123` |
| Austria | VAT ID | ATU + digits | ATU12345678 | 9914 (VAT) | `9914:ATU12345678` |
| Belgium | Enterprise No | BE + 10 digits | BE0123456789 | 0208 (Enterprise No), 9925 (VAT), 0088 (GLN) | `0208:0123456789` / `9925:BE0123456789` / `0088:1234567890123` |
| Bulgaria | VAT | BG + digits | BG123456789 | 9926 (VAT) | `9926:BG123456789` |
| Croatia | VAT | HR + digits | HR12345678901 | 9934 (VAT) | `9934:HR12345678901` |
| Cyprus | VAT | CY + digits | CY12345678X | 9928 (VAT) | `9928:CY12345678X` |
| Czech Republic | VAT | CZ + digits | CZ12345678 | 9929 (VAT) | `9929:CZ12345678` |
| Denmark | CVR (8 digits) | Same as CVR | 12345678 | 0184 (CVR), 0088 (GLN) | `0184:12345678` / `0088:1234567890123` |
| Estonia | Company Code | EE + digits | EE12345678 | 0191 (Company Code), 0088 (GLN) | `0191:12345678` / `0088:1234567890123` |
| Finland | Business ID (Y-tunnus) | FI + number | FI12345678 | 0037 (Business ID), 0088 (GLN) | `0037:12345678` / `0088:1234567890123` |
| France | SIRET (14 digits) | FR + VAT | FR12345678901 | 0009 (SIRET), 9957 (VAT), 0088 (GLN) | `0009:12345678901234` / `9957:FR12345678901` / `0088:1234567890123` |
| Germany | VAT ID | DE + 9 digits | DE123456789 | 9930 (VAT), 0088 (GLN), 0060 (DUNS) | `9930:DE123456789` / `0088:1234567890123` / `0060:123456789` |
| Global | DUNS Number | 9 digits | 123456789 | 0060 (DUNS) | `0060:123456789` |
| Global | GLN (GS1) | 13 digits | 1234567890123 | 0088 (GLN) | `0088:1234567890123` |
| Global | LEI | 20 alphanumeric chars | 5493001KJTIIGC8Y1R12 | 0216 (LEI) | `0216:5493001KJTIIGC8Y1R12` |
| Greece | VAT | EL + digits | EL123456789 | 9933 (VAT) | `9933:EL123456789` |
| Hungary | VAT | HU + digits | HU12345678 | 9910 (VAT) | `9910:HU12345678` |
| Ireland | VAT | IE + digits | IE1234567A | 9935 (VAT) | `9935:IE1234567A` |
| Italy | VAT | IT + 11 digits | IT12345678901 | 9906 (VAT), 0088 (GLN) | `9906:IT12345678901` / `0088:1234567890123` |
| Japan | Corporate No (13 digits) | 13 digits, no prefix | 1234567890123 | 0188 (Corporate No) | `0188:1234567890123` |
| Latvia | VAT | LV + digits | LV12345678901 | 9939 (VAT) | `9939:LV12345678901` |
| Lithuania | VAT | LT + digits | LT123456789 | 9938 (VAT) | `9938:LT123456789` |
| Luxembourg | SIRENE | B + digits | B123456 | 0002 (SIRENE) | `0002:B123456` |
| Netherlands | KvK No | NL + VAT | NL123456789B01 | 0106 (KvK), 9930 (VAT), 0088 (GLN) | `0106:12345678` / `9930:NL123456789B01` / `0088:1234567890123` |
| Norway | Org No (9 digits) | Org No + MVA | 999888777MVA | 0192 (OrgNr), 0088 (GLN) | `0192:999888777` / `0088:1234567890123` |
| Poland | VAT | PL + digits | PL1234567890 | 9945 (VAT) | `9945:PL1234567890` |
| Portugal | NIF | PT + 9 digits | PT123456789 | 9937 (VAT) | `9937:PT123456789` |
| Romania | VAT | RO + digits | RO12345678 | 9936 (VAT) | `9936:RO12345678` |
| Singapore | UEN (alphanumeric) | Alphanumeric | 201901234K | 0195 (UEN), 0088 (GLN) | `0195:201901234K` / `0088:1234567890123` |
| Slovakia | VAT | SK + digits | SK2020123456 | 9950 (VAT) | `9950:SK2020123456` |
| Spain | VAT / NIF | ES + digits | ESB12345678 | 9920 (VAT), 0088 (GLN) | `9920:ESB12345678` / `0088:1234567890123` |
| Sweden | Org Nr (10 digits) | SE + Org No + 01 | SE556677889901 | 0007 (OrgNr), 0088 (GLN) | `0007:5566778899` / `0088:1234567890123` |
| Switzerland | UID | CHE-123.456.789 | CHE123456789 | 0183 (UID), 0088 (GLN) | `0183:CHE123456789` / `0088:1234567890123` |
| United Kingdom | GLN / VAT | GB + digits | GB123456789 | 0088 (GLN), 9932 (VAT), 0060 (DUNS) | `0088:1234567890123` / `9932:GB123456789` / `0060:123456789` |

> 💡 **GLN (0088), DUNS (0060), and LEI (0216)** are global schemes accepted across all countries — useful when a company is registered under one of these instead of a country-specific identifier.

Use these rules to quickly validate a Peppol ID before submitting:

| Rule | Check |
|---|---|
| Format | Must be `NNNN:value` — 4-digit ICD code, colon, then the identifier |
| ICD Code | Must be a valid ICD code from the table above |
| No spaces | No spaces anywhere in the ID |
| No dashes as separator | Separator is always `:` not `-` |
| Case sensitivity | Some identifiers are case-sensitive (e.g. UEN in Singapore) |
| Country prefix in value | Depends on scheme — VAT schemes (9xxx) include the country prefix (e.g. `DE123...`), Org No schemes (0xxx) typically do not |

#### Nemhandel

A Nemhandel identifier follows the same format as Peppol:

```
<EAS Code>:<Identifier Value>
```

| EAS Code | Scheme ID | Identifier Type | Format / Validation | Example | Use Case |
|---|---|---|---|---|---|
| `0088` | GLN | EAN/GLN — GS1 Global Location Number | 13 digits | `0088:5790000435944` | Most common — default for both B2B and B2G |
| `9902` | DK:CVR | Danish Company Registration Number | 8 digits | `9902:12345678` | Standard for Danish companies |
| `0184` | CVR | Danish Company Register (ISO) | 8 digits | `0184:12345678` | Alternative CVR scheme — ISO version |
| `9904` | DK:SE | Danish SE number (VAT/tax) | 8 digits | `9904:12345678` | Tax registered entities |
| `9905` | DK:VANS | Value Added Network Services | Alphanumeric | `9905:VANS12345` | Legacy EDI-based routing |
| `0096` | DK:P | P-number (production unit) | 10 digits | `0096:1234567890` | Specific production unit routing |

> 💡 Danish companies may also be reachable on **Peppol** using `0184:CVR`.
>
> If a customer asks which to use:
> - **Nemhandel** for Danish public sector (B2G)
> - **Peppol** for cross-border B2B.

#### SDI

SDI (Sistema di Interscambio) is Italy's mandatory e-invoicing clearance network. Unlike Peppol, SDI uses its own scheme codes (not ICD codes).

A SDI identifier is structured as:

```
<EAS Code (schemeID)>:<EndpointID value>
```

| EAS Code | Identifier Type | Meaning | Format / Validation | Example |
|---|---|---|---|---|
| `0211` | Italian VAT number | Partita IVA — standard B2B, most common | `IT` + 11 digits | `0211:IT01234567890` |
| `0210` | Italian tax code | Codice Fiscale — individual or sole trader | 16 alphanumeric chars (individual) / 11 digits (company) | `0210:RSSMRA85M01H501Z` / `0210:01234567890` |
| `0201` | IPA code | Public administration — B2G only | 6 alphanumeric chars | `0201:ABCDEF` |
| `0088` | GLN | GS1 identifier — alternative when GLN is registered | 13 digits | `0088:1234567890123` |
| `0000000` | SDI recipient code | Codice Destinatario — legacy / fallback routing | 7 alphanumeric chars | `0000000:ABC1234` |

> ⚠️ **Which EAS code to use?**
> - **B2B** → use `0211` (Partita IVA) as default
> - **Individual / sole trader** → use `0210` (Codice Fiscale)
> - **Public sector (B2G)** → use `0201` (IPA code) — find IPA codes at https://www.indicepa.gov.it
> - **Fallback / legacy** → use `0000000` (Codice Destinatario) only when the recipient doesn't have a VAT or IPA code registered on SDI

## 2. Architecture: Dual-Provider Model

Light will operate a dual-provider e-invoicing architecture, delivering flexibility based on user preferences and network availability. Invopop is currently under development and will form part of this setup once released.

## 3. Setup Guide

### 3.1 Avalara Setup

This section applies to customers being onboarded to e-invoicing using the **Avalara** integration. Currently, Light supports the following networks via Avalara:

- Peppol
- Nemhandel
- SDI

#### Step 1: Pre-Setup

Before touching any system, confirm the following with the customer:

1. **Identify the e-invoicing channel(s) needed**
   Confirm which network(s) the customer needs to be registered on:
   - **Peppol:** Used across EU (Germany, Sweden, Finland, Belgium, Netherlands, etc.)
   - **Nemhandel:** Denmark specifically
   - **SDI:** Italy only

2. **Check if the customer already has an existing e-invoicing ID**
   Ask: *"Do you already have a Peppol ID / Nemhandel ID / SDI Codice Destinatario from a previous provider?"*
   - **Yes** → Ask them to provide the ID and arrange to decouple/transfer it from their previous provider before proceeding.
   - **No** → A new ID will be created on their behalf during Avalara onboarding.

3. **Collect the required information per network**

For **Peppol or Nemhandel**, collect:

| # | Field | Notes |
|---|---|---|
| 1 | Company Legal Name | As registered |
| 2 | Country | ISO country code |
| 3 | Address Line 1 | |
| 4 | Address Line 2 | Optional |
| 5 | City | |
| 6 | Postal Code | |
| 7 | Preferred Identifier Type | **Always force to use VAT ID (Peppol) or CVR (Nemhandel)** |
| 8 | Identifier Number | The actual number for the chosen identifier |
| 9 | Legal Representative Email | Used to receive Avalara setup emails — must be the actual legal rep |
| 10 | Legal Representative First Name | |
| 11 | Legal Representative Last Name | |
| 12 | Legal Representative Phone | |
| 13 | Legal Representative Position | e.g. CEO, CFO, Director |
| 14 | Business Registration Certificate | PDF format required |

For **SDI (Italy)**, additionally collect:

- Supplier VAT number (*Partita IVA*)
- Fiscal code (*Codice Fiscale*), if different from VAT
- Recipient Code (*Codice Destinatario*) — 7-character code, or PEC email as fallback
- Confirmation of invoice numbering format (must be sequential)
- Whether **archive** is required (if yes, Namirial forms must be sent to Italian tax authorities for validation — handle separately)

> ⚠️ **IMPORTANT:** Hand off all collected information to the IM or Tech Implementation team before proceeding to Step 2.

#### Step 2: Enable E-Invoicing Integration in Light

- Log in to Light as a **company admin**
- Navigate to: **Settings → Integrations** → `https://app.light.inc/settings/integrations`
- Click **"Add Integration"** and select **"Avalara"**
- Complete the initial setup form
- Once submitted, Avalara will send a confirmation email to the account — this may take a few minutes

#### Step 3: Avalara Platform Configuration

- Log in to the Avalara e-invoicing portal: `https://vatreturns.avalara.com`
- Follow the onboarding instructions in the email from Avalara
- Add `integration@light.inc` **as an admin user** in the Avalara account — this is required for visibility and support
- Configure each company entity within Avalara:
  - Enter legal name, address, and tax registration details
  - Verify the correct identifier scheme is selected (VAT, GLN, OrgNo, etc.) — **this must match what was agreed in Step 1**
  - Confirm compliance requirements for each entity's country

> ⚠️ **IMPORTANT:** Save the Avalara client login credentials to 1Password in the shared folder immediately after setup is complete.

#### Step 4: Configure E-Invoicing Details Per Entity

Select the E-Invoicing and Live Reporting mandates that you need to activate for each of your entities. You will need to submit entity information as outlined in the Pre-Setup section. Please allow up to 1 working day to receive a response on whether the E-Invoicing ID application (e.g., Peppol, Nemhandel, SDI) has been completed or failed.

After configuring entities in Avalara, the **legal representative** of each entity will receive a separate email per entity containing the Peppol/e-invoicing network identifier.

The email contains a string in this format:

```
iso6523-actorid-upis::<EAS code>:<e-invoice address>
```

**Example:**

- EAS Code: `9902`
- E-invoice Address: `DK43523503`
- Full string: `iso6523-actorid-upis::9902:DK43523503`

This information can also be found directly within Avalara.

> 📌 **NOTE:** The EAS code corresponds directly to the identifier type selected during Avalara onboarding (e.g. VAT = 9930, GLN = 0088, OrgNo = varies by country). The same registration number must be used in the entity settings in Light (Step 5).

If the email has not arrived after 24 hours:

- Check that the legal representative email entered in Avalara is correct
- Verify the entity was fully saved in Avalara
- This information can also be found directly within the Avalara platform under the entity's profile

#### Step 5: API Key and Webhook Configuration

**Create the Webhook**

In the Avalara platform, navigate to **Integrations** and create a new integration with the following settings:

| Field | Value |
|---|---|
| Integration Type | Webhook |
| Endpoint URL | `https://api.light.inc/rest/v1/avalara/webhooks/document-status-change` |
| Description | Webhook integration with Light |
| Message Signature Key | `hexke0-zabbig-taQnuc` |
| Status | Active |
| Events to Send | Document Complete, Document Error |

**Create the API Key and Secret**

- Navigate to: `https://app.avalara.com/integrations/license-keys`
- Create a new license key
- **Copy both the key and secret immediately** — the secret will not be shown again
- Store both securely in **1Password** in the shared folder
- Share with the Tech Implementation team via 1Password

**Link Avalara and Light in Retool**

- Navigate to the Retool tool: `https://lightspace.retool.com/apps/d760dcce-e008-11f0-b212-83862665bfba/Avalara/page1`
- Retrieve your **Light API Token** from your Light Dashboard and paste it into Retool.
- Select the correct company
- Enter the **API Key** and **Secret** from Avalara
- Press **Submit**
- Click **Refresh** — confirm the network shows as registered successfully

**Link Entities in Retool**

- Register company entity from Avalara to Light
- Repeat this process to **link each entity individually** from Avalara to Light

> 📹 Reference setup video: https://drive.google.com/file/d/1xnstpX-M7MF368sZwT7dZLsxdDCQiikE/view

#### Step 6: Entity Details Configuration

1. Navigate to: **Settings → Entities** → `https://app.light.inc/settings/entities`
2. For each entity, enter the following exactly as provided in the Avalara email:
   - **EAS Code** (e.g. `9902`)
   - **E-Invoice Address** (e.g. `DK43523503`)
   - **VAT Number**
   - **Business Registration Number**
3. Double-check that the EAS code and registration number are consistent with what was selected in Avalara — mismatches are a common cause of validation failures

> 📌 This step must be completed for **every entity** that needs to send or receive e-invoices. Entities without these fields configured will not be able to submit e-invoices.

#### Step 7: Configure E-Invoicing Details Per Customer

This step sets up each customer (buyer) so that Light knows where to send e-invoices addressed to them. It is usually completed by the client themselves, but as an IM you may need to:

- Assist customers who are unsure of their e-invoicing details or the correct format
- Complete this yourself when testing, since the test requires your entity to be registered as a valid e-invoice **receiver**

**How to access:**

- Navigate to **Sales Invoices → Customers** → `https://app.light.inc/customers`
- Create a new customer or open an existing one, then fill in the e-invoicing fields.

**Fields to complete:**

| Field | Description | Example |
|---|---|---|
| EAS Code | The identifier scheme code that corresponds to the type of business ID being used. This must match the customer's registered identifier type on their e-invoicing network. | `9930` = German VAT, `0088` = GLN, `0192` = Norwegian Org No, `0106` = Danish CVR |
| E-Invoice Address | The actual identifier value — this is the customer's unique address on the e-invoicing network. Do not include the EAS code prefix here. | `DK43523503`, `DE123456789` |
| E-Invoice Network | The network the customer is registered on. Must match the sender's registered network — you cannot send a Peppol invoice to an SDI address. | `Peppol`, `Nemhandel`, `SDI` |
| Customer Type | Determines validation rules and routing logic. B2G always requires an e-invoicing address. B2B requires one if structured e-invoicing is enabled. B2C is optional. | `Business (B2B)`, `Government (B2G)`, `Consumer (B2C)` |

> 💡 **Not sure what the customer's EAS code or e-invoice address is?**
>
> Use the e-invoicing directories in **Section 1.4** to look up a company by name or registration number:
> - **Peppol:** https://directory.peppol.eu/public/locale-en_US/menuitem-search
> - **Nemhandel:** https://registration.nemhandel.dk/NemHandelRegisterWeb/public/participant/info
> - **SDI:** No public directory — the Codice Destinatario must be obtained directly from the Italian customer

#### Step 8: Configure EDIFACT Codes on Tax Codes

Tax codes in Light include an optional **EDIFACT** field that classifies the tax treatment within outgoing e-invoice XML. This is required for invoices to be accepted by certain tax authorities and recipients.

**How to configure:**

1. Navigate to: **Accounting → Tax codes** → `https://app.light.inc/accounting/ledger-tax-codes`
2. Click **+ Create tax code**, or open an existing tax code and click **Edit**
3. Select the appropriate **EDIFACT (optional)** code from the dropdown
4. Save

The selected EDIFACT code is included in the e-invoice document to classify the tax treatment (e.g. standard VAT, zero-rated, reverse charge, exempt).

> 💡 Assign EDIFACT codes to **every tax code** that will be used on e-invoice transactions. Missing EDIFACT codes are a common cause of invoice rejection at the Peppol/SDI validation layer.

#### Step 9: Test Before Go-Live

- **Create a test e-invoice** from one entity to another (vendor to vendor)
- Verify the invoice is submitted to Avalara successfully
- Confirm status updates are received back in Light (Document Complete or Document Error webhook events)
- Check the full invoice lifecycle: Submitted → Validated → Delivered
- For Italy (SDI): confirm the Codice Destinatario is correctly included in the XML and that the invoice is accepted by SDI

### 3.2 Invopop Setup

**Coming Soon:** Light will operate a dual-provider e-invoicing architecture, delivering flexibility based on user preferences and network availability. Invopop will serve as the modern self-service rail for all new customers onboarded from 2026 onwards, complementing the existing Avalara integration.

Invopop is currently under development. Full setup instructions, configuration steps, and supported networks will be documented here once the integration is released. In the meantime, all new customers should be onboarded via the **Avalara Setup** guide in Section 3.1.

For the latest updates on Invopop's release timeline, contact **Tech Partnership**.

### 3.3 Invopop Setup

## 4. Glossary

| Term | Definition |
|---|---|
| **AADE** | *Ανεξάρτητη Αρχή Δημοσίων Εσόδων* — Greece's Independent Authority for Public Revenue. Operates the MyDATA digital tax reporting platform |
| **AFIP** | *Administración Federal de Ingresos Públicos* — Argentina's federal tax authority. Operates the mandatory Factura Electrónica e-invoicing system |
| **AP** | Accounts Payable — the process of managing and paying incoming invoices from suppliers |
| **AR** | Accounts Receivable — the process of managing and collecting payment for outgoing invoices to customers |
| **ATCUD** | *Código Único de Documento* — Portugal's mandatory unique document code. Combined with a QR code on invoices for tax authority validation |
| **Avalara** | Third-party tax compliance and e-invoicing provider. Light's provider for Peppol, Nemhandel, and SDI |
| **B2B** | Business to Business — commercial transactions between two businesses |
| **B2C** | Business to Consumer — commercial transactions between a business and an individual consumer |
| **B2G** | Business to Government — commercial transactions between a business and a public sector entity |
| **BIC** | Bank Identifier Code — also known as SWIFT code. Identifies a specific bank in international transactions |
| **BIS** | Business Interoperability Specifications — the standard invoice format used on the Peppol network (e.g. Peppol BIS Billing 3.0) |
| **CFDI** | *Comprobante Fiscal Digital por Internet* — Mexico's mandatory digital tax receipt format. Issued and validated through SAT (Mexico's tax authority) |
| **Chorus Pro** | France's official public procurement portal for B2G e-invoicing. Mandatory for invoices addressed to French public sector entities |
| **CII** | Cross-Industry Invoice — a UN/CEFACT XML standard used in some European e-invoicing regimes (e.g. ZUGFeRD, Factur-X) |
| **Clearance Model** | An e-invoicing model where invoices must be submitted to and approved by a tax authority before being delivered to the buyer. Used in Italy (SDI), Saudi Arabia (ZATCA), and others |
| **Codice Destinatario** | A 7-character alphanumeric code assigned to Italian businesses for SDI routing. Required on all B2B invoices in Italy unless a PEC email is used |
| **Codice Fiscale** | Italian individual or company tax identification code. Required on SDI invoices for sole traders and individuals |
| **CVR** | Central Business Register number — Denmark's company registration number. Used as the primary identifier for Nemhandel and Peppol in Denmark |
| **DBNAlliance** | Digital Business Networks Alliance — the US e-invoicing network initiative. Adoption is voluntary and still in early stages |
| **DIAN** | *Dirección de Impuestos y Aduanas Nacionales* — Colombia's tax and customs authority. Operates the mandatory e-invoicing clearance system |
| **DGI** | *Direction Générale des Impôts* — Tax authority name used in Morocco and Uruguay. Operates national e-invoicing platforms in both countries |
| **DGT** | Directorate General of Taxes — Indonesia's tax authority. Operates the mandatory e-Faktur e-invoicing system |
| **DUNS** | Dun & Bradstreet Universal Numbering System — a global 9-digit business identifier. Peppol scheme code `0060` |
| **EAN** | European Article Number — a 13-digit barcode/identifier. In e-invoicing context, used interchangeably with GLN for routing on Nemhandel and Peppol |
| **EAS Code** | Electronic Address Scheme code — a 4-digit code that identifies the type of business identifier used in Peppol and Nemhandel addressing (e.g. 9930 = German VAT, 0088 = GLN, 0192 = Norwegian Org No) |
| **e-Arşiv** | Turkey's e-archive invoice system for B2C transactions and companies not registered on the e-Fatura network |
| **e-Faktur** | Indonesia's mandatory electronic tax invoice system operated by DGT. Required for VAT-registered businesses |
| **e-Fatura** | Turkey's mandatory structured e-invoice format for B2B and B2G transactions, submitted through the Revenue Administration (GIB) |
| **e-Invoice / E-Invoicing** | The structured, digital exchange of invoice data between buyers and suppliers in a machine-readable format (XML) recognized by tax authorities. Different from a PDF invoice |
| **El Fatoura** | Tunisia's national e-invoicing platform operated by the tax authority. Mandatory for B2G, B2B, and B2C transactions |
| **Endpoint ID** | The actual identifier value used to route an e-invoice to a specific recipient on a network (e.g. a VAT number, GLN, or Org number) |
| **eTIMS** | Electronic Tax Invoice Management System — Kenya's e-invoicing platform operated by KRA (Kenya Revenue Authority) |
| **Factur-X** | A Franco-German hybrid e-invoice format that embeds structured XML (CII) data inside a PDF. Used in France and Switzerland. Also known as ZUGFeRD in Germany |
| **Facturae** | Spain's structured XML e-invoice format, used primarily for B2G invoicing to Spanish public administrations |
| **FatturaPA** | The mandatory XML format for Italian electronic invoices transmitted via SDI |
| **FBR** | *Federal Board of Revenue* — Pakistan's tax authority. Operates the mandatory e-invoicing system for registered businesses |
| **FIRS** | *Federal Inland Revenue Service* — Nigeria's tax authority. An e-invoicing mandate is in development |
| **Finvoice** | Finland's domestic e-invoicing standard, used alongside Peppol. Not yet supported by Light |
| **Fiscalization** | Croatia's mandatory fiscal invoice system requiring real-time reporting of all cash transactions to the tax authority |
| **GDT** | *General Department of Taxation* — Vietnam's tax authority. Operates the mandatory e-Invoice system for all businesses |
| **GLN** | Global Location Number — a 13-digit GS1 identifier used globally. Peppol scheme code `0088`. Universally accepted across all Peppol-connected networks as a fallback identifier |
| **GOBL** | Go Business Language — an open-source structured data format developed by Invopop for representing business documents (invoices, credit notes, parties) |
| **GOBL Party** | A GOBL object representing a business entity (legal name, VAT, address, contact). Used by Invopop during e-invoice registration and sending |
| **IAS** | Invoice Archiving Service — long-term digital storage of e-invoices to meet legal retention requirements (e.g. 10 years in Germany, Italy) |
| **IBAN** | International Bank Account Number — used on e-invoices to specify payment destination for bank transfer |
| **ICD Code** | International Code Designator — the 4-digit scheme code in Peppol that identifies what type of business identifier is being used. Also referred to as EAS Code |
| **IM** | Implementation Manager — the Light team member responsible for onboarding a customer and setting up their e-invoicing configuration |
| **InvoiceNow** | Singapore's Peppol-based national e-invoicing network |
| **Invopop** | Third-party e-invoicing provider. Light's latest provider, supports Peppol, SDI, KSeF, PDP, and other networks |
| **IPA Code** | *Indice delle Pubbliche Amministrazioni* — a 6-character code identifying Italian public sector entities on SDI. Required for B2G invoices in Italy. EAS code `0201` |
| **IRP** | Invoice Registration Portal — India's e-invoicing clearance portal operated by the GST Network (GSTN). Mandatory for businesses above a turnover threshold |
| **ISTD** | *Income and Sales Tax Department* — Jordan's tax authority. Operates the mandatory e-invoicing system for registered businesses |
| **KRA** | *Kenya Revenue Authority* — Kenya's tax authority. Operates the eTIMS e-invoicing platform |
| **KSeF** | *Krajowy System e-Faktur* — Poland's national e-invoicing clearance system. B2B mandate upcoming |
| **KvK** | *Kamer van Koophandel* — Netherlands Chamber of Commerce registration number. Peppol scheme code `0106` |
| **Legal Entity** | A company or organization registered in a specific country. In Light, each legal entity has its own e-invoicing configuration (EAS code, e-invoice address, provider) |
| **LEI** | Legal Entity Identifier — a 20-character global identifier for legal entities. Peppol scheme code `0216` |
| **LHDN** | *Lembaga Hasil Dalam Negeri* — Malaysia's Inland Revenue Board. Operates the MyInvois e-invoicing platform, currently rolling out in phases |
| **Mandate** | A legal requirement imposed by a government for businesses to use e-invoicing. Can be B2G only, B2B, or B2C depending on the country |
| **MoF** | Ministry of Finance — used in multiple countries (e.g. Taiwan's MoF operates the national e-Invoice platform) |
| **MyDATA** | Greece's digital tax reporting platform operated by AADE. Requires real-time reporting of invoice data |
| **MyInvois** | Malaysia's national e-invoicing platform operated by LHDN. Mandatory for businesses above a turnover threshold, with phased rollout from 2024 |
| **NAV** | *Nemzeti Adó- és Vámhivatal* — Hungary's National Tax and Customs Administration. Operates the RTIR (Online Számla) real-time invoice reporting system |
| **Nemhandel** | Denmark's national e-invoicing network (also known as NHR — NemHandel Register). Mandatory for B2G. Supports GLN, CVR, SE number, and other schemes |
| **NF-e** | *Nota Fiscal Eletrônica* — Brazil's mandatory electronic invoice format for goods |
| **NFS-e** | *Nota Fiscal de Serviços Eletrônica* — Brazil's mandatory electronic invoice for services (complements NF-e which covers goods) |
| **NTS** | *National Tax Service* — South Korea's tax authority. Operates the mandatory e-Tax Invoice system for VAT-registered businesses |
| **Online Számla** | Hungary's real-time invoice reporting system operated by NAV. All VAT-registered businesses must report invoice data in real time |
| **Org No / OrgNr** | Organisation Number — used in Norway (`0192`) and Sweden (`0007`) as the primary Peppol identifier |
| **Partita IVA** | Italian VAT registration number. Required on all SDI invoices. EAS code `0211` on SDI |
| **PEC** | *Posta Elettronica Certificata* — Italy's certified email system. Used as a fallback routing address on SDI when no Codice Destinatario is available |
| **Peppol** | Pan-European Public Procurement Online — a global network of certified access points for exchanging e-documents. Uses standardised UBL or CII XML formats |
| **Peppol Access Point** | A certified service provider that connects businesses to the Peppol network for sending and receiving documents. Avalara and Invopop act as access points for Light |
| **Peppol BIS** | Peppol Business Interoperability Specifications — the standard document format used on Peppol (e.g. BIS Billing 3.0 for invoices) |
| **PDP** | *Plateforme de Dématérialisation Partenaire* — France's certified e-invoicing platform operator. Required for the upcoming French B2B e-invoicing mandate |
| **PINT A-NZ** | Peppol International ANZ — the Peppol invoice format profile adopted by Australia and New Zealand for cross-border and domestic e-invoicing |
| **Provider** | In Light's context, the third-party service used to send and receive e-invoices. Currently either Avalara (legacy) or Invopop (new) |
| **RD** | *Revenue Department* — Thailand's tax authority. Operates the e-Tax Invoice & e-Receipt system |
| **Registration Workflow** | The Invopop process by which a business registers its identity on an e-invoicing network (Peppol, SDI, etc.). Can be triggered via API or embedded iframe |
| **Retool** | Light's internal tooling platform. Used by the Tech Implementation team to link Avalara API credentials to Light entities |
| **RO e-Factura** | Romania's mandatory e-invoicing clearance system. All B2G and B2B invoices must be submitted to and validated by the Romanian tax authority (ANAF) before delivery |
| **RTIR** | *Real-Time Invoice Reporting* — Hungary's system for real-time reporting of invoice data to the tax authority (NAV) |
| **SAT** | *Servicio de Administración Tributaria* — Mexico's tax authority. Validates and certifies all CFDI e-invoices |
| **SDI** | *Sistema di Interscambio* — Italy's mandatory e-invoicing clearance platform operated by the Italian tax authority (Agenzia delle Entrate). All B2B, B2G, and B2C invoices in Italy must pass through SDI |
| **SE Number** | Danish tax/VAT registration number (SE-nummer). Used for Nemhandel routing. Scheme code `9904` |
| **SEFAZ** | *Secretaria da Fazenda* — Brazil's state-level tax authority. Oversees the NF-e and NFS-e e-invoicing systems |
| **SII** | Can refer to two systems: (1) *Servicio de Impuestos Internos* — Chile's tax authority operating Factura Electrónica; (2) *Suministro Inmediato de Información* — Spain's real-time VAT reporting system |
| **Silo API** | Invopop's document storage API. Used to create and store GOBL entries (invoices, parties) before triggering workflows |
| **SIRET** | French establishment identifier (14 digits). Used as the primary Peppol scheme for French companies. ICD code `0009` |
| **SRI** | *Servicio de Rentas Internas* — Ecuador's tax authority. Operates the mandatory e-invoicing system for all businesses |
| **SUNAT** | *Superintendencia Nacional de Aduanas y de Administración Tributaria* — Peru's tax authority. Operates the mandatory electronic invoicing system |
| **SwissDIGIN** | A Swiss e-invoicing standard based on ZUGFeRD/Factur-X, used for structured invoice exchange in Switzerland |
| **TicketBAI** | A Basque Country (Spain) mandatory e-invoicing and fiscal ticketing system. Applies to businesses operating in the Basque region |
| **UBL** | Universal Business Language — an OASIS XML standard for business documents including invoices. The primary format used on the Peppol network |
| **UBL ZATCA** | The XML invoice format based on Universal Business Language (UBL) used by Saudi Arabia's ZATCA Fatoora e-invoicing platform |
| **UID** | Swiss business identifier (*Unternehmens-Identifikationsnummer*). Format: `CHE-xxx.xxx.xxx`. Peppol scheme code `0183` |
| **VAT** | Value Added Tax — a consumption tax applied in most countries. VAT numbers are commonly used as e-invoicing identifiers across Europe |
| **VeriFactu** | Spain's upcoming mandatory real-time invoice verification system. Replaces the current voluntary system with mandatory reporting for all businesses |
| **Webhook** | An HTTP callback that sends real-time notifications when an event occurs. Light uses webhook to receive invoice status updates (Document Complete, Document Error) |
| **XRechnung** | Germany's mandatory structured XML invoice format for B2G invoices. Based on the EU standard EN 16931 |
| **ZATCA** | *Zakat, Tax and Customs Authority* — Saudi Arabia's tax authority. Operates the Fatoora e-invoicing platform (mandatory for B2B and B2G) |
| **ZUGFeRD** | *Zentraler User Guide des Forums elektronische Rechnung Deutschland* — a hybrid German invoice format that embeds structured XML data inside a PDF. Used alongside XRechnung |

## 5. Key Contacts & Resources

| Role / Resource | Contact / Link |
|---|---|
| E-Invoicing Owner | Tech Partnership (Peter Theisen, Raja Palawija) |
| CS & IMs | Kristine Enkov |
| Linear Team | Integration : Tax & E-invoicing |
| Slack Channel | #e-invoicing |
| Avalara Platform Login | https://vatreturns.avalara.com |
| Light App Settings | https://app.light.inc/settings/integrations |
| Entity Settings | https://app.light.inc/settings/entities |
| Avalara Webhook URL | https://api.light.inc/rest/v1/avalara/webhooks/document-status-change |
| E-Invoicing Setup Video | https://drive.google.com/file/d/1xnstpX-M7MF368sZwT7dZLsxdDCQiikE/view |
