# InkSoft (inksoft)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

InkSoft is a custom apparel e-commerce, online store, and design platform for screen printers, embroiderers, and print shops - part of the Inktavo family alongside Printful and GraphicsFlow. It provides hosted online stores, a browser-based Design Studio, product catalogs, art and clip-art libraries, and order management.

InkSoft's developer surface is the **InkSoft API 2** - a per-store, RPC-style HTTP API with predictable, resource-oriented URLs that return data as **XML or JSON** and support **CORS** for client-side web apps. It is used to build custom storefronts, product-catalog pages, design and clip-art galleries, external cart/checkout flows, and single sign-on against a specific InkSoft web store.

## Access Model (read this first)

The InkSoft API 2 **reference is public** - a live reference runs at [demo.inksoft.com/demo?Page=Api2](https://demo.inksoft.com/demo?Page=Api2), with help-center articles and a sample-code repo and wiki at [github.com/InkSoft/api](https://github.com/InkSoft/api). **Production use is account/license-gated**, however:

- API 2 is enabled **per store** from the Manage Web Stores area of the admin portal.
- Access **requires an InkSoft Unlimited license** and is **subject to an additional monthly fee**.
- There is **no self-service developer signup** independent of an InkSoft store subscription.

Because InkSoft does not publish a formal OpenAPI definition, the method names in this catalog are real (taken from InkSoft's public wiki and API 2 reference), but exact request paths, parameters, and payloads beyond those names are **modeled** (`endpointsModeled`). No OpenAPI, AsyncAPI, or Postman collection files are included, to avoid fabricating a surface InkSoft does not itself publish.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/inksoft/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/inksoft/refs/heads/main/apis.yml)

## Tags

- Custom Apparel
- E-commerce
- Online Stores
- Print Shop
- Design Studio
- Screen Printing
- Product Catalog

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

Base URL pattern (per store): `https://stores.inksoft.com/{StoreName}/Api2/`

### InkSoft Stores & Products API

Retrieve a web store's product catalog for building custom catalog and product-detail pages. Documented API 2 methods include `GetProductCategoryList` (all categories and subcategories in a store with cover-art links) and product-list/product-detail calls used to render catalog pages. Requests are scoped to a specific store and return XML or JSON.

- **Reference:** [demo.inksoft.com/demo?Page=Api2](https://demo.inksoft.com/demo?Page=Api2)

### InkSoft Designs & Art API

Browse and search the design and clip-art libraries behind the InkSoft Design Studio. Documented methods include `GetStoreDesignCategoryList`, `GetStoreDesignList`, `GetUserDesignList` (a user's saved designs by UserID), `GetArtCategoryList`, and `GetArtList`. Selected `design_id` and `art_id` values are handed to the Design Studio to load artwork.

- **Reference:** [github.com/InkSoft/api/wiki](https://github.com/InkSoft/api/wiki)

### InkSoft Cart & Orders API

Drive an external cart and checkout flow against an InkSoft store. Documented methods include `GetCart`, `SaveCartItemNotes`, `SaveCartShippingAddress`, `SaveCartBillingAddress`, `GetCartShippingAddresses`, `GetCartShippingMethods`, `GetCartPaymentMethods`, and `SaveCartOrder` (place the order given a payment type and cart total).

- **Reference:** [github.com/InkSoft/api/wiki](https://github.com/InkSoft/api/wiki)

### InkSoft Users & SSO API

Provision and link InkSoft user accounts for single sign-on. The documented `CreateUser` method creates an InkSoft account alongside your own user record and returns an InkSoft UserID, which you pass to the Design Studio so saved art and designs attach to that account.

- **Reference:** [github.com/InkSoft/api/wiki](https://github.com/InkSoft/api/wiki)

## Common Properties

- [GitHub Organization](https://github.com/InkSoft)
- [LinkedIn](https://www.linkedin.com/company/inksoft)
- [Website](https://www.inksoft.com)
- [Documentation](https://help.inksoft.com/hc/en-us/categories/8146540560795-InkSoft-API)
- [API Reference](https://demo.inksoft.com/demo?Page=Api2)
- [Plans](plans/inksoft-plans-pricing.yml)
- [Rate Limits](rate-limits/inksoft-rate-limits.yml)
- [Fin Ops](finops/inksoft-finops.yml)
- [Blog](https://www.inksoft.com/blog/)

## WebSocket Review

InkSoft does **not** expose a documented public WebSocket API. The InkSoft API 2 is entirely request/response HTTP (XML/JSON over HTTPS). See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
