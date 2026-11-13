# Awesome Agentic Commerce [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for agentic commerce protocols: UCP, ACP, AP2, MPP, AMP, A2A, MCP, and WebMCP

This repository is a **reference point** to official resources. It does not own or maintain these protocols. For authoritative information, always consult the official documentation.

Contributions are welcome — please read [CONTRIBUTING.md](./CONTRIBUTING.md) first. In short: this list indexes protocols, not products built on them, and corrections are the most valuable contribution you can make.

Protocol versions and selected status claims were checked on **November 13, 2026**. See the [curation audit](./RESEARCH-2026-11-13.md) for sources and verification limits; dated announcements describe availability at publication, not necessarily current deployment support.

## Contents

- [What is Agentic Commerce?](#what-is-agentic-commerce)
- [Standards Bodies & Governance](#standards-bodies--governance)
- [UCP - Universal Commerce Protocol](#ucp---universal-commerce-protocol)
- [ACP - Agentic Commerce Protocol](#acp---agentic-commerce-protocol)
- [AP2 - Agent Payments Protocol](#ap2---agent-payments-protocol)
- [MPP - Machine Payments Protocol](#mpp---machine-payments-protocol)
- [AMP - Agentic Mobile Protocol](#amp---agentic-mobile-protocol)
- [A2A - Agent2Agent Protocol](#a2a---agent2agent-protocol)
- [MCP - Model Context Protocol](#mcp---model-context-protocol)
- [WebMCP - Browser-Native Agent Tools](#webmcp---browser-native-agent-tools)
- [Web Bot Auth](#web-bot-auth)
- [How They Relate](#how-they-relate)
- [Crypto Payment Rails](#crypto-payment-rails)
- [Fiat Payment Rails](#fiat-payment-rails)
- [Integration & Orchestration Layer](#integration--orchestration-layer)
- [Tools & Plugins](#tools--plugins)
- [Developer Tools](#developer-tools)
- [Related Technologies](#related-technologies)
- [Learning Resources](#learning-resources)
  - [Platform Announcements](#-platform-announcements)
- [Market Sizing](#market-sizing)
- [Regulatory Landscape](#regulatory-landscape)
- [Community Resources](#community-resources)
- [Adopters & Partners](#adopters--partners)
- [Contributing](#contributing)

<br>

## What is Agentic Commerce?

Agentic commerce is the emerging paradigm where AI agents act on behalf of users to discover products, compare options, and complete purchases. Instead of humans clicking "buy" buttons on websites, AI assistants like ChatGPT, Gemini, or Copilot can browse catalogs, compare prices, and execute transactions autonomously.

**The Challenge:** Traditional e-commerce assumes a human is directly interacting with a website. When an AI agent acts on behalf of a user, new questions arise:
- How does a merchant know the agent is authorized to buy?
- How can agents from different platforms communicate?
- How do you prove the user actually wanted this purchase?

**The Building Blocks:** Complementary protocols cover commerce (UCP, ACP), authorization evidence (AP2, Verifiable Intent), payment exchange (MPP, x402, L402), mobile wallet payments (AMP), agent communication (A2A), tools (MCP, WebMCP), and client identity ([Web Bot Auth](#web-bot-auth)). These are composable options; a purchase does not have to traverse every protocol.

<br>

## Standards Bodies & Governance

> Governance sources and selected standards updates, November 2026

Governance differs by project. Foundation membership, contribution to a standards body, and maintenance of a reference implementation are distinct relationships; contribution does not itself make a draft a completed standard.

| Body | Hosts | Notes |
|------|-------|-------|
| **Agentic AI Foundation (AAIF)** — Linux Foundation | MCP, A2A, goose, AGENTS.md | Formed December 9, 2025. Platinum members: AWS, Anthropic, Block, Bloomberg, Cloudflare, Google, Microsoft, OpenAI. Runs an **Agentic Commerce working group**. |
| **x402 Foundation** — Linux Foundation | x402 | Announced April 2, 2026 at MCP Dev Summit NA; operational launch July 14, 2026 with 40 founding members (17 premier, incl. Visa, Stripe, Solana Foundation). |
| **FIDO Alliance** | Standards work drawing on AP2 and Verifiable Intent | Agentic Authentication TWG and Payments TWG; the Verifiable Intent reference repository remains maintained by Mastercard and labeled Draft v0.1. |
| **UCP Governing Council** | UCP | Google, Shopify, Stripe as permanent members plus elected open seats; Technical Committee (16 seats) and per-vertical Domain Technical Councils. |
| **OpenAI + Stripe + Meta** | ACP | Lead maintainers listed in [MAINTAINERS.md](https://raw.githubusercontent.com/agentic-commerce-protocol/agentic-commerce-protocol/7fdd78df677a94dce04c770644b0fbbb1401272b/MAINTAINERS.md); the upstream README still names only OpenAI and Stripe. |
| **EMVCo** | Agentic Payments – Framework for Specifications | Draft framework introducing Intent Services; the November 10 update reports public-review feedback being considered, not a completed standard. |

### 🎖️ Official Resources

- [Agentic AI Foundation](https://aaif.io/) - AAIF projects and working groups
- [AAIF Formation Announcement](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation) - Linux Foundation, December 2025
- [x402 Foundation Operational Launch](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications) - Linux Foundation, July 14, 2026
- [FIDO Alliance: Trusted AI Agent Interactions](https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/) - Working group formation
- [Building the Trust Layer with AP2 and Verifiable Intent](https://fidoalliance.org/building-the-trust-layer-for-agentic-payments-with-ap2-and-verifiable-intent/) - FIDO Alliance
- [EMVCo Agentic Payments Framework](https://www.emvco.com/news-publications/emvco-requests-feedback-on-framework-for-secure-interoperable-and-scalable-card-based-agentic-payments/) - September 1, 2026 announcement of the draft and public review
- [EMVCo November Framework Update](https://www.emvco.com/news-publications/advancing-secure-agentic-payments-highlights-from-the-emvco-hanoi-board-of-advisors-meeting/) - November 10, 2026 update on feedback and potential specifications
- [Building Trust in Agentic Commerce](https://newsroom.bankofamerica.com/content/newsroom/press-releases/2026/09/global-banks-collaborate-on-principles-for-trusted-agentic-comme.html) - September 22, 2026 industry principles from ASB, Bank of America, Capital One, Commonwealth Bank, ING, and NatWest; not regulation or a protocol specification

<br>

## UCP - Universal Commerce Protocol

> End-to-end commerce standard for AI agent transactions

**Governance:** UCP Governing Council — see [official announcements](https://ucp.dev/documentation/announcements/) for council membership and the [repository](https://github.com/Universal-Commerce-Protocol/ucp) for project roles
**Latest release:** [v2026-08-25](https://github.com/Universal-Commerce-Protocol/ucp/releases/tag/v2026-08-25) — multi-vertical refactor, vendor-neutral 3DS2, payment schedules; [release history](https://github.com/Universal-Commerce-Protocol/ucp/releases) checked November 13, 2026
**Cadence:** quarterly releases (agreed by the Technical Council, July 2026)

### What is UCP?

UCP is "the common language for platforms, agents, and businesses." It defines building blocks for the entire commerce journey—from product discovery to checkout to order tracking—through a single, standardized interface.

**Key Concepts:**
- **Checkout** - Unified checkout sessions supporting complex cart logic, dynamic pricing, and tax calculations
- **Identity Linking** - OAuth 2.0-based secure connections between agents and user accounts (loyalty programs, saved addresses)
- **Order Management** - Real-time webhooks for shipment tracking, returns, and post-purchase updates

**Why it matters:** Without UCP, every agent platform would need custom integrations with every merchant (N×N problem). UCP collapses this into a single standard that any agent can use with any UCP-enabled merchant.

### 🆕 What Changed in v2026-08-25

The August 2026 release is the point where UCP stopped being shopping-shaped and became a general commerce protocol. It carries **breaking changes** — treat it as a migration, not a bump.

**Breaking:**
- **Payment moved out of `shopping` into `common`** — `split_payments`, `payment_terms`, and `ap2_mandates` now live under `dev.ucp.common.payment.*`
- **Spec reorganized into domain verticals**, with shared primitives under `common/types/`
- **Buyer consent restructured** from fixed booleans into a dynamic map keyed by reverse-DNS identifiers (`dev.ucp.consent.*`) returning `consent_purpose` objects
- **`signing_keys[]` removed**; `keys[]` (JWK Set) is now the sole canonical signing key field
- **Fulfillment schema restructured** — `allows_` prefixes dropped, `multi_destination` remodeled from map to array, `fulfillment_option.description` upgraded to a structured object
- **Fractional quantities** — `quantity` is now `anyOf` integer or a structured `measure.json` object, with sale-basis pricing steps
- **Structured request constraints** — static schemas replaced by response-carried `$requestConstraints` with JSONPath targeting

**New capabilities:**
- **Actions primitive** — a horizontal `actions[]` array for out-of-band requests such as authentication
- **Vendor-agnostic 3D Secure (3DS2)** — Device Data Collection and Challenge flows, no vendor lock-in
- **Location search & lookup** — physical store search with geocoding, plus standardized operating hours with timezone handling
- **Payment schedules** — deferred payments, deposits, installments
- **Split payments** — multi-instrument checkout
- **Capability versioning** — formal date-based versioning and forward-compatibility guidelines

### 🏛️ Governance & Domain Councils

UCP expanded from a single spec into a multi-vertical program with dedicated councils:

| Council | Formed | Inaugural Members |
|---------|--------|-------------------|
| **Food** | July 16, 2026 | Block (Square), DoorDash, Google, Toast, Uber Eats |
| **Lodging** | August 11, 2026 | Amadeus, Booking.com, Expedia, Google, Hilton, Marriott, Trip.com |
| **Payments** | September 2, 2026 | Adyen, Ant International, Coinbase, Global Payments, Google, PayPal, Shopify, Stripe |

- **Governing Council** — Stripe joined as a permanent member (April 28, 2026) alongside Google and Shopify, plus two elected open seats
- **Technical Committee** — expanded to 16 seats, adding Amazon, Meta, Microsoft, Salesforce, and Stripe

- [UCP Announcements](https://ucp.dev/documentation/announcements/) - Council formations and release notices

### 📊 Adoption Signal

The [UCP Checker August 2026 report](https://ucpchecker.com/blog/state-of-agentic-commerce-august-2026) is a dated, independent crawler snapshot of discoverable storefronts and declared capabilities. Its findings about platform concentration and MCP coverage apply to that sample. Endpoint discovery does not establish active checkout usage, completed purchases, or current market-wide adoption.

### 🎖️ Official Resources

- [UCP Documentation](https://ucp.dev/) - Protocol overview and guides
- [UCP GitHub](https://github.com/Universal-Commerce-Protocol/ucp) - Specification and source
- [UCP Specification](https://ucp.dev/specification/overview/) - Technical spec
- [UCP Playground](https://ucp.dev/latest/specification/shopping/playground/) - Interactive testing
- [UCP Roadmap](https://ucp.dev/documentation/roadmap/) - Development roadmap
- [UCP Core Concepts](https://ucp.dev/documentation/core-concepts/) - Foundational model
- [UCP and AP2](https://ucp.dev/documentation/ucp-and-ap2/) - How UCP uses AP2 for payment authorization
- [UCP Versioning](https://ucp.dev/versioning/) - Version and capability-versioning policy
- [Schema Authoring](https://ucp.dev/documentation/schema-authoring/) - Writing UCP schemas
- [Stripe UCP Integration](https://docs.stripe.com/agentic-commerce/protocols/ucp) - Stripe's UCP integration documentation

### 🔌 Tools & Plugins

- [UCP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/ucp-agentic-commerce) - Claude Code plugin for UCP development

### 🏪 Google Merchant Integration

**Implementation version:** Google's native-checkout guide resolves to the **`2026-04-08`** implementation reference, checked November 13, 2026. Build to the version and capabilities documented for the particular Google surface; the current UCP release does not establish support for every August capability in that integration.

- [Google Merchant UCP Guide](https://developers.google.com/merchant/ucp) - Google integration docs
- [Native Checkout Guide](https://developers.google.com/merchant/ucp/implementation/2026-04-08/native-checkout-api) - Google's versioned native checkout implementation
- [Embedded Checkout Guide](https://developers.google.com/merchant/ucp/guides/checkout/embedded) - Embedded checkout implementation
- [UCP FAQ](https://developers.google.com/merchant/ucp/faq) - Frequently asked questions

### 🐍 SDKs & Implementations

- [UCP Samples](https://github.com/Universal-Commerce-Protocol/samples) - Reference implementations
- [UCP Python SDK](https://github.com/Universal-Commerce-Protocol/python-sdk) - Official Python SDK
- [UCP Conformance Tests](https://github.com/Universal-Commerce-Protocol/conformance) - Compliance testing
- [Shopify UCP](https://shopify.engineering/ucp) - Shopify's implementation
- [Shopify Agent Docs](https://shopify.dev/docs/agents) - Shopify agent integration
- [Shopify UCP Buyer Consent](https://shopify.dev/changelog/posts/checkout-mcp-and-cart-mcp-now-support-ucp-buyer-consent) - October 16, 2026 support for `dev.ucp.shopping.buyer_consent` in Checkout MCP and Cart MCP on UCP `2026-08-25`
- [Shopify UCP Location Search and Lookup](https://shopify.dev/changelog/posts/discover-a-merchant-s-retail-stores-with-ucp-location-search-and-lookup) - October 22, 2026 store discovery; checkout for pickup at the selected location is not supported
- [Shopify UCP Permalinks](https://shopify.dev/changelog/posts/cart-and-checkout-permalinks-now-support-ucp-at-buy) - October 28, 2026 support for `dev.ucp.shopping.permalink` at the `/buy` endpoint

### 📰 Announcements

- [Under the Hood: UCP](https://developers.googleblog.com/under-the-hood-universal-commerce-protocol-ucp/) - Google Developers Blog
- [Agentic Commerce Tools](https://blog.google/products/ads-commerce/agentic-commerce-ai-tools-protocol-retailers-platforms/) - Google Blog
- [Shopify: AI Commerce at Scale](https://www.shopify.com/news/ai-commerce-at-scale) - Shopify announcement
- [Gemini Enterprise for CX](https://cloud.google.com/transform/a-new-era-agentic-commerce-retail-ai) - Google Cloud agentic retail platform
- [NRF 2026: The AI Platform Shift](https://blog.google/company-news/inside-google/message-ceo/nrf-2026-remarks/) - Google CEO remarks at NRF 2026
- [Open Rails for Agentic Commerce at OSS NA 2026](https://opensource.googleblog.com/2026/06/open-rails-for-agentic-commerce-at-open-source-summit-north-america-2026.html) - Google Open Source Blog, June 2026 — UCP keynote at Open Source Summit North America
- [Shopify Spring '26 Edition: Agentic Commerce for Every Developer](https://www.shopify.com/news/spring-26-edition-dev) - June 2026 — UCP access opens to all developers; agent profiles self-register in the Developer Dashboard against a public MCP endpoint, no approval gate
- [UCP v2026-08-25 Release Notes](https://github.com/Universal-Commerce-Protocol/ucp/releases/tag/v2026-08-25) - Full changelog for the August release
- [SEJ: UCP Releases Spec Update With Schema Changes](https://www.searchenginejournal.com/ucp-releases-spec-update-with-schema-changes/587590/) - Coverage of the August schema changes

<br>

## ACP - Agentic Commerce Protocol

> Open standard for programmatic commerce between AI agents and businesses

**Maintainers:** OpenAI, Stripe, Meta — per the [lead maintainer file](https://raw.githubusercontent.com/agentic-commerce-protocol/agentic-commerce-protocol/7fdd78df677a94dce04c770644b0fbbb1401272b/MAINTAINERS.md); the upstream README still names only OpenAI and Stripe
**Latest published snapshot:** `2026-04-17` (beta; cart, feed, orders, authentication, MCP compatibility) — [spec directory](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/tree/main/spec) checked November 13, 2026; proposed work also sits in `unreleased/`
**Status:** Beta, Apache 2.0, date-based versioning

### What is ACP?

ACP defines interfaces for agent-assisted commerce, including checkout, product feeds, and delegated payments. It initially powered ChatGPT's Instant Checkout experience. OpenAI's March 2026 product update shifted emphasis toward discovery and merchant-controlled checkout; that product change does not remove the protocol's checkout specification.

**Key Concepts:**
- **Shared Payment Token (SPT)** - A secure, one-time-use token that lets agents initiate payments without ever seeing the user's card number. The token is scoped to a specific merchant and cart total.
- **Agentic Checkout** - A REST API with an optional MCP binding; the [checkout schema](https://raw.githubusercontent.com/agentic-commerce-protocol/agentic-commerce-protocol/7fdd78df677a94dce04c770644b0fbbb1401272b/spec/2026-04-17/openapi/openapi.agentic_checkout.yaml) defines five operations across four paths: create, update, retrieve, complete, and cancel
- **Delegated Payment** - The flow where Stripe (or another PSP) issues an SPT, and the agent passes it to the merchant to complete the transaction

**Why it matters:** Delegated payment tokens reduce the agent's exposure to raw card credentials. Tokenization alone does not establish an integration's PCI compliance; responsibilities depend on the payment flow and systems involved.

### 📌 Current Status (November 13, 2026)

Keep published specifications, repository work, and platform product availability separate:

- **Latest published snapshot remains `2026-04-17`.** Dated spec directories are `2025-09-29`, `2025-12-12`, `2026-01-16`, `2026-01-30`, `2026-04-17`. Proposed work is staged in `unreleased/`.
- **OpenAI changed the checkout experience.** Its [March 24 announcement](https://openai.com/index/powering-product-discovery-in-chatgpt/) describes expanding ACP for product discovery and connecting users to merchant-owned checkout. It does not quantify Instant Checkout sales or establish that ACP is now discovery-only.
- **Meta integration is separately documented.** [Stripe's Facebook checkout announcement](https://stripe.com/newsroom/news/checkout-for-facebook) describes that integration; it does not establish that every Meta shopping surface uses ACP.
- ⚠️ **Naming collision to watch:** the widely-cited "2026-07-28" release is the **MCP** specification, *not* ACP. Several secondary sources conflate the two.

### 🎖️ Official Resources

- [Agentic Commerce Portal](https://www.agenticcommerce.dev/) - Main hub
- [ACP GitHub](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol) - Draft spec and examples
- [OpenAI Commerce Docs](https://developers.openai.com/commerce/) - OpenAI documentation
- [Stripe Agentic Commerce Documentation](https://docs.stripe.com/agentic-commerce) - Stripe's integration overview across supported protocols

### 🔌 Tools & Plugins

- [ACP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/acp-agentic-commerce) - Claude Code plugin for ACP development

### 📋 Specifications

All OpenAPI specs below are from the latest published snapshot, `2026-04-17`; the protocol remains beta.

- [Spec Directory (all versions)](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/tree/main/spec) - Every dated snapshot plus `unreleased/`
- [Agentic Checkout Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.agentic_checkout.yaml) - Checkout OpenAPI spec
- [Agentic Checkout Webhook Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.agentic_checkout_webhook.yaml) - Webhook events
- [Cart Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.cart.yaml) - Cart OpenAPI spec
- [Feed Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.feed.yaml) - Product feed OpenAPI spec
- [Delegated Payment Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.delegate_payment.yaml) - Payment OpenAPI spec
- [Delegated Authentication Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.delegate_authentication.yaml) - Authentication OpenAPI spec
- [MCP Binding](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/docs/mcp-binding.md) - How ACP maps onto MCP
- [Governance Model](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/docs/governance.md) - Protocol governance
- [Operating Model](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/docs/operating-model.md) - How the spec is developed
- [SEP Guidelines](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/docs/sep-guidelines.md) - Spec Enhancement Proposal process

### 🛍️ For Merchants

- [Get Started Guide](https://developers.openai.com/commerce/guides/get-started/) - Implementation guide
- [Key Concepts](https://developers.openai.com/commerce/guides/key-concepts/) - Core concepts
- [Production Readiness](https://developers.openai.com/commerce/guides/production/) - Production deployment
- [ChatGPT Merchant Program](https://chatgpt.com/merchants) - Join ChatGPT marketplace

### 📰 Announcements

- [Buy it in ChatGPT](https://openai.com/index/buy-it-in-chatgpt/) - OpenAI announcement
- [Stripe Instant Checkout](https://stripe.com/newsroom/news/stripe-openai-instant-checkout) - Stripe announcement
- [Developing an Open Standard](https://stripe.com/blog/developing-an-open-standard-for-agentic-commerce) - Stripe Blog
- [Stripe Commerce Solutions](https://stripe.com/blog/introducing-our-agentic-commerce-solutions) - Stripe solutions
- [Powering Product Discovery in ChatGPT](https://openai.com/index/powering-product-discovery-in-chatgpt/) - OpenAI's pivot from Instant Checkout to merchant-controlled checkout, March 2026
- [Stripe: Checkout for Facebook](https://stripe.com/newsroom/news/checkout-for-facebook) - Meta native checkout powered by Stripe over ACP

<br>

## AP2 - Agent Payments Protocol

> Secure payment authorization for agent-led transactions using cryptographic mandates

**Maintainers:** FIDO Alliance (donated by Google, April 2026)
**Ecosystem:** See [official project documentation](https://ap2-protocol.org/) for participants and implementation resources
**Latest version:** v0.2.0, released April 28, 2026 (introduces "Human Not Present" autonomous payments) — [changelog](https://github.com/google-agentic-commerce/AP2/blob/main/CHANGELOG.md) checked November 13, 2026
**Standardization:** Work through the FIDO Agentic Authentication TWG and Payments TWG is distinct from the repository's release history
**Roadmap:** Digital wallets, push payment methods (UPI, PIX), digital currencies

### What is AP2?

AP2 models how payment participants verify authorization when an agent makes a purchase, including when the user is absent.

AP2 introduces **Mandates**: cryptographically signed, tamper-evident records of authorization. A valid signature verifies the signed record; it does not guarantee that a system correctly interpreted the user's wishes.

> ⚠️ **Terminology change (2026):** what earlier documentation called the **Cart Mandate** is now the **Checkout Mandate**. The spec site was reorganized under `/ap2/*` paths and older `/topics/*` and `/specification/` URLs no longer resolve. Material written before mid-2026 — including most tutorials — still uses the old names.

**Key Concepts:**
- **Checkout Mandate** *(formerly Cart Mandate)* - Authorizes checkout completion; its closed form includes a merchant-signed Checkout object
- **Payment Mandate** - Authorizes payment for the checkout and carries payment details or constraints for verification by payment participants
- **Open and Closed Mandates** - Both mandate types have open and closed forms: open mandates express constraints for later execution, while closed mandates bind concrete checkout or payment details. The current model has two primary types, not a third Intent Mandate type
- **Agent Authorization Framework** - A distinct specification section covering how an agent's authority is established and verified.

**Roles:** Shopping Agent (discovery, checkout construction, execution) · Credential Provider (sources credentials, verifies agent authorization) · Merchant (catalog, fulfillment) · Merchant Payment Processor · **Trusted Surface** (the UI that obtains user consent before a mandate is created) · Network and Issuer.

**Positioning:** AP2 now describes itself as an extension for **A2A, MCP, and UCP** — the explicit UCP alignment is newer than the original framing.

**Why it matters:** Mandates provide evidence that payment participants can verify against authorization constraints. They support audit and dispute handling without independently determining legal liability. See the [mandate model](https://ap2-protocol.org/ap2/specification/).

### 🎖️ Official Resources

- [AP2 Documentation](https://ap2-protocol.org/) - Protocol overview
- [AP2 Executive Summary](https://ap2-protocol.org/overview/) - Roles, mandates, and model
- [AP2 GitHub](https://github.com/google-agentic-commerce/AP2) - Samples and demos
- [AP2 Specification](https://ap2-protocol.org/ap2/specification/) - Technical spec

### 🔌 Tools & Plugins

- [AP2 Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/ap2-agentic-payments) - Claude Code plugin for AP2 development

### 📚 Key Topics

- [Agent Authorization Framework](https://ap2-protocol.org/ap2/agent_authorization/) - How agent authority is established and verified
- [Flows](https://ap2-protocol.org/ap2/flows/) - Human-present and human-not-present transaction flows
- [Checkout Mandate](https://ap2-protocol.org/ap2/checkout_mandate/) - Authorizing checkout completion (formerly Cart Mandate)
- [Payment Mandate](https://ap2-protocol.org/ap2/payment_mandate/) - Open and closed payment authorization, including recurrence and budget constraints
- [Security and Privacy Considerations](https://ap2-protocol.org/ap2/security_and_privacy_considerations/) - Security model
- [Implementation Considerations](https://ap2-protocol.org/ap2/implementation_considerations/) - Practical guidance
- [FAQ](https://ap2-protocol.org/faq/) - Common questions
- [Glossary](https://ap2-protocol.org/glossary/) - Terminology

### 💻 Code Samples

> The repository was reorganized in 2026: `samples/` moved under `code/`, and an SDK and web client were added.

- [Code Samples](https://github.com/google-agentic-commerce/AP2/tree/main/code/samples) - Human-present and human-not-present flows, cards and x402 variants, Android digital payment credentials
- [AP2 SDK](https://github.com/google-agentic-commerce/AP2/tree/main/code/sdk) - Reference SDK
- [Web Client](https://github.com/google-agentic-commerce/AP2/tree/main/code/web-client) - Browser reference client
- [CHANGELOG](https://github.com/google-agentic-commerce/AP2/blob/main/CHANGELOG.md) - Authoritative version history

### 📰 Announcements

- [Announcing AP2](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol) - Google Cloud Blog
- [Google Donates AP2 to FIDO Alliance](https://blog.google/products-and-platforms/platforms/google-pay/agent-payments-protocol-fido-alliance/) - April 2026, also announces v0.2 with "Human Not Present" flow
- [FIDO Alliance Forms Agentic Standards Working Groups](https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/) - April 28, 2026 — New **Agentic Authentication TWG** (chaired by CVS Health, Google, OpenAI; vice-chaired by Amazon, Google, Okta) and existing **Payments TWG** (chaired by Mastercard, Visa) will develop interoperable standards from AP2 + Mastercard's Verifiable Intent
- [PYMNTS: Google + Mastercard Contribute to FIDO](https://www.pymnts.com/artificial-intelligence-2/2026/google-and-mastercard-contribute-agentic-commerce-standards-to-fido-alliance/) - Industry coverage of the contributions

<br>

## MPP - Machine Payments Protocol

> Open standard for autonomous agent micropayments

**Co-Authors:** Stripe, Tempo
**Launched:** March 18, 2026, alongside Tempo mainnet
**Documentation:** [mpp.dev](https://mpp.dev); [specification index](https://paymentauth.org/) — checked November 13, 2026

### What is MPP?

MPP is an open, HTTP-native standard for autonomous agent micropayments. A server answers an unpaid request with HTTP `402` and payment requirements; the agent authorizes, retries, and receives the resource plus a receipt. It introduces a **sessions primitive** that allows AI agents to initiate, manage, and settle small-value transactions without human intervention at each step.

**Key Concepts:**
- **Sessions** - A primitive that bundles multiple micropayments into a single authorized context, reducing friction for high-frequency agent transactions
- **Streaming payments** - Added as a first-class primitive at Stripe Sessions 2026 (April 29–30). Bills per-token, per-second, or per-call usage in real time against a stablecoin balance
- **Micropayments** - Designed for small-value, high-volume payments typical of agent-to-agent and agent-to-service interactions
- **Payment Methods** - A method-independent HTTP authentication framework with separate specifications for methods including card, Stripe, Tempo, and Lightning; credential mechanisms and limits depend on the method and implementation

**Relationship to x402:** Both define payment exchanges over HTTP. MPP's cryptographic mechanisms depend on its [payment method](https://paymentauth.org/), so EIP-3009 or Permit2 is not a universal MPP substrate. x402 also documents [usage-based charging](https://docs.x402.org/schemes/upto) and [batch settlement](https://docs.x402.org/schemes/batch-settlement); compare specific methods, schemes, and SDK support rather than attributing those capabilities exclusively to MPP.

**Why it matters:** As AI agents consume paid APIs, purchase digital goods, and transact with other agents autonomously, traditional checkout flows break down. MPP provides a purpose-built payment layer for machine-to-machine commerce at scale.

### 🎖️ Official Resources

- [MPP Protocol Site](https://mpp.dev) - Official documentation and implementation guides
- [MPP Specifications](https://paymentauth.org/) - Payment authentication, payment methods, discovery, and transport drafts
- [Payment HTTP Authentication Draft](https://paymentauth.org/draft-httpauth-payment-01.html) - Method-independent HTTP payment authentication
- [MPP SDKs](https://mpp.dev/sdk) - TypeScript, Python, Rust, Go, and Ruby SDKs with a feature-support matrix
- [MPP Expanded Identity Primitives](https://mpp.dev/blog/expanded-identity-primitives) - November 11, 2026 SDK update for optional identity verification alongside the core payment flow
- [Stripe Blog: Introducing MPP](https://stripe.com/blog/machine-payments-protocol) - Launch announcement
- [MPP Stripe Docs](https://docs.stripe.com/payments/machine/mpp) - Integration documentation
- [Machine Payments Sample App](https://github.com/stripe-samples/machine-payments) - Complete reference implementation
- [`mppx` CLI](https://www.npmjs.com/package/mppx) - Server SDK and `mppx validate` conformance checker
- [Visa Card Spec & SDK for MPP](https://corporate.visa.com/en/sites/visa-perspectives/innovation/visa-card-specification-sdk-for-machine-payments-protocol.html) - Visa card specification and SDK

### 🔌 Tools & Plugins

- [MPP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/stripe-mpp) - Claude Code plugin for MPP development

### 📰 Announcements

- [Fortune: Tempo Blockchain + MPP Launch](https://fortune.com/2026/03/18/stripe-tempo-paradigm-mpp-ai-payments-protocol/) - Stripe and Tempo partnership
- [PYMNTS: Visa Scales via MPP](https://www.pymnts.com/visa/2026/visa-scales-agentic-commerce-through-stripe-protocol-collaboration/) - Visa scaling through MPP collaboration
- [Everything We Announced at Sessions 2026](https://stripe.com/blog/everything-we-announced-at-sessions-2026) - Stripe, April 2026 — streaming payments added to MPP
- [Machine Payments and the Protocols Behind Agentic Commerce](https://stripe.com/sessions/2026/machine-payments-and-the) - Stripe Sessions 2026 talk
- [Forrester: Why MPP Signals a Turning Point for Micropayments](https://www.forrester.com/blogs/why-stripes-machine-payments-protocol-signals-a-turning-point-for-micropayments) - Analyst perspective

<br>

## AMP - Agentic Mobile Protocol

> Open-source mobile-first agentic payment framework for digital wallets, super apps, and wearables

**Maintainers:** Ant International (Alipay+ ecosystem)
**Launched:** April 2026 — **Phase I rollout live September 2026**

### What is AMP?

AMP is an agentic payment framework for mobile interfaces, digital wallets, and super apps. Its reference implementation includes mandate-chain libraries and examples for human-present and autonomous payments.

**Key Concepts:**
- **KYA (Know Your Agent) Framework** - Establishes an agent's digital identity and certifies its authorized capabilities, parallel to KYC for humans
- **Agent Trust Rating** - Dynamic risk-management score that determines an agent's trustworthiness and controls its level of autonomy
- **Money-back Guarantee** - Launch materials describe refund protection for payment partners in account-takeover cases; consult the applicable program terms for coverage
- **Cross-device Compatibility** - Designed for non-card form factors absent from traditional payment rails

**Why it matters:** The Alipay+ network reaches 1.8B user accounts and 150M merchants globally — primarily across APAC. AMP gives this footprint an agentic-commerce layer and complements card-based protocols (Visa TAP, Mastercard Agent Pay) for emerging markets where mobile wallets dominate.

### 🎖️ Official Resources

- [AMP GitHub](https://github.com/ant-intl/AMP) - Official protocol documentation, Python libraries, tests, and human-present and autonomous payment samples

### 🚀 Phase I Rollout (September 2026)

AMP moved from announcement to production in September 2026:

- **10 Alipay+ digital wallets** live, together serving ~1.5B user accounts
- **7 acquiring partners**: Adyen, Allinpay, Checkout.com, Fiserv, Global Payments, Nuvei, Worldline
- Ant International also joined the **UCP Payments Technical Council** (September 2, 2026) and the **KYA interoperability collaboration** with Mastercard and Visa — see [Cross-Network Interoperability](#-cross-network-interoperability-kya)

### 📰 Announcements

- [Ant International Launches AMP](https://www.businesswire.com/news/home/20260427209524/en/Ant-International-Launches-Open-Sourced-Agentic-Mobile-Protocol-to-Drive-AI-Commerce) - BusinessWire, April 27, 2026
- [PYMNTS: Agentic AI Gets Its Own Payment Protocol](https://www.pymnts.com/artificial-intelligence-2/2026/agentic-ai-gets-its-own-payment-protocol/) - Industry coverage, April 30, 2026
- [AMP Rolls Out Globally with Wallets and Acquirers](https://www.aol.com/articles/ant-internationals-agentic-mobile-protocol-032600000.html) - September 11, 2026 — Phase I rollout plus KYA collaboration with Mastercard and Visa

<br>

## A2A - Agent2Agent Protocol

> Open standard for AI agent interoperability and communication

**Maintainers:** Agentic AI Foundation (Linux Foundation) — Growth Stage project since August 27, 2026; originally created by Google
**Latest version:** [v1.0.1](https://github.com/a2aproject/A2A/releases) — GitHub publication May 28, 2026, embedded changelog dated May 26; checked November 13, 2026. v1.0.0 was released March 12, 2026
**Backing:** 150+ organizations; adopted across Google Cloud, AWS, and Microsoft Azure

### What is A2A?

A2A enables AI agents built on different frameworks, by different companies, running on separate servers to discover each other's capabilities and collaborate on tasks—**as agents, not just as tools.**

Think of it as the "common language" that lets a travel planning agent talk to a flight booking agent, a hotel agent, and a car rental agent to coordinate a complete trip.

**Key Concepts:**
- **Agent Card** - A JSON document that agents publish describing who they are, what they can do, and how to communicate with them. It's like a business card for AI agents.
- **Tasks** - The fundamental unit of work. Tasks have a lifecycle (submitted → working → completed/failed) and can be long-running with progress updates.
- **Messages & Parts** - Agents communicate through messages containing different content types: text, files, or structured data.
- **Update Mechanisms** - Three ways to get task updates: polling (simple), streaming (real-time), or push notifications (webhooks for async work).

**A2A vs MCP:** MCP (Model Context Protocol) connects agents to **tools and data**. A2A connects **agents to other agents**. They're complementary—an agent might use MCP to access a database and A2A to delegate work to a specialized agent. As of August 2026 both are hosted by the same body, the [Agentic AI Foundation](#standards-bodies--governance).

### 🆕 v1.0 and the Move to AAIF

- **v1.0 shipped March 12, 2026** — the first stable, production-ready specification. Headline additions: multi-protocol bindings and version negotiation, multi-tenancy, **signed Agent Cards** for cryptographic identity verification, proper OAuth flows for headless agents, and paginated task listing.
- **Joined the Agentic AI Foundation on August 27, 2026** as a Growth Stage project, placing A2A under the same neutral governance as MCP rather than direct Google stewardship.
- Framework support spans LangGraph, CrewAI, Pydantic AI, AG2, and IBM BeeAI; enterprise adopters include ServiceNow, Salesforce, Atlassian, and SAP.

### 🎖️ Official Resources

- [A2A Documentation](https://a2a-protocol.org/latest/) - Protocol overview
- [A2A GitHub](https://github.com/a2aproject/A2A) - Specification and SDKs
- [A2A Specification](https://a2a-protocol.org/latest/specification/) - Technical spec

### 🔌 Tools & Plugins

- [A2A Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/a2a-multi-agent) - Claude Code plugin for A2A development

### 🐍 Official SDKs

- [Python SDK](https://github.com/a2aproject/a2a-python) - `pip install a2a-sdk`
- [JavaScript SDK](https://github.com/a2aproject/a2a-js) - `npm install @a2a-js/sdk`
- [Go SDK](https://github.com/a2aproject/a2a-go) - `go get github.com/a2aproject/a2a-go`
- [Java SDK](https://github.com/a2aproject/a2a-java) - Maven package
- [.NET SDK](https://github.com/a2aproject/a2a-dotnet) - `dotnet add package A2A`

### 💻 Samples & Tools

- [A2A Samples](https://github.com/a2aproject/a2a-samples) - Code samples and demos
- [A2A Inspector](https://github.com/a2aproject/a2a-inspector) - Debugging tool

### 📚 Tutorials

- [A2A Codelab](https://codelabs.developers.google.com/intro-a2a-purchasing-concierge) - Google hands-on tutorial

### 📰 Announcements

- [Announcing A2A](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/) - Google Developers Blog
- [A2A v0.3 Upgrade](https://cloud.google.com/blog/products/ai-machine-learning/agent2agent-protocol-is-getting-an-upgrade) - Google Cloud Blog
- [A2A One-Year Milestone: 150+ Organizations](https://www.linuxfoundation.org/press/a2a-protocol-surpasses-150-organizations-lands-in-major-cloud-platforms-and-sees-enterprise-production-use-in-first-year) - Linux Foundation, April 2026 — 22K+ GitHub stars, integrated into Azure AI Foundry and AWS Bedrock AgentCore
- [A2A Protocol Ships v1.0](https://a2a-protocol.org/latest/blog/2026/03/12/a2a-protocol-ships-v10-production-ready-standard-for-agent-to-agent-communication/) - March 12, 2026 — first stable release
- [A New Chapter for A2A: Joining the Agentic AI Foundation](https://a2a-protocol.org/latest/blog/2026/08/27/a-new-chapter-for-a2a-joining-the-agentic-ai-foundation/) - August 27, 2026
- [A2A Joins AAIF's Open Agentic Stack](https://aaif.io/blog/a2a-joins-aaif) - AAIF announcement
- [Forbes: Agent2Agent Joins the Agentic AI Foundation Alongside MCP](https://www.forbes.com/sites/janakirammsv/2026/08/19/agent2agent-joins-the-agentic-ai-foundation-alongside-mcp/) - Industry analysis

<br>

## MCP - Model Context Protocol

> Agent-to-tool communication, including optional bindings for commerce protocols

**Maintainers:** Agentic AI Foundation (Linux Foundation), donated by Anthropic December 2025
**Latest version:** `2026-07-28` — [official versioning](https://modelcontextprotocol.io/docs/2026-07-28/learn/versioning) checked November 13, 2026

### Why MCP belongs in an agentic commerce list

MCP lets agents invoke commerce tools through a common interface. UCP supports REST and MCP, and ACP provides a REST API alongside its MCP binding. Implementing either commerce protocol does **not** require MCP. Choose the binding supported by the integration: see [Google's UCP overview](https://developers.google.com/merchant/ucp) and [ACP's checkout API](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/2026-04-17/openapi/openapi.agentic_checkout.yaml).

### 🆕 What Changed in `2026-07-28`

- **Stateless core** — MCP moved from a bidirectional stateful protocol to a request/response model, so servers deploy on serverless and edge infrastructure. This directly affects how you model long-lived checkout sessions.
- **Extensions framework** — a versioned mechanism for adding capabilities without changing the core protocol
- **Tasks extension** — contributed by AWS, adds reliable long-running agent work
- **MCP Apps extension** — interactive UI surfaces
- **Authorization hardening** — the core authorization spec now tracks production OAuth 2.0 and OpenID Connect deployments more closely
- **Formal deprecation policy**

### 🎖️ Official Resources

- [MCP Documentation](https://modelcontextprotocol.io/) - Protocol overview and guides
- [MCP GitHub](https://github.com/modelcontextprotocol) - Specification and SDKs
- [The 2026-07-28 Specification](https://blog.modelcontextprotocol.io/posts/2026-07-28/) - Release announcement
- [AAIF Migration Guide](https://aaif.io/blog/mcp-2026-07-28-whats-changing-and-how-to-migrate) - What's changing and how to migrate
- [Anthropic: Donating MCP and Establishing the AAIF](https://anthropic.com/news/donating-the-model-context-protocol-and-establishing-of-the-agentic-ai-foundation) - Governance handover

<br>

## WebMCP - Browser-Native Agent Tools

> Websites expose tools directly to AI agents from the page, via `document.modelContext`

**Venue:** W3C Web Machine Learning Community Group (incubation — **not** a W3C Standard or on the Standards Track)
**Authors:** Google and Microsoft engineers
**API surface:** `document.modelContext`
**Spec:** [Draft Community Group Report, November 12, 2026](https://webmachinelearning.github.io/webmcp/) — checked November 13, 2026
**Vendor positions:** Mozilla **neutral**; WebKit/Safari **oppose** — see [Vendor Positions](#-vendor-positions-authoritative) before building on this

### What is WebMCP?

WebMCP lets a web page register tools that an AI agent running in the browser can call directly, rather than the agent scraping the DOM or driving a headless browser. For commerce, that means a merchant can expose "search catalog," "add to cart," or "apply discount" as first-class agent-callable tools on their existing storefront — no separate server-side MCP deployment required.

**Key Concepts:**
- **Tool registration** — pages register tools via the page-level model context API
- **Declarative form annotations** — existing forms can be surfaced to agents with markup rather than script
- **Human-in-the-loop** — tools can require explicit user interaction before executing, which matters for anything that spends money
- **Browser session auth** — tools run in the user's already-authenticated session

### 🧭 Vendor Positions (authoritative)

Both other engines have now **formally closed** their standards-positions reviews. This is the single most important fact about WebMCP's outlook, and it is frequently misreported as "under evaluation":

| Engine | Position | Date |
|---|---|---|
| **Mozilla / Firefox** | **Neutral** ([standards-positions#1412](https://github.com/mozilla/standards-positions/issues/1412)) | August 5, 2026 |
| **WebKit / Safari** | **Oppose** ([standards-positions#670](https://github.com/WebKit/standards-positions/issues/670)) | June 11, 2026 |

WebKit's opposition is architectural, not incidental. The issue is labelled with concerns spanning **privacy, security, meaningful user consent, duplication, API design, internationalization, portability, use cases, and venue**. The substance of their argument:

- An agent acting for a user is **assistive technology**, and sites should not be able to detect that a user is relying on one
- If a site's actions are hard for an agent to use, that is a gap in the page's own semantics — the fix belongs in **HTML and ARIA**, the platform's shared layers, not in a parallel agent-facing tool layer
- The proposal designs a solution before establishing what the problem actually is

**Why this matters for commerce:** WebKit's "don't expose that the user is using an agent" invariant runs in the opposite direction from [Web Bot Auth](#web-bot-auth), Visa TAP, and the [KYA framework](#-cross-network-interoperability-kya), all of which exist precisely so merchants *can* identify and verify agents. That is a genuine unresolved tension in the stack, not a detail.

Discussion is ongoing and the spec authors have signalled willingness to converge — including floating a declarative-only variant — so this is not necessarily final.

### 📊 Reported Implementation Status

**Chrome origin trial:** [Chrome's documentation](https://developer.chrome.com/docs/ai/webmcp), updated October 7, documents a trial starting in **Chrome 149** and local testing via `about:flags#enable-webmcp-testing`.

**Metadata discrepancy:** checked November 13, the [ChromeStatus API](https://chromestatus.com/api/v0/features/5117755740913664) still says `Proposed` and `origintrial: false` in its summary, but detailed trial stage `5111811472621568` records an origin trial beginning at milestone 149. The detailed record supports Chrome's documentation; the summary flags are inconsistent. An origin trial is not general availability.

The spec repository's [implementation-status.md](https://github.com/webmachinelearning/webmcp/blob/main/implementation-status.md) separately reports Edge, Brave, and ChatGPT Desktop support. Treat these as repository-reported claims and verify the particular vendor's support before relying on them. Standards positions above describe design assessments, not promises of browser implementation.

### ⚠️ Other Caveats

- **API renamed.** The tool-registration getter moved from `navigator.modelContext` to **`document.modelContext`**. Chrome 150 deprecates the old name but keeps it as an alias — tutorials published before August 2026 still use the old spelling, so check which surface any example targets.
- **Incubation only.** Per Chrome Platform Status, maturity is "Specification being incubated in a Community Group" — not a Working Group, not on the Standards Track.

### 🎖️ Official Resources

- [WebMCP on Chrome for Developers](https://developer.chrome.com/docs/ai/webmcp) - Official Chrome documentation and origin trial details
- [WebMCP Explainer (W3C Community Group)](https://github.com/webmachinelearning/webmcp) - Specification and design discussion
- [WebMCP Draft Specification](https://webmachinelearning.github.io/webmcp/) - Document-level API, conformance requirements, and links to Web Platform Tests; Community Group incubation
- [Implementation Status](https://github.com/webmachinelearning/webmcp/blob/main/implementation-status.md) - Spec repo's own per-browser support claims
- [Chrome Platform Status entry](https://chromestatus.com/feature/5117755740913664) - Maturity and browser signals
- [Mozilla standards position (neutral)](https://github.com/mozilla/standards-positions/issues/1412) - Firefox's formal position
- [WebKit standards position (oppose)](https://github.com/WebKit/standards-positions/issues/670) - Safari's formal position and rationale

### 🔌 Tools & Plugins

- [WebMCP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/webmcp-browser-agents) - Claude Code plugin for WebMCP development

<br>

## Web Bot Auth

> Cryptographic client identity for automated HTTP requests

**Originator:** Cloudflare
**Mechanism:** HTTP Message Signatures ([RFC 9421](https://www.rfc-editor.org/rfc/rfc9421.html)) — an Ed25519 key, a `Signature-Agent` header, and a published JWKS directory
**Standards status:** Active IETF working-group Internet-Draft, [draft-ietf-webbotauth-httpsig-protocol-01](https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/), updated October 29, 2026; checked November 13, 2026. An adopted WG draft, not an RFC

### Why it belongs here

Web Bot Auth answers a question none of the commerce protocols answer on their own: *is this agent who it claims to be?* Rather than IP ranges and spoofable user-agent strings, a bot proves identity per request with a cryptographic signature. It has quietly become the common substrate under several protocols in this list:

- **Visa Trusted Agent Protocol** is built on it
- **Mastercard Agent Pay** incorporates it for agent authentication
- **Shopify** began signing and authenticating agent traffic with it in May 2026 — unsigned agents get the strictest Storefront API rate-limit tier, which makes it a practical prerequisite for agentic storefronts and Hydrogen integrations
- **OpenAI** signs ChatGPT agent and agentic requests with it
- **UCP** has tracked Web Bot Auth interoperability in its release planning

Client authentication and purchase authorization are separate: a valid agent signature does not itself prove that a shopper authorized a transaction.

### 🎖️ Official Resources

- [Web Bot Auth](https://www.webbotauth.com/) - Overview and adoption
- [IETF Web Bot Auth Working Group](https://datatracker.ietf.org/wg/webbotauth/about/) - Charter and drafts
- [Web Bot Auth HTTP Signature Draft](https://datatracker.ietf.org/doc/draft-ietf-webbotauth-httpsig-protocol/) - Adopted working-group draft and revision history
- [Cloudflare web-bot-auth](https://github.com/cloudflare/web-bot-auth) - Reference implementation
- [RFC 9421: HTTP Message Signatures](https://www.rfc-editor.org/rfc/rfc9421.html) - The underlying signature standard
- [Securing Agentic Commerce](https://blog.cloudflare.com/secure-agentic-commerce/) - Cloudflare on Web Bot Auth under Visa and Mastercard protocols

<br>

## How They Relate

The table groups related responsibilities; it is not a mandatory execution sequence. Commerce semantics, authorization evidence, client identity, tool access, payment exchange, and settlement can be combined according to the integration. Payment providers and networks supply implementations and rails rather than another required protocol step.

| Protocol | Layer | Purpose | Governance |
|----------|-------|---------|------------|
| **Web Bot Auth / Visa TAP** | Client identity | Authenticate automated requests; identity alone does not authorize a purchase | IETF WG draft / Visa |
| **MCP** | Tools | Agents reach tools and data; optional UCP and ACP bindings | AAIF (Linux Foundation) |
| **WebMCP** | Browser tools | Pages expose tools to in-browser agents | W3C Community Group (incubation) |
| **A2A** | Communication | Agents discover and talk to each other | AAIF (Linux Foundation) |
| **UCP** | Commerce | End-to-end commerce across shopping, food, and lodging | UCP Governing Council |
| **ACP** | Commerce | Checkout, product feeds, and delegated payment interfaces | OpenAI + Stripe + Meta |
| **AP2** | Authorization evidence | Checkout and Payment mandates, each with open and closed forms | FIDO Alliance standards work |
| **Verifiable Intent** | Authorization evidence | Verifiable intent, delegation constraints, and credential verification | Mastercard reference implementation; contributed to FIDO work |
| **MPP** | Payment exchange | HTTP payment authentication with method-specific payment flows | Stripe + Tempo |
| **AMP** | Payments | Mobile-first agentic payments via digital wallets (Alipay+) | Ant International |
| **x402** | Payment exchange | HTTP payment negotiation and settlement schemes | x402 Foundation (Linux Foundation) |
| **L402** | Payment exchange / API access | Lightning payments with Macaroon authorization tokens | Lightning Labs |

### Example: Planning a Trip

This is an illustrative composition, not a reference implementation or a guarantee of cross-merchant atomicity.

1. **A2A** - Your personal agent discovers flight, hotel, and car rental agents and coordinates options
2. **AP2** - A trusted surface obtains your authorization for open Checkout and Payment mandates with applicable merchant, item, and payment constraints
3. **Budget enforcement** - For a $700 recurring payment budget, the implementation evaluating the constraint tracks prior presentations and checks each proposed payment against the remaining allowance, as required by the [Payment Mandate specification](https://ap2-protocol.org/ap2/payment_mandate/)
4. **UCP/ACP** - Agents use the commerce interface supported by each merchant to prepare checkout
5. **AP2** - Closed mandates bind the concrete checkout and payment details within the authorized constraints
6. **Result** - Bookings have verifiable authorization records; handling a later booking failure, cancellation, or refund still requires application logic

### UCP vs ACP

Both define commerce interfaces, with different integration surfaces and capabilities:

- **UCP** - Commerce capabilities including identity linking, order management, and AP2 mandate support; Google and Shopify publish implementation guides
- **ACP** - Checkout, feeds, and delegated payment interfaces, including Shared Payment Token flows; OpenAI and Stripe publish integration guides

Merchants wanting maximum reach may implement both — or sit behind an [integration layer](#integration--orchestration-layer) that speaks several protocols at once.

**Version and product distinction:** As checked November 13, UCP's latest release is `2026-08-25` and ACP's latest published snapshot is `2026-04-17` (beta). OpenAI's shift toward discovery and merchant-controlled checkout is a product-strategy change; it should not be read as removal of ACP's checkout API or exclusive platform support for either protocol.

<br>

## Crypto Payment Rails

### x402

> HTTP 402 stablecoin payments over HTTP — no API keys, accounts, or subscriptions

**Governance:** [x402 Foundation](https://x402.org/) under the Linux Foundation (originated by Coinbase and Cloudflare)
**Latest spec:** V2 — standardized payment headers, reusable session tokens, multi-chain support via CAIP

x402 leverages HTTP's `402 Payment Required` status code for instant stablecoin payments. It requires no API keys, accounts, or subscriptions—just a wallet. x402 also serves as a crypto payment rail within AP2 — see the [x402 flow samples](https://github.com/google-agentic-commerce/AP2/tree/main/code/samples) in the AP2 repository.

**Governance timeline:** Coinbase and Cloudflare announced their intent to form the foundation in September 2025. The Linux Foundation announced the x402 Foundation on **April 2, 2026** at MCP Dev Summit North America, and declared its **operational launch on July 14, 2026** with 40 founding member organizations — 17 of them premier members, including Visa, Stripe, and the Solana Foundation.

**Adoption evidence:** Transaction counts, active wallets, and verified commercial purchases measure different things. The March 2026 reporting linked below is historical analysis, not a current estimate of organic demand.

- [x402 Documentation](https://docs.x402.org/introduction) - Foundation documentation, SDK support, and migration guides
- [x402 GitHub](https://github.com/x402-foundation/x402) - Canonical specification, SDKs, and examples; `coinbase/x402` is a fork
- [x402 Specification](https://github.com/x402-foundation/x402/tree/main/specs) - Technical spec
- [x402 Upto](https://docs.x402.org/schemes/upto) - Authorize a maximum and settle the actual cost of a request
- [x402 Batch Settlement](https://docs.x402.org/schemes/batch-settlement) - Batch settlement implementation guidance
- [x402 Signed Offers and Receipts](https://docs.x402.org/extensions/offer-receipt) - Signed offer and receipt extension
- [Coinbase Developer Docs](https://docs.cdp.coinbase.com/x402/welcome) - Coinbase-specific implementation guide
- [Linux Foundation: x402 Foundation Operational Launch](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications) - July 14, 2026, 40 founding members
- [Cloudflare: Launching the x402 Foundation](https://blog.cloudflare.com/x402/) - Cloudflare Blog
- [Cloudflare and AWS Embed x402 at the Edge](https://www.infoq.com/news/2026/07/cloudflare-aws-x402-micropayment/) - InfoQ, July 2026
- [Coinbase Agent.market](https://cryptonews.com/news/coinbase-x402-ai-agent-app-store-crypto-payments/) - x402-paywalled AI agent app store
- [CoinDesk: Demand Is Just Not There Yet](https://www.coindesk.com/markets/2026/03/11/coinbase-backed-ai-payments-protocol-wants-to-fix-micropayment-but-demand-is-just-not-there-yet) - March 11, 2026 reporting on transaction volume and its measurement limits
- [Solana Integration Guide](https://solana.com/developers/guides/getstarted/intro-to-x402) - Solana x402 integration
- [Stellar x402 Facilitator](https://stellar.org/blog/foundation-news/x402-on-stellar) - Production facilitator on OpenZeppelin Relayer (sub-5s settlement)
- [Pay.sh by Solana + Google Cloud](https://www.banklesstimes.com/articles/2026/05/06/solana-and-google-cloud-launch-pay-sh-for-ai-agent-micropayments/) - May 2026 stablecoin micropayment gateway for AI agents accessing Gemini, BigQuery, Vertex AI, and 50+ APIs

### L402

> Macaroons + Lightning Network micropayments for stateless API authentication

**Creator:** Lightning Labs

L402 combines Macaroons (bearer authorization tokens) with Lightning Network micropayments for a stateless, pay-per-request API authentication model. It's the Bitcoin-native alternative to x402.

- [L402 Builder's Guide](https://docs.lightning.engineering/the-lightning-network/l402) - Comprehensive documentation
- [L402 Protocol Specification](https://docs.lightning.engineering/the-lightning-network/l402/protocol-specification) - Technical spec
- [L402 GitHub](https://github.com/lightninglabs/L402) - Protocol specification source
- [Aperture](https://github.com/lightninglabs/aperture) - Production L402 reverse proxy for REST and gRPC APIs

### Fewsats

> L402 toolkit for AI agents — MCP server, CLI, Python SDK

**Maintenance status:** Not reverified in the November review; check the repositories' recent activity and compatibility before depending on them. Inactivity alone does not establish abandonment.

- [Fewsats MCP Server](https://github.com/fewsats/fewsats-mcp) - MCP server for AI agent L402 payments
- [L402 Python SDK](https://github.com/Fewsats/L402-python) - Python SDK for L402 agent payments

### PipRail

> Backendless, self-custody x402 toolkit — TypeScript SDK + MCP server, no facilitator

An open-source x402 implementation with no backend, database, or protocol fee: payments settle directly to the developer's wallet and are verified locally against their own RPC. A single `chain:` parameter spans the major EVM chains plus Solana, TON, Tron, NEAR, Sui, Aptos, Algorand, Stellar, and the XRP Ledger. MIT licensed.

- [PipRail GitHub](https://github.com/piprail/piprail) - Source, chain drivers, and runnable merchant/agent demos
- [@piprail/sdk](https://www.npmjs.com/package/@piprail/sdk) - TypeScript SDK for x402 payments across EVM and non-EVM chains
- [@piprail/mcp](https://www.npmjs.com/package/@piprail/mcp) - MCP server giving an agent a budget-bound wallet to pay x402 URLs
- [PipRail Docs](https://docs.piprail.com) - Chain coverage, the `exact` scheme, and gasless/keyless rails

<br>

## Fiat Payment Rails

EMVCo's draft **Agentic Payments – Framework for Specifications** introduces **Intent Services** for registering and managing consumer-authorized intent through a transaction lifecycle. The [September announcement](https://www.emvco.com/news-publications/emvco-requests-feedback-on-framework-for-secure-interoperable-and-scalable-card-based-agentic-payments/) opened public review; the [November 10 update](https://www.emvco.com/news-publications/advancing-secure-agentic-payments-highlights-from-the-emvco-hanoi-board-of-advisors-meeting/) reports feedback being considered. This is standards-development work, not a completed specification or a claim of network deployment.

### 🤝 Cross-Network Interoperability (KYA)

> Ant International + Mastercard + Visa, September 9–10, 2026

Ant International, Mastercard, and Visa announced collaboration on a shared **Know-Your-Agent (KYA)** interoperability framework across their agentic commerce initiatives.

**What it does:** establishes shared principles so common trust signals are recognized across card networks, wallet ecosystems, agent platforms, and marketplaces, while each network keeps its own verification and decisioning. The goal is to cut duplicate agent identity verification and integration cost.

**What it is not:** a merged protocol or a published specification. As of September 2026 this is an announced collaboration on principles, not a shipped standard.

The announcement cites McKinsey's projection that AI agents could orchestrate **$3–5 trillion** of global consumer commerce by 2030.

- [Ant International, Mastercard and Visa Initiate KYA Collaboration](https://www.businesswire.com/news/home/20260909003891/en/Ant-International-Mastercard-and-Visa-Initiate-Collaboration-on-Know-Your-Agent-Interoperability-to-Scale-Agentic-Commerce) - BusinessWire, September 9, 2026 (primary source)
- [PYMNTS: Visa and Mastercard Team With Ant on KYA](https://www.pymnts.com/cybersecurity/2026/visa-mastercard-team-with-ant-know-your-agent-framework) - Industry coverage
- [Biometric Update: Making Agentic Protocols Interoperable](https://www.biometricupdate.com/202609/ant-international-visa-mastercard-work-to-make-agentic-protocols-interoperable) - Analysis of the interop challenge

### Visa — Intelligent Commerce

> Trusted Agent Protocol (TAP) — authentication framework for agent-to-network communication

**Initiative:** Visa "Intelligent Commerce" program
**Authentication:** [Web Bot Auth](#web-bot-auth) over HTTP Message Signatures (RFC 9421)
**Announced:** October 14, 2025 with Cloudflare and 12 launch partners (Adyen, Ant International, Checkout.com, Coinbase, CyberSource, Elavon, Fiserv, Microsoft, Nuvei, Shopify, Stripe, Worldpay)
**Status:** Commercially launched Q1 2026 — 100+ partners enrolled, 30+ in sandbox, 20+ integrating in production. Fiserv was the first major processor to adopt at scale (January 2026).

Visa's TAP provides the authentication layer for AI agents to interact with card networks directly, using cryptographic HTTP message signatures. It signs an agent's identity into HTTP request headers so a merchant can cryptographically verify that the agent is legitimate.

- [Intelligent Commerce Developer Program](https://developer.visa.com/capabilities/visa-intelligent-commerce) - Visa agent commerce program
- [Trusted Agent Protocol (TAP)](https://developer.visa.com/capabilities/trusted-agent-protocol) - TAP documentation
- [TAP GitHub](https://github.com/visa/trusted-agent-protocol) - Reference implementation and spec; consult the developer portal for integration availability
- [Visa Launches Validator Node on Tempo](https://investor.visa.com/news/news-details/2026/Visa-Launches-Validator-Node-on-Tempo-Blockchain/default.aspx) - April 14, 2026 — Visa runs validator on Stripe's Tempo chain (TradFi/DeFi crossover)
- [Visa Agentic Ready Expands to Canada](https://www.globenewswire.com/news-release/2026/05/05/3287953/0/en/Visa-Expands-Agentic-Ready-Program-to-Canada-to-Advance-AI-Driven-Commerce.html) - May 5, 2026 — BMO, CIBC, RBC, Scotiabank, TD as early adopters
- **July 2026:** Visa became a premier member of the [x402 Foundation](#x402) at its operational launch
- **September 2026:** Visa joined Mastercard and Ant International on the [KYA interoperability framework](#-cross-network-interoperability-kya)

### Mastercard — Agent Pay

> Agentic Tokens — scoped, time-limited payment credentials for AI agents

Mastercard Agent Pay issues Agentic Tokens: scoped, time-limited credentials that allow agents to initiate payments within defined boundaries. Authentication is built on [Web Bot Auth](#web-bot-auth). Consult the developer documentation for supported integrations and availability; the separate Agent Pay for Machines program is described below.

#### Agent Pay for Machines

**Availability:** Announced June 10, 2026; [developer Early Access announced October 20](https://www.mastercard.com/uz/uz/news-and-trends/press/2026/october/Mastercard-Agent-Pay-for-Machines-in-action.html), with buyer/seller APIs, a toolkit, sandbox, and documentation. Early Access does not establish general availability.

A distinct product for the machine-to-machine end of the spectrum: high-velocity, low-value, and micro-transactions executed programmatically at machine speed. Four capabilities:

- **Credentialing** — every agent receives credentials; can use Verifiable Intent for cross-ecosystem recognition
- **Permissioning** — organizations set authorization rules and spending limits, programmatically enforced
- **Transacting** — verified participants connect across providers for continuous automated commerce
- **Settling** — multi-rail settlement across cards, accounts, and **stablecoins**

Mastercard's launch announcement states compatibility with **x402** and describes participating partners. Compatibility, partner participation, and production availability are separate claims.

- [Agent Pay Developer Docs](https://developer.mastercard.com/mastercard-checkout-solutions/documentation/use-cases/agent-pay/) - Integration documentation
- [Mastercard Launches Agent Pay for Machines](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Pay-for-Machines-to-Unlock-Super-Fast-Always-On-Payments/default.aspx) - June 10, 2026 — machine-speed micropayments, x402-compatible, multi-rail settlement
- [Mastercard Launches Agent Suite](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Suite-to-Ready-Enterprises-for-a-New-Era/default.aspx) - January 27, 2026 announcement of an enterprise toolkit targeting Q2 availability; subsequent general availability was not independently confirmed in the November review
- [Verifiable Intent](https://verifiableintent.dev) - Specification and verification model for authorization and delegation evidence
- [Verifiable Intent GitHub](https://github.com/agent-intent/verifiable-intent) - Draft v0.1 maintained by Mastercard; credential formats, constraints, verification procedures, Python examples, and tests
- [FIDO: AP2 and Verifiable Intent](https://fidoalliance.org/building-the-trust-layer-for-agentic-payments-with-ap2-and-verifiable-intent/) - Contribution to FIDO standards work, distinct from a completed FIDO standard
- **September 2026:** Mastercard joined Visa and Ant International on the [KYA interoperability framework](#-cross-network-interoperability-kya)

### American Express — Agentic Commerce Experiences (ACE)

> Developer kit, intent evidence, scoped credentials, and Agent Purchase Protection

**Launched:** April 14, 2026
**Partners:** OpenAI, Google, Microsoft, PayPal, Stripe + 11 others

Amex ACE combines agent registration, account enablement, intent intelligence, scoped payment credentials, and cart context. The October 13 **Intent Intelligence framework** describes an Intent ID, Proof of Intent Token, and credentials tied to the authorized purchase. Agent Purchase Protection is a separate program whose coverage depends on its terms.

- [American Express Debuts ACE Developer Kit](https://www.digitalcommerce360.com/2026/04/14/american-express-agentic-commerce-developer-kit-purchase-protection/) - DigitalCommerce360 coverage of launch
- [PYMNTS: Amex to Back Purchases by Customer's AI Agents](https://www.pymnts.com/artificial-intelligence-2/2026/american-express-to-back-purchases-made-by-customers-ai-agents/) - Coverage of Agent Purchase Protection
- [Amex Agentic Commerce Hub](https://www.americanexpress.com/en-us/company/agentic-commerce/) - Official Amex page (primary source)
- [Amex Intent Intelligence Framework](https://www.americanexpress.com/en-us/newsroom/technology-innovation/intent-intelligence-framework-agentic-commerce/) - October 13, 2026 explanation of intent evidence and scoped credentials

### PayPal — Agent Ready

> ACP-based agent payments for existing PayPal and Braintree merchants

PayPal's Agent Ready provides agent-initiated payment integration for existing merchants. Store Sync covers catalog integration, and the Agent Toolkit provides programmatic access. Consult the integration documentation for security and compliance responsibilities.

- [Agentic Commerce Overview](https://docs.paypal.ai/growth/agentic-commerce/overview) - PayPal agentic commerce docs
- [Agent Ready Documentation](https://docs.paypal.ai/growth/agentic-commerce/agent-ready) - Agent Ready integration guide
- [Store Sync](https://docs.paypal.ai/growth/agentic-commerce/store-sync) - Product catalog and cart integration
- [Agent Toolkit](https://github.com/paypal/agent-toolkit) - PayPal agent API integration via function calling

### Cloudflare — Agents SDK

> Infrastructure SDK with x402 support and announced Visa/Mastercard integration plans

Cloudflare's Agents SDK embeds payment rails directly into the edge infrastructure layer, currently supporting x402. Cloudflare is also the originator of [Web Bot Auth](#web-bot-auth), the agent-identity layer beneath both Visa TAP and Mastercard Agent Pay.

**Status caveat:** Cloudflare's October 2025 announcement described planned Visa TAP and Mastercard Agent Pay support in the Agents SDK. The announcement alone does not establish delivery; native SDK availability for those integrations was not independently confirmed in the November review.

- [Agents SDK Documentation](https://developers.cloudflare.com/agents/) - Full SDK docs
- [x402 Integration](https://developers.cloudflare.com/agents/x402/) - x402 in the Agents SDK
- [Secure Agentic Commerce](https://blog.cloudflare.com/secure-agentic-commerce/) - Visa and Mastercard protocol support announcement, October 2025

<br>

## Integration & Orchestration Layer

> Middleware that speaks several agentic protocols so merchants do not have to pick one

A distinct category emerged in mid-2026: rather than choosing between UCP, ACP, and AP2, enterprise merchants increasingly sit behind an abstraction layer that translates across all of them. This is a direct consequence of the protocol landscape refusing to consolidate.

### Adyen Agentic

> "The universal translator for the next era of commerce" — announced June 16, 2026

A modular API suite letting enterprises sell through conversational AI platforms without rebuilding commerce systems per channel. Three layers:

- **Agentic Feed** — distributes real-time catalog, pricing, and availability data
- **Agentic Cart** — connects existing checkout, tax, fulfillment, and order management to agent platforms
- **Agentic Payments** — authentication, token portability, and risk management for agent-led transactions

Speaks UCP, ACP, AP2, and Meta's AI checkout. Strategic partners include American Express, Mastercard, Visa, and Salesforce; early enterprise merchants include ESW, Scheels, Sezane, and SharkNinja. Limited availability for US enterprise merchants at launch.

- [Adyen Agentic Announcement](https://www.adyen.com/press-and-media/adyen-agentic) - Official press release, June 16, 2026
- [Adyen Agentic Knowledge Hub](https://www.adyen.com/knowledge-hub/adyen-agentic-the-universal-translator-for-the-next-era-of-commerce) - Technical overview
- [PYMNTS: Adyen Debuts Agentic Solutions for Enterprise Merchants](https://www.pymnts.com/news/b2b-payments/2026/adyen-debuts-agentic-solutions-for-enterprise-merchants/) - Industry coverage

### Related

- [PayPal Agent Ready](#paypal--agent-ready) - ACP-based agent payments for existing PayPal and Braintree merchants
- [Cloudflare Agents SDK](#cloudflare--agents-sdk) - Edge infrastructure with native x402 support

<br>

## Tools & Plugins

- [Agentic Commerce Claude Plugins](https://github.com/OrcaQubits/agentic-commerce-claude-plugins) - Claude Code plugins for agentic commerce protocol development (UCP, ACP, AP2, MPP, A2A, WebMCP, NLWeb)

<br>

## Developer Tools

### ✅ UCP Validation & Testing

- [UCP Playground](https://ucp.dev/latest/specification/shopping/playground/) - Official testing environment
- [UCP Checker](https://ucpchecker.com/) - Schema compliance validation
- [UCP Lighthouse](https://ucp.rest/) - Payload validation
- [Merchant Directory](https://merchants.awesomeucp.com/) - UCP-enabled merchants

### 🤖 Agent Development

- [Agent Development Kit (ADK)](https://google.github.io/adk-docs/) - Google's agent framework
- [ADK Python](https://github.com/google/adk-python) - ADK Python SDK
- [ADK Samples](https://github.com/google/adk-samples) - ADK sample code
- [Awesome ADK Agents](https://github.com/Sri-Krishna-V/awesome-adk-agents) - Curated ADK examples

<br>

## Related Technologies

> MCP and WebMCP now have dedicated sections above — see [MCP](#mcp---model-context-protocol) and [WebMCP](#webmcp---browser-native-agent-tools).

- [NLWeb](https://github.com/microsoft/NLWeb) - Microsoft-originated framework for making any website agent-ready via Schema.org + MCP
- [AGENTS.md](https://agents.md/) - Convention for giving coding agents project context; an AAIF founding project
- [OAuth 2.0](https://oauth.net/2/) - Authorization framework used by UCP identity linking
- [HTTP Message Signatures (RFC 9421)](https://www.rfc-editor.org/rfc/rfc9421.html) - Signature scheme underlying Visa TAP and Web Bot Auth
- [EIP-3009](https://eips.ethereum.org/EIPS/eip-3009) - Transfer-with-authorization primitive used by some EVM payment implementations; not a universal requirement of MPP

<br>

## Learning Resources

### 📖 Community Guides

- [UCP Complete Guide](https://a2aprotocol.ai/blog/2026-universal-commerce-protocol) - 2026 UCP overview — predates the v2026-08-25 breaking changes
- [A2A Complete Guide](https://a2aprotocol.ai/blog/2025-full-guide-a2a-protocol) - 2025 A2A overview — ⚠️ pre-v1.0; check against the [current spec](https://a2a-protocol.org/latest/specification/)
- [A2A Advanced Features](https://a2aprotocol.ai/blog/2025-part2-full-guide-a2a-protocol) - Deep dive Part 2 — ⚠️ pre-v1.0

> ⚠️ **Dating caveat for all third-party guides below:** the protocols moved fast in 2026. AP2 renamed Cart Mandate to Checkout Mandate, A2A reached v1.0 in March, MCP went stateless in July, and UCP shipped breaking changes in August. Tutorials written before mid-2026 are likely to use superseded names and URLs. Prefer the official specs where they disagree.

### 📖 Third-Party Analysis

- [UCP Standards & Protocols Map](https://universalcommerceprotocol.blog/en/standards-schemas-protocols/) - Mapping of schema.org Product, GS1, MCP, A2A, AP2, ACP, Visa Intelligent Commerce, and Mastercard Agent Pay, and how they interlock
- [Everest Group: AP2 Analysis](https://www.everestgrp.com/googles-agent-payments-protocol-ap2-a-new-chapter-in-agentic-commerce-blog/) - Industry analysis
- [CSA: AP2 Security Framework](https://cloudsecurityalliance.org/blog/2025/10/06/secure-use-of-the-agent-payments-protocol-ap2-a-framework-for-trustworthy-ai-driven-transactions) - Security framework
- [IBM: What Is A2A](https://www.ibm.com/think/topics/agent2agent-protocol) - A2A explainer
- [Solo.io: A2A Guide](https://www.solo.io/topics/ai-infrastructure/what-is-a2a) - Infrastructure perspective
- [Illustrated Guide to AP2](https://arthurchiao.art/blog/ap2-illustrated-guide/) - Visual explainer

### 📝 Implementation Tutorials

- [AP2 Technical Guide (Medium)](https://medium.com/@visrow/google-agent-payments-protocol-ap2-technical-guide-implementation-73ee772fe349) - AP2 implementation
- [AP2 Java Implementation](https://medium.com/@visrow/agent-payments-protocol-ap2-complete-guide-with-java-implementation-aec56400d360) - Java guide
- [ACP Implementation Guide (Medium)](https://medium.com/@maheshlambe/step-by-step-guide-for-implementing-the-agentic-commerce-protocol-acp-aed4f9b1a457) - ACP step-by-step

### 📰 News Coverage

- [TechCrunch: UCP Launch](https://techcrunch.com/2026/01/11/google-announces-a-new-protocol-to-facilitate-commerce-using-ai-agents/) - UCP announcement
- [InfoQ: A2A Open Source](https://www.infoq.com/news/2025/04/google-agentic-a2a/) - A2A coverage
- [FinTech Magazine: AP2](https://fintechmagazine.com/news/agentic-pay-systems-googles-agent-payments-protocol) - AP2 coverage
- [SEJ: ACP & UCP for SEO](https://www.searchenginejournal.com/agentic-commerce-what-seos-need-to-consider-acp-ucp/563503/) - SEO considerations

### 🏢 Platform Announcements

#### Google
- [Gemini Enterprise for CX](https://www.googlecloudpresscorner.com/2026-01-11-Google-Cloud-Brings-Shopping-and-Customer-Service-Together-with-Gemini-Enterprise-for-Customer-Experience) - Official press release (Jan 2026)
- [NRF 2026 Remarks](https://blog.google/company-news/inside-google/message-ceo/nrf-2026-remarks/) - Google CEO message on AI platform shift
- [Google UCP Checkout in Canada](https://blog.google/intl/en-ca/products/explore-get-answers/a-new-way-to-shop-introducing-a-more-intuitive-agentic-shopping-experience-for-consumers-and-retailers-in-canada/) - November 4, 2026 rollout for eligible retailers; Merchant Center simplification is described as starting in 2027

#### OpenAI
- [Powering Product Discovery in ChatGPT](https://openai.com/index/powering-product-discovery-in-chatgpt/) - March 24, 2026 update on discovery and merchant-controlled checkout
- [Businesses in ChatGPT](https://openai.com/index/introducing-businesses-chatgpt/) - November 10, 2026 beta for eligible US businesses, including profiles, product feeds, and Business Agents; a product announcement, not an ACP version change

#### Microsoft
- [Microsoft Agentic AI for Retail](https://news.microsoft.com/source/2026/01/08/microsoft-propels-retail-forward-with-agentic-ai-capabilities-that-power-intelligent-automation-for-every-retail-function/) - Copilot Checkout, Brand Agents, Dynamics 365

#### Anthropic
- [Claude Commerce Agents](https://github.com/anthropics/commerce-agents) - **September 2, 2026** — open Apache-2.0 reference blueprint for shopping agents and merchant-operations agents on Claude. Examples across retail, travel, telecom, and entertainment, plus a `commerce-builder` Claude Code plugin. Notably ships **no payment protocol, no checkout, and no ad layer**: `checkout` renders the cart for the host application to complete, so the model never sees payment details. Explicitly *not maintained and not accepting contributions*.
- [DC360: Anthropic Debuts Claude Features Focused on Agentic Commerce](https://www.digitalcommerce360.com/2026/09/02/anthropic-debuts-claude-features-focused-on-agentic-commerce/) - Launch coverage; early users include Shopify, Visa, Mastercard, Accenture
- [PYMNTS: Anthropic Built the Shopping Brain and Skipped the Wallet](https://www.pymnts.com/news/artificial-intelligence/2026/anthropic-built-the-shopping-brain-and-skipped-the-wallet/) - Analysis of the deliberate payment-layer omission
- [Claude Marketplace Launch](https://siliconangle.com/2026/03/06/anthropic-launches-claude-marketplace-third-party-cloud-services/) - Third-party services in Claude (Snowflake, GitLab, Harvey AI, Replit, Lovable Labs), March 2026
- [Project Deal: Agent-to-Agent Commerce Experiment](https://www.anthropic.com/features/project-deal) - Marketplace experiment studying how model quality affects negotiation outcomes

#### Shopify
- [Shop MCP](https://shopify.dev/changelog/posts/add-shopping-and-shop-pay-checkout-to-any-agent-with-shop-mcp) - October 13, 2026 announcement of catalog, cart, and Shop Pay checkout access through MCP
- [Spring '26 Edition for Developers](https://www.shopify.com/news/spring-26-edition-dev) - **June 2026** — UCP opens to every developer with no approval gate; agents self-register a profile in the Developer Dashboard and call the public MCP endpoint
- **Web Bot Auth enforcement (May 2026)** — Shopify applies stricter Storefront API rate limits to bots and agents; unsigned traffic gets the strictest tier, so agent operators must sign requests with [Web Bot Auth](#web-bot-auth) to qualify for higher limits. Affects Hydrogen storefronts and Storefront MCP integrations.
- **Agentic Storefronts admin surface** — a dedicated *Sales channels → Agentic* page showing which queries products rank for inside ChatGPT and Microsoft Copilot, sales attributed to AI channels, and product-data recommendations
- [Shopify API Rate Limits](https://shopify.dev/docs/api/usage/limits) - Current limit tiers, including the bot and agent tiers

#### Meta
- [Muse Personal AI Agent](https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/) - September 8, 2026 launch, updated November 10; purchases require user confirmation. The announcement does not establish ACP use or identify Muse as the previously reported Hatch project
- [TechCrunch: Zuckerberg Teases Agentic Commerce](https://techcrunch.com/2026/01/28/zuckerberg-teases-agentic-commerce-tools-and-major-ai-rollout-in-2026/) - Meta Q4 earnings reveals 2026 AI roadmap
- [eMarketer: Meta Readies AI Shopping Agents for Instagram](https://www.emarketer.com/content/meta-readies-ai-shopping-agents-instagram-rival-tiktok-shop) - Historical reporting on a planned Instagram shopping agent; not confirmation of delivery
- [The Information: Meta's 'Hatch' Agent and Instagram Shopping Tool](https://www.theinformation.com/articles/meta-building-ai-agent-called-hatch-agentic-shopping-tool-instagram) - Historical reporting on Meta's internal agent effort

#### Amazon
- **Rufus retired May 13, 2026**, replaced by **Alexa for Shopping** — a unified assistant across the Shopping app, Amazon.com, and Echo Show. Material written before May 2026 referring to "Rufus" describes a discontinued brand.
- [Modern Retail: Buy for Me Analysis](https://www.modernretail.co/technology/brands-are-upset-that-buy-for-me-is-featuring-their-products-on-amazon-without-permission/) - Deep dive on Amazon's agentic purchasing
- [Amazon's Walled Garden Approach](https://stellagent.ai/insights/amazon-ai-agent-rufus-buy-for-me) - Analysis of Amazon's strategy of blocking third-party agents while building its own

<br>

## Market Sizing

Forecasts use different geographies and definitions of agent influence. The links below are research leads, not a comparable market-size series; check each original report's geography, target year, denominator, and methodology before reusing its estimate. The November review did not independently revalidate these forecasts.

- [McKinsey: Up to $5 Trillion in Agentic Commerce Sales by 2030](https://www.digitalcommerce360.com/2025/10/20/mckinsey-forecast-5-trillion-agentic-commerce-sales-2030/) - The global forecast
- [ICSC + McKinsey: $1T US Agentic Sales by 2030](https://www.paymentsdive.com/news/agentic-commerce-us-one-trillion-2030/819490/) - US B2C forecast
- [Forrester: Agentic Payments in B2C Commerce — Where We Are Now](https://www.forrester.com/blogs/agentic-payments-in-b2c-commerce-where-we-are-now/) - Analyst reality check against the forecasts

<br>

## Regulatory Landscape

> Distinguish enacted requirements, proposed rules, official guidance, and commentary. The sources below address different jurisdictions and legal questions.

Authorization records can inform disputes, but a protocol's signature or mandate does not by itself determine liability among the agent platform, merchant, payment provider, and consumer.

### European Union
- **High-risk timelines:** The Commission's [AI Omnibus publication](https://digital-strategy.ec.europa.eu/en/news/ai-omnibus-enters-force) reports entry into force on July 27, 2026 and gives **December 2, 2027 for Annex III high-risk systems** and **August 2, 2028 for high-risk systems embedded in regulated products**. These dates are attributed to the Commission; the audit could not independently inspect the linked legislative text. Do not conflate them with the Act's other applicability dates
- [EU AI Act Implementation](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai) - Official overview and phased obligations
- [Commission High-Risk Classification Guidance](https://digital-strategy.ec.europa.eu/en/policies/guidelines-ai-high-risk-systems) - Classification depends on intended use and the applicable category; a shopping agent is not automatically high-risk

### United States
- [CFPB Personal Financial Data Rights Reconsideration](https://www.consumerfinance.gov/rules-policy/rules-under-development/personal-financial-data-rights-reconsideration/) - August 22, 2025 advance notice under Dodd-Frank Section 1033, including questions about consumer representatives; this is not an agent-specific Regulation E rule or a resolution of payment-error liability

### ⚖️ Case Law: *Amazon v. Perplexity* (Ninth Circuit, August 4, 2026)

This preliminary-injunction decision addresses access by Perplexity's Comet agent on the record presented to the court.

**Holding:** The Ninth Circuit **vacated the preliminary injunction and remanded**. On that record, it treated the user as accessing Amazon with Comet's assistance and found Amazon had not established the CFAA access element against Perplexity. Routing through the user's computer was material to the analysis. [Court opinion, August 4, 2026](https://cdn.ca9.uscourts.gov/datastore/opinions/2026/08/04/26-1444.pdf).

**What it does *not* settle:**
- Other theories remain live — breach of contract, terms-of-service violations, and tort claims
- Agents with greater autonomy, or **direct server-to-server** communication, may land differently — the routing-through-the-user fact was load-bearing
- This was the preliminary-injunction stage only; the merits are unresolved

**Architectural inference:** Request routing and the user's role may matter to a similar analysis. The opinion did not adjudicate WebMCP, categorically authorize browser-resident agents, or resolve the legality of server-to-server commerce integrations.

- [Cooley: Ninth Circuit Rules on AI Agent Access Under the CFAA](https://www.cooley.com/news/insight/2026/2026-08-06-ninth-circuit-rules-on-ai-agent-access-to-third-party-websites-under-cfaa) - Legal analysis of the holding
- [Jones Day: Authorized by the User, Blocked by the Platform](https://www.jonesday.com/en/insights/2026/05/authorized-by-the-user-blocked-by-the-platform-testing-the-legal-limits-of-ai-agents) - The underlying legal question
- [Amazon Loses Injunction Blocking Perplexity's AI Shopping Agent](https://ppc.land/amazon-loses-injunction-blocking-perplexitys-ai-shopping-agent/) - Coverage of the reversal
- [Amazon Wins Court Order to Block Perplexity](https://www.cnbc.com/2026/03/10/amazon-wins-court-order-to-block-perplexitys-ai-shopping-agent.html) - CNBC, March 2026 — the since-vacated district court ruling

### United Kingdom
- [UK ICO: Agentic Commerce Report](https://ico.org.uk/about-the-ico/media-centre/news-and-blogs/2026/01/ai-ll-get-that/) - Tech Futures report on AI shopping agents and data protection

### Analysis
- [Agentic Commerce Regulation: What Merchants Must Know](https://www.chargeflow.io/blog/agentic-commerce-regulation-what-merchants-need-to-know) - Practical merchant compliance view
- [Center for Data Innovation: Regulation Meant for Humans Will Slow It Down](https://datainnovation.org/2026/03/agentic-commerce-is-coming-but-regulation-meant-for-humans-will-slow-it-down/) - Policy critique

<br>

## Community Resources

### 📚 Awesome Lists

- [Awesome UCP](https://github.com/Upsonic/awesome-ucp) - Community-curated UCP resources; check examples against the current specification
- [Awesome Agentic Patterns](https://github.com/nibzard/awesome-agentic-patterns) - Agentic AI patterns
- [Awesome Agentic Commerce](https://github.com/damoahdominic/awesome-agentic-commerce/) - Agentic commerce protocols resources
- [Awesome Agent Payments Protocol](https://github.com/unnamedaiagent/awesome-agent-payments-protocol) - Curated AP2, A2A, and x402 resources

### 🌐 Community Sites

- [Universal Commerce Protocol Blog](https://universalcommerceprotocol.blog/en/) - Bilingual (FR/EN) editorial hub on UCP, Shopify MCP, schema.org, and merchant readiness
- [A2A Protocol Community](https://a2aprotocol.ai/) - A2A guides and tutorials
- [Agent2Agent Info](https://agent2agent.info/) - A2A code examples
- [Agentic Commerce Pro](https://agenticcommerce.pro/) - ACP community examples
- [ACP Ready Directory](https://www.acpready.com/) - ACP-ready platforms and providers directory

### 📊 Trackers & State-of-the-Market

- [UCP Checker Blog](https://ucpchecker.com/blog/) - Monthly "State of Agentic Commerce" reports with independent crawler data on UCP adoption
- [agenticplug Protocol Tracker](https://agenticplug.ai/current-state-of-agentic-commerce) - Cross-protocol status and version tracker
- [Agentic Commerce Report](https://agenticcommerce.report/) - Weekly industry newsletter archive

### 📬 Newsletters

- [Agentic Commerce Frontier](https://agentcommerce.substack.com/) - Weekly agentic commerce newsletter

### 💬 Discussions

- [UCP GitHub Discussions](https://github.com/Universal-Commerce-Protocol/ucp/discussions)
- [ACP GitHub Discussions](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/discussions)
- [A2A GitHub Discussions](https://github.com/a2aproject/A2A/discussions)

<br>

## Adopters & Partners

Maintainers, foundation members, endorsers, and production implementers have different roles. Use the primary sources below for the named relationship and publication date; membership or endorsement alone does not establish an operational integration.

| Project or initiative | Primary source | What it establishes |
| --- | --- | --- |
| UCP | [Official announcements](https://ucp.dev/documentation/announcements/) | Dated governing and domain-council announcements; consult each notice for its roster |
| ACP | [Lead maintainers](https://raw.githubusercontent.com/agentic-commerce-protocol/agentic-commerce-protocol/7fdd78df677a94dce04c770644b0fbbb1401272b/MAINTAINERS.md) | OpenAI, Stripe, and Meta at the pinned revision; not a list of downstream adopters |
| AP2 | [Official documentation](https://ap2-protocol.org/) and [FIDO standards work](https://fidoalliance.org/building-the-trust-layer-for-agentic-payments-with-ap2-and-verifiable-intent/) | Protocol ecosystem and contribution to standardization; implementation support must be checked separately |
| A2A | [Linux Foundation one-year update](https://www.linuxfoundation.org/press/a2a-protocol-surpasses-150-organizations-lands-in-major-cloud-platforms-and-sees-enterprise-production-use-in-first-year) | Dated April 2026 ecosystem report |
| AAIF | [Foundation website](https://aaif.io/) | Foundation projects and membership, distinct from commerce protocol adoption |
| x402 Foundation | [Operational launch announcement](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications) | Founding membership as announced July 14, 2026 |
| Cross-network KYA | [Joint announcement](https://www.businesswire.com/news/home/20260909003891/en/Ant-International-Mastercard-and-Visa-Initiate-Collaboration-on-Know-Your-Agent-Interoperability-to-Scale-Agentic-Commerce) | Ant International, Mastercard, and Visa's September 2026 collaboration announcement |
| Banking principles | [Building Trust in Agentic Commerce](https://newsroom.bankofamerica.com/content/newsroom/press-releases/2026/09/global-banks-collaborate-on-principles-for-trusted-agentic-comme.html) | Six banks' September 22, 2026 industry principles; not a certification of protocol support |

See [Platform Announcements](#-platform-announcements) for dated product developments and the individual protocol sections for implementation resources.

---

## Contributing

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) before opening a pull request.

**The scope test:** does an entry help someone *understand or implement a protocol*, or does it *offer them a service that uses one*? The first belongs here; the second does not, however good the service.

- ✅ Specifications, official SDKs and docs, governance bodies, conformance tools, vendor-neutral analysis
- ✅ **Corrections** — outdated versions, renamed concepts, dead links, claims that stopped being true. Reviewed fastest
- ❌ Products, hosted services, and paid APIs built on these protocols
- ❌ New sections created to house your own entry

If you are affiliated with something you submit, say so in the pull request.

<br>

## License

This compilation is provided under the [MIT License](./LICENSE).

Linked specifications and implementations have their own licenses; consult each project's license and applicable standards-body terms.
