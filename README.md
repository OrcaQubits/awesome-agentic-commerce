# Awesome Agentic Commerce [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for agentic commerce protocols: UCP, ACP, AP2, MPP, AMP, and A2A

This repository is a **reference point** to official resources. It does not own or maintain these protocols. For authoritative information, always consult the official documentation.

## Contents

- [What is Agentic Commerce?](#what-is-agentic-commerce)
- [UCP - Universal Commerce Protocol](#ucp---universal-commerce-protocol)
- [ACP - Agentic Commerce Protocol](#acp---agentic-commerce-protocol)
- [AP2 - Agent Payments Protocol](#ap2---agent-payments-protocol)
- [MPP - Machine Payments Protocol](#mpp---machine-payments-protocol)
- [AMP - Agentic Mobile Protocol](#amp---agentic-mobile-protocol)
- [A2A - Agent2Agent Protocol](#a2a---agent2agent-protocol)
- [How They Relate](#how-they-relate)
- [Crypto Payment Rails](#crypto-payment-rails)
- [Fiat Payment Rails](#fiat-payment-rails)
- [Tools & Plugins](#tools--plugins)
- [Developer Tools](#developer-tools)
- [Related Technologies](#related-technologies)
- [Learning Resources](#learning-resources)
  - [Platform Announcements](#-platform-announcements)
- [Market Sizing](#market-sizing)
- [Community Resources](#community-resources)
- [Adopters & Partners](#adopters--partners)

<br>

## What is Agentic Commerce?

Agentic commerce is the emerging paradigm where AI agents act on behalf of users to discover products, compare options, and complete purchases. Instead of humans clicking "buy" buttons on websites, AI assistants like ChatGPT, Gemini, or Copilot can browse catalogs, compare prices, and execute transactions autonomously.

**The Challenge:** Traditional e-commerce assumes a human is directly interacting with a website. When an AI agent acts on behalf of a user, new questions arise:
- How does a merchant know the agent is authorized to buy?
- How can agents from different platforms communicate?
- How do you prove the user actually wanted this purchase?

**The Solution:** These five protocols work together to create a secure, interoperable foundation for agent-led commerce.

<br>

## UCP - Universal Commerce Protocol

> End-to-end commerce standard for AI agent transactions

**Maintainers:** Google, Shopify, Etsy, Wayfair, Target, Walmart

### What is UCP?

UCP is "the common language for platforms, agents, and businesses." It defines building blocks for the entire commerce journey—from product discovery to checkout to order tracking—through a single, standardized interface.

**Key Concepts:**
- **Checkout** - Unified checkout sessions supporting complex cart logic, dynamic pricing, and tax calculations
- **Identity Linking** - OAuth 2.0-based secure connections between agents and user accounts (loyalty programs, saved addresses)
- **Order Management** - Real-time webhooks for shipment tracking, returns, and post-purchase updates

**Why it matters:** Without UCP, every agent platform would need custom integrations with every merchant (N×N problem). UCP collapses this into a single standard that any agent can use with any UCP-enabled merchant.

### 🎖️ Official Resources

- [UCP Documentation](https://ucp.dev/) - Protocol overview and guides
- [UCP GitHub](https://github.com/Universal-Commerce-Protocol/ucp) - Specification and source
- [UCP Specification](https://ucp.dev/specification/overview/) - Technical spec
- [UCP Playground](https://ucp.dev/playground/) - Interactive testing
- [UCP Roadmap](https://ucp.dev/documentation/roadmap/) - Development roadmap

### 🔌 Tools & Plugins

- [UCP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/ucp-agentic-commerce) - Claude Code plugin for UCP development
- [NotFair](https://notfair.co) - Google Ads MCP server. Connect Claude and AI agents to a Google Ads account: diagnose campaign performance, recommend optimizations, and execute approved changes via the Google Ads API. Source: github.com/nowork-studio/toprank. Free tier available.

### 🏪 Google Merchant Integration

- [Google Merchant UCP Guide](https://developers.google.com/merchant/ucp) - Google integration docs
- [Native Checkout Guide](https://developers.google.com/merchant/ucp/guides/checkout/native) - Native checkout implementation
- [Embedded Checkout Guide](https://developers.google.com/merchant/ucp/guides/checkout/embedded) - Embedded checkout implementation
- [UCP FAQ](https://developers.google.com/merchant/ucp/faq) - Frequently asked questions

### 🐍 SDKs & Implementations

- [UCP Samples](https://github.com/Universal-Commerce-Protocol/samples) - Reference implementations
- [UCP Python SDK](https://github.com/Universal-Commerce-Protocol/python-sdk) - Official Python SDK
- [UCP Conformance Tests](https://github.com/Universal-Commerce-Protocol/conformance) - Compliance testing
- [Shopify UCP](https://shopify.engineering/ucp) - Shopify's implementation
- [Shopify Agent Docs](https://shopify.dev/docs/agents) - Shopify agent integration

### 📰 Announcements

- [Under the Hood: UCP](https://developers.googleblog.com/under-the-hood-universal-commerce-protocol-ucp/) - Google Developers Blog
- [Agentic Commerce Tools](https://blog.google/products/ads-commerce/agentic-commerce-ai-tools-protocol-retailers-platforms/) - Google Blog
- [Shopify: AI Commerce at Scale](https://www.shopify.com/news/ai-commerce-at-scale) - Shopify announcement
- [Gemini Enterprise for CX](https://cloud.google.com/transform/a-new-era-agentic-commerce-retail-ai) - Google Cloud agentic retail platform
- [NRF 2026: The AI Platform Shift](https://blog.google/company-news/inside-google/message-ceo/nrf-2026-remarks/) - Google CEO remarks at NRF 2026

<br>

## ACP - Agentic Commerce Protocol

> Open standard for programmatic commerce between AI agents and businesses

**Maintainers:** OpenAI, Stripe

### What is ACP?

ACP enables AI agents to complete purchases on behalf of users directly within chat interfaces—like buying products without leaving a ChatGPT conversation. It powers features like "Instant Checkout" where users can discover and purchase items seamlessly.

**Key Concepts:**
- **Shared Payment Token (SPT)** - A secure, one-time-use token that lets agents initiate payments without ever seeing the user's card number. The token is scoped to a specific merchant and cart total.
- **Agentic Checkout** - A RESTful API (or MCP server) that merchants implement with four endpoints: create, update, complete, and cancel checkout
- **Delegated Payment** - The flow where Stripe (or another PSP) issues an SPT, and the agent passes it to the merchant to complete the transaction

**Why it matters:** ACP separates payment credentials from the agent entirely. The user pays through Stripe's secure interface, receives an SPT, and the agent never touches sensitive payment data—solving the PCI compliance challenge for AI commerce.

### 🎖️ Official Resources

- [Agentic Commerce Portal](https://www.agenticcommerce.dev/) - Main hub
- [ACP GitHub](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol) - Draft spec and examples
- [OpenAI Commerce Docs](https://developers.openai.com/commerce/) - OpenAI documentation
- [Stripe ACP Docs](https://docs.stripe.com/agentic-commerce) - Stripe integration
- [ACP Protocol Integration](https://docs.stripe.com/agentic-commerce/protocol) - Protocol details

### 🔌 Tools & Plugins

- [ACP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/acp-agentic-commerce) - Claude Code plugin for ACP development

### 📋 Specifications

- [Agentic Checkout Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/openapi/openapi.agentic_checkout.yaml) - Checkout OpenAPI spec
- [Delegated Payment Spec](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/spec/openapi/openapi.delegate_payment.yaml) - Payment OpenAPI spec
- [Governance Model](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/main/docs/governance.md) - Protocol governance

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

<br>

## AP2 - Agent Payments Protocol

> Secure payment authorization for agent-led transactions using cryptographic mandates

**Maintainers:** FIDO Alliance (donated by Google, April 2026) + 60 partners
**Latest version:** v0.2 (introduces "Human Not Present" autonomous payments)

### What is AP2?

AP2 solves a fundamental problem: **How do you prove a user actually authorized an agent to make a purchase?** Today's payment systems assume a human is clicking "buy." When an autonomous agent makes a purchase—especially when the user isn't present—there's no proof of intent.

AP2 introduces **Mandates**: tamper-proof, cryptographically-signed digital contracts that serve as verifiable evidence of user authorization.

**Key Concepts:**
- **Intent Mandate** - Pre-authorization for future purchases with constraints. Example: "Buy concert tickets under $100 when they go on sale." The agent can act autonomously within these bounds.
- **Cart Mandate** - Explicit approval for a specific cart. The user reviews the exact items and price, then signs. This is non-repudiable proof of intent.
- **Payment Mandate** - Signals to payment networks that an agent is involved, enabling appropriate risk assessment and dispute resolution.

**Why it matters:** When disputes arise ("I didn't authorize this!"), AP2 mandates provide cryptographic proof of exactly what the user approved. This protects merchants, payment providers, and users in the new world of autonomous agent purchases.

### 🎖️ Official Resources

- [AP2 Documentation](https://ap2-protocol.org/) - Protocol overview
- [AP2 GitHub](https://github.com/google-agentic-commerce/AP2) - Samples and demos
- [AP2 Specification](https://ap2-protocol.org/specification/) - Technical spec

### 🔌 Tools & Plugins

- [AP2 Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/ap2-agentic-payments) - Claude Code plugin for AP2 development

### 📚 Key Topics

- [What is AP2](https://ap2-protocol.org/topics/what-is-ap2/) - Overview
- [Core Concepts](https://ap2-protocol.org/topics/core-concepts/) - Mandates, roles, flows
- [Privacy & Security](https://ap2-protocol.org/topics/privacy-and-security/) - Security model
- [Life of a Transaction](https://ap2-protocol.org/topics/life-of-a-transaction/) - Transaction flows
- [AP2, A2A and MCP](https://ap2-protocol.org/topics/ap2-a2a-and-mcp/) - Protocol relationships
- [AP2 and x402](https://ap2-protocol.org/topics/ap2-and-x402/) - Crypto payments extension
- [A2A Extension](https://ap2-protocol.org/a2a-extension/) - A2A integration
- [FAQ](https://ap2-protocol.org/faq/) - Common questions
- [Glossary](https://ap2-protocol.org/glossary/) - Terminology
- [Roadmap](https://ap2-protocol.org/roadmap/) - What's coming

### 💻 Code Samples

- [Python Samples](https://github.com/google-agentic-commerce/AP2/tree/main/samples/python) - Python examples
- [Android Samples](https://github.com/google-agentic-commerce/AP2/tree/main/samples/android) - Android examples

### 📰 Announcements

- [Announcing AP2](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol) - Google Cloud Blog
- [Google Donates AP2 to FIDO Alliance](https://blog.google/products-and-platforms/platforms/google-pay/agent-payments-protocol-fido-alliance/) - April 2026, also announces v0.2 with "Human Not Present" flow
- [FIDO Alliance Forms Agentic Standards Working Groups](https://fidoalliance.org/fido-alliance-to-develop-standards-for-trusted-ai-agent-interactions/) - April 28, 2026 — New **Agentic Authentication TWG** (chaired by CVS Health, Google, OpenAI; vice-chaired by Amazon, Google, Okta) and existing **Payments TWG** (chaired by Mastercard, Visa) will develop interoperable standards from AP2 + Mastercard's Verifiable Intent
- [PYMNTS: Google + Mastercard Contribute to FIDO](https://www.pymnts.com/artificial-intelligence-2/2026/google-and-mastercard-contribute-agentic-commerce-standards-to-fido-alliance/) - Industry coverage of the contributions

<br>

## MPP - Machine Payments Protocol

> Open standard for autonomous agent micropayments

**Co-Authors:** Stripe, Tempo

### What is MPP?

MPP is an open standard for autonomous agent micropayments. It introduces a **sessions primitive** that allows AI agents to initiate, manage, and settle small-value transactions without human intervention at each step.

**Key Concepts:**
- **Sessions** - A primitive that bundles multiple micropayments into a single authorized context, reducing friction for high-frequency agent transactions
- **Micropayments** - Designed for small-value, high-volume payments typical of agent-to-agent and agent-to-service interactions
- **Multi-Rail Support** - Supports card networks, digital wallets, and Lightning Network for flexible settlement

**Why it matters:** As AI agents consume paid APIs, purchase digital goods, and transact with other agents autonomously, traditional checkout flows break down. MPP provides a purpose-built payment layer for machine-to-machine commerce at scale.

### 🎖️ Official Resources

- [Stripe Blog: Introducing MPP](https://stripe.com/blog/machine-payments-protocol) - Launch announcement
- [MPP Stripe Docs](https://docs.stripe.com/payments/machine/mpp) - Integration documentation
- [Visa Card Spec & SDK for MPP](https://corporate.visa.com/en/sites/visa-perspectives/innovation/visa-card-specification-sdk-for-machine-payments-protocol.html) - Visa card specification and SDK

### 🔌 Tools & Plugins

- [MPP Claude Code Plugin](https://github.com/OrcaQubits/agentic-commerce-claude-plugins/tree/main/stripe-mpp) - Claude Code plugin for MPP development

### 📰 Announcements

- [Fortune: Tempo Blockchain + MPP Launch](https://fortune.com/2026/03/18/stripe-tempo-paradigm-mpp-ai-payments-protocol/) - Stripe and Tempo partnership
- [PYMNTS: Visa Scales via MPP](https://www.pymnts.com/visa/2026/visa-scales-agentic-commerce-through-stripe-protocol-collaboration/) - Visa scaling through MPP collaboration

<br>

## AMP - Agentic Mobile Protocol

> Open-source mobile-first agentic payment framework for digital wallets, super apps, and wearables

**Maintainers:** Ant International (Alipay+ ecosystem)
**Launched:** April 2026

### What is AMP?

AMP is the first agentic payment protocol designed natively for mobile interfaces — smartphones, smartwatches, AR glasses, and in-car systems — rather than card-based desktop checkout. It establishes a universal, auditable standard for AI agents to transact across digital wallets and super apps.

**Key Concepts:**
- **KYA (Know Your Agent) Framework** - Establishes an agent's digital identity and certifies its authorized capabilities, parallel to KYC for humans
- **Agent Trust Rating** - Dynamic risk-management score that determines an agent's trustworthiness and controls its level of autonomy
- **Money-back Guarantee** - Every agent-initiated transaction is backed by a refund mechanism for payment partners in cases of account takeover
- **Cross-device Compatibility** - Designed for non-card form factors absent from traditional payment rails

**Why it matters:** The Alipay+ network reaches 1.8B user accounts and 150M merchants globally — primarily across APAC. AMP gives this footprint an agentic-commerce layer and complements card-based protocols (Visa TAP, Mastercard Agent Pay) for emerging markets where mobile wallets dominate.

### 📰 Announcements

- [Ant International Launches AMP](https://www.businesswire.com/news/home/20260427209524/en/Ant-International-Launches-Open-Sourced-Agentic-Mobile-Protocol-to-Drive-AI-Commerce) - BusinessWire, April 27, 2026
- [PYMNTS: Agentic AI Gets Its Own Payment Protocol](https://www.pymnts.com/artificial-intelligence-2/2026/agentic-ai-gets-its-own-payment-protocol/) - Industry coverage, April 30, 2026

<br>

## A2A - Agent2Agent Protocol

> Open standard for AI agent interoperability and communication

**Maintainers:** Google (Linux Foundation)

### What is A2A?

A2A enables AI agents built on different frameworks, by different companies, running on separate servers to discover each other's capabilities and collaborate on tasks—**as agents, not just as tools.**

Think of it as the "common language" that lets a travel planning agent talk to a flight booking agent, a hotel agent, and a car rental agent to coordinate a complete trip.

**Key Concepts:**
- **Agent Card** - A JSON document that agents publish describing who they are, what they can do, and how to communicate with them. It's like a business card for AI agents.
- **Tasks** - The fundamental unit of work. Tasks have a lifecycle (submitted → working → completed/failed) and can be long-running with progress updates.
- **Messages & Parts** - Agents communicate through messages containing different content types: text, files, or structured data.
- **Update Mechanisms** - Three ways to get task updates: polling (simple), streaming (real-time), or push notifications (webhooks for async work).

**A2A vs MCP:** MCP (Model Context Protocol) connects agents to **tools and data**. A2A connects **agents to other agents**. They're complementary—an agent might use MCP to access a database and A2A to delegate work to a specialized agent.

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

<br>

## How They Relate

```
User → AI Agent → A2A (agent discovery & coordination)
                → UCP/ACP (commerce actions)
                → AP2 (payment authorization)
                → MPP (agent micropayments)
                → Payment Rails (Stripe, Visa TAP, Mastercard, PayPal, x402, L402)
                → Merchants & Payment Networks
```

| Protocol | Layer | Purpose |
|----------|-------|---------|
| **A2A** | Communication | Agents discover and talk to each other |
| **UCP** | Commerce | End-to-end commerce (Google ecosystem) |
| **ACP** | Commerce | Agent checkout (OpenAI/Stripe ecosystem) |
| **AP2** | Payments | Secure payment authorization with mandates |
| **MPP** | Payments | Autonomous agent micropayments via sessions |
| **AMP** | Payments | Mobile-first agentic payments via digital wallets (Alipay+) |
| **x402/L402** | Crypto Rails | Stablecoin and Lightning Network payments for agents |
| **Visa TAP / Mastercard Agent Pay / PayPal Agent Ready** | Fiat Rails | Card network and wallet infrastructure for agent transactions |

### Example: Planning a Trip

1. **A2A** - Your personal agent discovers a flight agent, hotel agent, and car rental agent
2. **A2A** - Agents collaborate to find options within your $700 budget
3. **AP2** - You create an Intent Mandate: "Book travel under $700 total"
4. **UCP/ACP** - Each agent executes checkout with their respective merchants
5. **AP2** - Cart Mandates are signed for each booking, providing proof of your approval
6. **Result** - Three coordinated bookings, all cryptographically tied to your authorization

### UCP vs ACP

Both enable commerce, but target different ecosystems:
- **UCP** - Google AI surfaces (Search AI Mode, Gemini), supports identity linking, uses AP2 for payments
- **ACP** - OpenAI/ChatGPT ecosystem, uses Shared Payment Tokens via Stripe

Merchants wanting maximum reach may implement both.

<br>

## Crypto Payment Rails

### x402

> HTTP 402 stablecoin payments over HTTP — no API keys, accounts, or subscriptions

**Foundation:** Coinbase (co-founded with Cloudflare)

x402 leverages HTTP's `402 Payment Required` status code for instant stablecoin payments. It requires no API keys, accounts, or subscriptions—just a wallet. x402 serves as the crypto payment rail within the [AP2 protocol](https://ap2-protocol.org/topics/ap2-and-x402/).

- [x402 Documentation](https://www.x402.org/) - Protocol overview and ecosystem
- [x402 GitHub](https://github.com/coinbase/x402) - Specification, SDKs, and examples
- [x402 Specification](https://github.com/coinbase/x402/tree/main/specs) - Technical spec
- [Coinbase Developer Docs](https://docs.cdp.coinbase.com/x402/welcome) - Quickstart guide
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

> Practical L402 toolkit for AI agents — MCP server, CLI, Python SDK

[Fewsats](https://github.com/fewsats) provides the tooling layer that makes L402 accessible to AI agents, including an MCP server for direct agent integration.

- [Fewsats MCP Server](https://github.com/fewsats/fewsats-mcp) - MCP server for AI agent L402 payments
- [L402 Python SDK](https://github.com/Fewsats/L402-python) - Python SDK for L402 agent payments

<br>

## Fiat Payment Rails

### Visa — Intelligent Commerce

> Trusted Agent Protocol (TAP) — authentication framework for agent-to-network communication

**Initiative:** Visa "Intelligent Commerce" program
**Authentication:** HTTP Message Signatures (RFC 9421)
**Status:** 30+ partners in sandbox, early 2026

Visa's TAP provides the authentication layer for AI agents to interact with card networks directly, using cryptographic HTTP message signatures.

- [Intelligent Commerce Developer Program](https://developer.visa.com/capabilities/visa-intelligent-commerce) - Visa agent commerce program
- [Trusted Agent Protocol (TAP)](https://developer.visa.com/capabilities/trusted-agent-protocol) - TAP documentation
- [TAP GitHub](https://github.com/visa/trusted-agent-protocol) - Reference implementation and spec
- [Visa Launches Validator Node on Tempo](https://investor.visa.com/news/news-details/2026/Visa-Launches-Validator-Node-on-Tempo-Blockchain/default.aspx) - April 14, 2026 — Visa runs validator on Stripe's Tempo chain (TradFi/DeFi crossover)
- [Visa Agentic Ready Expands to Canada](https://www.globenewswire.com/news-release/2026/05/05/3287953/0/en/Visa-Expands-Agentic-Ready-Program-to-Canada-to-Advance-AI-Driven-Commerce.html) - May 5, 2026 — BMO, CIBC, RBC, Scotiabank, TD as early adopters

### Mastercard — Agent Pay

> Agentic Tokens — scoped, time-limited payment credentials for AI agents

Mastercard Agent Pay issues Agentic Tokens: scoped, time-limited credentials that allow agents to initiate payments within defined boundaries. Includes an official MCP server for API access.

- [Agent Pay Developer Docs](https://developer.mastercard.com/mastercard-checkout-solutions/documentation/use-cases/agent-pay/) - Integration documentation
- [Mastercard Launches Agent Suite](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Suite-to-Ready-Enterprises-for-a-New-Era/default.aspx) - January 27, 2026 — Enterprise toolkit bundling Agent Pay with deployment tools (GA Q2 2026)
- [Mastercard Verifiable Intent (contributed to FIDO Alliance)](https://www.pymnts.com/artificial-intelligence-2/2026/google-and-mastercard-contribute-agentic-commerce-standards-to-fido-alliance/) - April 28, 2026 — Co-developed with Google, designed to work with AP2

### American Express — Agentic Commerce Experiences (ACE)

> Developer kit + Agent Purchase Protection — first card network with consumer-facing dispute coverage for agent errors

**Launched:** April 14, 2026
**Partners:** OpenAI, Google, Microsoft, PayPal, Stripe + 11 others

Amex ACE is a developer kit with five components: agent registration, account enablement, intent intelligence (creating an "intent contract" + Proof of Intent Token), single-use payment credentials bound to intent and constraints, and cart context (banks/brands compare submitted cart vs. intent). Pairs with **Amex Agent Purchase Protection** — industry-first coverage for charges arising from AI agent errors when both card member and merchant acted correctly.

- [American Express Debuts ACE Developer Kit](https://www.digitalcommerce360.com/2026/04/14/american-express-agentic-commerce-developer-kit-purchase-protection/) - DigitalCommerce360 coverage of launch
- [PYMNTS: Amex to Back Purchases by Customer's AI Agents](https://www.pymnts.com/artificial-intelligence-2/2026/american-express-to-back-purchases-made-by-customers-ai-agents/) - Coverage of Agent Purchase Protection
- [Amex Agentic Commerce Hub](https://www.americanexpress.com/en-us/company/agentic-commerce/) - Official Amex page (primary source)

### PayPal — Agent Ready

> ACP-based agent payments for existing PayPal and Braintree merchants

PayPal's Agent Ready enables existing merchants to accept agent-initiated payments with minimal integration overhead. PayPal manages security and PCI compliance. Includes Store Sync for catalog integration and an Agent Toolkit for programmatic access.

- [Agentic Commerce Overview](https://docs.paypal.ai/growth/agentic-commerce/overview) - PayPal agentic commerce docs
- [Agent Ready Documentation](https://docs.paypal.ai/growth/agentic-commerce/agent-ready) - Agent Ready integration guide
- [Store Sync](https://docs.paypal.ai/growth/agentic-commerce/store-sync/create-a-product-catalog) - Product catalog and cart integration
- [Agent Toolkit](https://github.com/paypal/agent-toolkit) - PayPal agent API integration via function calling

### Cloudflare — Agents SDK

> Infrastructure SDK with native x402 support and upcoming Visa/Mastercard agent protocol integration

Cloudflare's Agents SDK embeds payment rails directly into the edge infrastructure layer, currently supporting x402 with Visa and Mastercard agent protocols on the roadmap.

- [Agents SDK Documentation](https://developers.cloudflare.com/agents/) - Full SDK docs
- [x402 Integration](https://developers.cloudflare.com/agents/x402/) - x402 in the Agents SDK
- [Secure Agentic Commerce](https://blog.cloudflare.com/secure-agentic-commerce/) - Visa and Mastercard protocol support announcement

<br>

## Tools & Plugins

- [Agentic Commerce Claude Plugins](https://github.com/OrcaQubits/agentic-commerce-claude-plugins) - Claude Code plugins for agentic commerce protocol development (UCP, ACP, AP2, A2A)

<br>

## Developer Tools

### ✅ UCP Validation & Testing

- [UCP Playground](https://ucp.dev/playground/) - Official testing environment
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

- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - Agent-to-tool communication standard
- [MCP GitHub](https://github.com/modelcontextprotocol) - MCP repositories
- [OAuth 2.0](https://oauth.net/2/) - Authorization framework used by UCP

<br>

## Learning Resources

### 📖 Official Guides

- [UCP Complete Guide](https://a2aprotocol.ai/blog/2026-universal-commerce-protocol) - 2026 UCP overview
- [A2A Complete Guide](https://a2aprotocol.ai/blog/2025-full-guide-a2a-protocol) - 2025 A2A overview
- [A2A Advanced Features](https://a2aprotocol.ai/blog/2025-part2-full-guide-a2a-protocol) - Deep dive Part 2

### 📖 Third-Party Analysis

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

#### OpenAI
- [Powering Product Discovery in ChatGPT](https://openai.com/index/powering-product-discovery-in-chatgpt/) - Pivot from Instant Checkout to discovery (March 2026)

#### Microsoft
- [Microsoft Agentic AI for Retail](https://news.microsoft.com/source/2026/01/08/microsoft-propels-retail-forward-with-agentic-ai-capabilities-that-power-intelligent-automation-for-every-retail-function/) - Copilot Checkout, Brand Agents, Dynamics 365

#### Anthropic
- [Claude Marketplace Launch](https://siliconangle.com/2026/03/06/anthropic-launches-claude-marketplace-third-party-cloud-services/) - Third-party services in Claude (Snowflake, GitLab, Harvey AI, Replit, Lovable Labs), March 2026
- [Project Deal: Agent-to-Agent Commerce Experiment](https://www.anthropic.com/features/project-deal) - 69-employee marketplace pilot, 186 deals, $4K GMV — first published study on how model quality affects negotiation outcomes

#### Meta
- [TechCrunch: Zuckerberg Teases Agentic Commerce](https://techcrunch.com/2026/01/28/zuckerberg-teases-agentic-commerce-tools-and-major-ai-rollout-in-2026/) - Meta Q4 earnings reveals 2026 AI roadmap

#### Amazon
- [Modern Retail: Buy for Me Analysis](https://www.modernretail.co/technology/brands-are-upset-that-buy-for-me-is-featuring-their-products-on-amazon-without-permission/) - Deep dive on Amazon's agentic purchasing

#### Regulatory
- [UK ICO: Agentic Commerce Report](https://ico.org.uk/about-the-ico/media-centre/news-and-blogs/2026/01/ai-ll-get-that/) - Tech Futures report on AI shopping agents and data protection

<br>

## Market Sizing

- [ICSC + McKinsey: $1T US Agentic Sales by 2030](https://www.paymentsdive.com/news/agentic-commerce-us-one-trillion-2030/819490/) - Most-cited TAM forecast for US B2C agentic commerce

<br>

## Community Resources

### 📚 Awesome Lists

- [Awesome UCP](https://github.com/Upsonic/awesome-ucp) - Curated UCP resources
- [Awesome Agentic Patterns](https://github.com/nibzard/awesome-agentic-patterns) - Agentic AI patterns
- [Awesome Agentic Commerce](https://github.com/damoahdominic/awesome-agentic-commerce/) - Agentic commerce protocols resources

### 🌐 Community Sites

- [A2A Protocol Community](https://a2aprotocol.ai/) - A2A guides and tutorials
- [Agent2Agent Info](https://agent2agent.info/) - A2A code examples
- [Agentic Commerce Pro](https://agenticcommerce.pro/) - ACP community examples
- [ACP Ready Directory](https://www.acpready.com/) - ACP-ready platforms and providers directory

### 📬 Newsletters

- [Agentic Commerce Frontier](https://agentcommerce.substack.com/) - Weekly agentic commerce newsletter

### 💬 Discussions

- [UCP GitHub Discussions](https://github.com/Universal-Commerce-Protocol/ucp/discussions)
- [ACP GitHub Discussions](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/discussions)
- [A2A GitHub Discussions](https://github.com/a2aproject/A2A/discussions)

<br>

## Adopters & Partners

### UCP Co-Developers
- [x] Google
- [x] Shopify
- [x] Etsy
- [x] Wayfair
- [x] Target
- [x] Walmart

### UCP Endorsers
- [x] Adyen
- [x] American Express
- [x] Best Buy
- [x] Flipkart
- [x] Kroger
- [x] Lowe's
- [x] Macy's
- [x] Mastercard
- [x] Papa Johns
- [x] Sephora
- [x] Stripe
- [x] The Home Depot
- [x] Visa
- [x] Woolworths
- [x] Zalando

### ACP Partners
- [x] OpenAI
- [x] Stripe
- [x] Microsoft Copilot
- [x] Anthropic
- [x] Perplexity
- [x] Salesforce
- [x] Vercel
- [x] Replit
- [x] Fiserv (Mastercard Agent Pay integration)

### AP2 Payment Partners
- [x] Mastercard
- [x] Visa
- [x] American Express
- [x] PayPal
- [x] Adyen
- [x] Coinbase
- [x] Revolut
- [x] Worldpay

### A2A Supporters
- [x] Google (Linux Foundation governance)
- [x] 150+ organizations
- [x] Atlassian
- [x] MongoDB
- [x] ServiceNow

### Visa Agentic Ready

**Europe:** Barclays, HSBC UK, Banco Santander, Revolut, Commerzbank, Nationwide, Nexi, Raiffeisen, DZ Bank — 21+ issuers enrolled
**Canada (May 2026):** BMO, CIBC, RBC, Scotiabank, TD
**APAC + LatAm:** 85+ partners (incl. Alliance Bank Malaysia, CIMB, Maybank)

### Other Agentic Commerce Platforms
- [x] Amazon (Shop Direct / Buy for Me / Rufus)
- [x] Meta (Announced agentic commerce tools for 2026)
- [x] Microsoft (Copilot Checkout, Brand Agents)
- [x] Tempo (MPP co-author, blockchain-based agent payments)
- [x] Ant International (AMP, Alipay+ ecosystem — 1.8B users, 150M merchants)
- [x] Anthropic (Claude Marketplace, Project Deal experiment)

---

## License

This compilation is provided under the [MIT License](./LICENSE).

The protocols themselves are Apache 2.0 licensed by their respective maintainers.
