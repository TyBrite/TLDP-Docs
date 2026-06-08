# TLDP-Docs

Documentation for the **TLDP API** (Tybrite Logistics Developer Platform), built
with [Mintlify](https://mintlify.com) and published at
**https://tldp.tybritelabs.com/docs**.

## Structure

```
TLDP-Docs/
├── docs.json                 # Mintlify config (theme + navigation)
├── openapi.yaml              # API spec — drives the API Reference
├── sdk-source/               # Reference copy of the SDK source (read-only)
├── index.mdx                 # Landing
├── quickstart.mdx            # First request, end to end
├── authentication.mdx        # API keys: secret vs publishable, test vs live
├── webhooks.mdx              # Events, payload, signature verification
├── api-reference/
│   └── introduction.mdx      # Conventions + errors (the rest is from openapi.yaml)
└── sdk/
    ├── introduction.mdx       # SDK install + client + idioms
    └── api-reference/classes/ # One page per SDK service
        ├── OrdersService.mdx
        ├── ShipmentsService.mdx
        ├── RatesService.mdx
        ├── TrackingService.mdx
        ├── ProofOfDeliveryService.mdx
        ├── ReturnsService.mdx
        ├── WebhooksService.mdx
        └── SystemService.mdx
```

## Two kinds of reference

- **API Reference** is generated from `openapi.yaml`.
- **TypeScript SDK** pages are handwritten guides for the `@tybrite-labs/tldp-sdk`
  client — examples, return shapes, and idioms.

## Develop locally

Install the [Mintlify CLI](https://www.npmjs.com/package/mint) and preview from
the folder containing `docs.json`:

```bash
npm i -g mint
mint dev          # preview at http://localhost:3000
```
