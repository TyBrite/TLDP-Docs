# TLDP-Docs

The public documentation site for the **TLDP API** (Tybrite Logistics Developer
Platform), published with [Mintlify](https://mintlify.com) at
**https://tldp.tybritelabs.com/docs**.

## Structure

```
TLDP-Docs/
├── docs.json                 # Mintlify config (theme + navigation)
├── openapi.yaml              # API spec — drives the auto-generated API Reference
├── sdk-source/               # Reference copy of the generated SDK src/ (read-only)
├── index.mdx                 # Landing
├── quickstart.mdx            # First request, end to end
├── authentication.mdx        # API keys: secret vs publishable, test vs live
├── webhooks.mdx              # Events, payload, signature verification
├── api-reference/
│   └── introduction.mdx      # Conventions + errors (the rest is from openapi.yaml)
└── sdk/
    ├── introduction.mdx       # SDK install + client + idioms
    └── api-reference/classes/ # HANDWRITTEN, one .mdx per SDK service
        ├── OrdersService.mdx
        ├── ShipmentsService.mdx
        ├── RatesService.mdx
        ├── TrackingService.mdx
        ├── ProofOfDeliveryService.mdx
        ├── ReturnsService.mdx
        ├── WebhooksService.mdx
        └── SystemService.mdx
```

## The two kinds of reference

- **API Reference** (the `API Reference` tab) is **auto-generated** from
  `openapi.yaml`. It updates whenever the spec is recopied here.
- **TypeScript SDK** pages are **handwritten**. They document the SDK's actual
  behavior and idioms — examples, return shapes, and gotchas — and are written
  for external developers (no internal architecture). They must be **updated by
  hand** when the SDK surface changes (a method added/removed/renamed, a param
  or response shape change).

## Keeping in sync

`openapi.yaml` and `sdk-source/` are **copied from the TLDP monorepo** after any
API change. The handwritten SDK pages are then updated by hand. See the TLDP
monorepo's `CLAUDE.md` (the SDK → docs pipeline) and
`tldp-typescript-sdk/MINTLIFY_CONFIGURATION.md` for the full workflow.

## Develop locally

```bash
npm i -g mintlify
mintlify dev      # preview at http://localhost:3000
```
