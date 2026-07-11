# InkSoft (inksoft)

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
