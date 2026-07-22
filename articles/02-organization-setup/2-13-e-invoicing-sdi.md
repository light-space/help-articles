# Italian SDI e-invoicing

This article explains how to configure Italian SDI e-invoicing in Light. If your company operates in Italy, you can send and receive electronic invoices through the Sistema di Interscambio (SDI) using Light's integration with Invopop.

[Open in Light →](https://app.light.inc/settings/entities)

## What is SDI?

SDI (Sistema di Interscambio) is Italy's mandatory e-invoicing exchange system, operated by the Italian tax authority (Agenzia delle Entrate). Key SDI features:

- **Mandatory in Italy**: Electronic invoicing through SDI is required for B2B, B2G, and most B2C transactions between Italian parties
- **Central Exchange**: Every invoice is transmitted through SDI, which validates it and delivers it to the recipient
- **FatturaPA Format**: Invoices are exchanged as structured XML in Italy's FatturaPA format
- **Codice Destinatario Routing**: SDI delivers incoming invoices based on a recipient code (Codice Destinatario) registered with the tax authority

Light integrates with Invopop to handle SDI submissions and delivery automatically.

> Good to know: SDI is specific to Italy. For cross-border EU e-invoicing, see the [Peppol article](/articles/02-organization-setup/2-7-e-invoicing-peppol).

## Registering your entity with SDI

To enable SDI on an Italian company entity:

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities) and open your Italian entity
2. Make sure the entity's country is set to **Italy** and its **VAT number** (Partita IVA) is filled in — a **Business registration number** (Codice Fiscale) is also recommended
3. In the **E-invoicing** section, click **Add**
4. Select the **Invopop** provider and the **SDI** network (SDI is only offered for Italian entities)
5. Choose a **Registration type**:
   - **Sending and receiving** (default): send invoices to customers and receive supplier invoices in Light
   - **Sending only**: send invoices without routing incoming invoices to Light
6. Click **Next** to start the registration

SDI registration is fully automatic — there is no document verification step. The registration shows as **Processing** and typically completes within about 15 minutes, after which the status changes to **Active**.

> Good to know: Unlike Peppol, SDI does not use an EAS code or e-invoice address, so these fields stay empty on your entity. This is expected.

If a registration fails, the onboarding details show the failure reason. Fix the underlying issue (for example, an invalid Partita IVA) and click **Retry registration** to start again.

## Receiving supplier invoices (Codice Destinatario)

To receive supplier invoices in Light, you must tell the Italian tax authority to route invoices addressed to your company to Invopop by registering Invopop's Codice Destinatario: **JKKZDGR**.

For each Italian entity that should receive invoices:

1. Log in to the [Agenzia delle Entrate portal](https://ivaservizi.agenziaentrate.gov.it/portale/) with valid credentials for the company being registered (SPID, CIE, CNS, or Entratel)
2. Open the **Fatture e Corrispettivi** section
3. In the **Fatturazione elettronica** box, select **Registrazione delle modalità di ricezione della fattura elettronica**
4. Choose the **Codice Destinatario** option and enter the code `JKKZDGR`
5. Confirm with **Conferma**

Once registered, SDI delivers incoming electronic invoices to Invopop, and they appear in Light automatically. Until you complete this registration, incoming invoices keep arriving through your current channel.

> Important: The Codice Destinatario is a routing identifier that tells SDI where to deliver incoming electronic invoices. If you previously registered a different provider's code, registering `JKKZDGR` replaces it — invoices sent to an outdated Codice Destinatario will be rejected, so complete the switch before decommissioning your old channel.

## Best practices

- Register your Italian entities with SDI before issuing production invoices
- For send & receive registrations, complete the Codice Destinatario registration on the Agenzia delle Entrate portal right after the SDI registration turns **Active**
- Keep your entity's Partita IVA and Codice Fiscale up to date — SDI validates them during registration
- Consult your Italian tax advisor or the [Agenzia delle Entrate](https://www.agenziaentrate.gov.it/) for official regulatory requirements

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
