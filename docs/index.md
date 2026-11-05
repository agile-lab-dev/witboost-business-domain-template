# Business Domain Template — Usage Guide

Use this template to register a **Business Domain** in the Witboost catalog. Business Domains represent organisational or functional areas of your company (e.g. Finance, HR, Supply Chain). Data Products are always created inside a domain, so domains must exist before creating data products.

Domains can also be nested: a **Business Domain** can be declared as a sub-domain of a broader domain (called a **Business Field**).

---

## Step 1 — Domain Details

Fill in the fields below to describe your domain.

| Field | Required | Description |
|---|---|---|
| **Name** | Yes | Human-readable name for the domain (e.g. `Customer Analytics`). |
| **Description** | | A clear explanation of what functional area this domain covers, its purpose, and any relevant business context. |
| **Domain Owner** | Yes | The person accountable for this domain. Select a user from the catalog. |
| **Is Subdomain of** | | If this domain belongs to a broader domain, select the parent domain here. Leave blank for top-level domains. |

### Example

| Field | Example value |
|---|---|
| **Name** | `Customer Analytics` |
| **Description** | `Covers all analytics initiatives related to customer behaviour, segmentation, and lifetime value.` |
| **Domain Owner** | `user:jane.doe_mycompany.com` |
| **Is Subdomain of** | _(leave blank for a top-level domain)_ |

---

## Repository Details

The template generates the shared GitLab repository URL automatically, targeting `business-domains` in the configured organisation's business-domains group. Replace `{{orgname}}` in both repository URL expressions when configuring the template for your organisation. A missing repository is created by the publish action.

Each domain is stored at `domains/<normalized-name>/catalog-info.yaml`. For example, `Customer Analytics` is stored at `domains/customeranalytics/catalog-info.yaml`. Normalization removes non-word characters and lowercases the name, matching the catalog entity name.

This template requires Witboost version 2.11.5+ in order to work.

## What happens after you click Create?

1. The catalog descriptor is published to the domain's directory in the shared repository without removing unrelated files.
2. The entity is registered in the Witboost catalog and immediately visible under **Domains**.
3. You can start creating Data Products inside the new domain right away.
