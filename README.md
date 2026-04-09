# Awesome Agentic Commerce [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for agentic commerce protocols: UCP, ACP, AP2, MPP, and A2A

This repository is a **reference point** to official resources. It does not own or maintain these protocols. For authoritative information, always consult the official documentation.

## Contents

- [What is Agentic Commerce?](#what-is-agentic-commerce)
- [UCP - Universal Commerce Protocol](#ucp---universal-commerce-protocol)
- [ACP - Agentic Commerce Protocol](#acp---agentic-commerce-protocol)
- [AP2 - Agent Payments Protocol](#ap2---agent-payments-protocol)
- [MPP - Machine Payments Protocol](#mpp---machine-payments-protocol)
- [A2A - Agent2Agent Protocol](#a2a---agent2agent-protocol)
- [How They Relate](#how-they-relate)
- [Crypto Payment Rails](#crypto-payment-rails)
- [Fiat Payment Rails](#fiat-payment-rails)
- [Tools & Plugins](#tools--plugins)
- [Developer Tools](#developer-tools)
- [Related Technologies](#related-technologies)
- [Learning Resources](#learning-resources)
  - [Major Platform Announcements (January 2026)](#-major-platform-announcements-january-2026)
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
- [OpenAI Shifts Checkout Plans](https://www.digitalcommerce360.com/2026/03/06/openai-shifts-checkout-plans-agentic-commerce-strategy/) - OpenAI agentic commerce strategy pivot
- [CNBC: OpenAI's Agentic Shopping Stumbled](https://www.cnbc.com/2026/03/20/open-ai-agentic-shopping-etsy-shopify-walmart-amazon.html) - Challenges with early agentic shopping

<br>

## AP2 - Agent Payments Protocol

> Secure payment authorization for agent-led transactions using cryptographic mandates

**Maintainers:** Google + 60 partners

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

### Mastercard — Agent Pay

> Agentic Tokens — scoped, time-limited payment credentials for AI agents

Mastercard Agent Pay issues Agentic Tokens: scoped, time-limited credentials that allow agents to initiate payments within defined boundaries. Includes an official MCP server for API access.

- [Agent Pay Developer Docs](https://developer.mastercard.com/mastercard-checkout-solutions/documentation/use-cases/agent-pay/) - Integration documentation

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
- [Human Pages](https://humanpages.ai) - The open directory AI agents use to hire humans for real-world tasks. x402 pay-per-use pricing in USDC on Base.

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
- [AP2 Guide (DEV)](https://dev.to/czmilo/2025-complete-guide-to-ai-agent-payments-how-the-ap2-protocol-is-reshaping-intelligent-commerce-2imf) - DEV Community guide
- [A2A Guide (DEV)](https://dev.to/czmilo/2025-complete-guide-agent2agent-a2a-protocol-the-new-standard-for-ai-agent-collaboration-1pph) - DEV Community guide

### 📰 News Coverage

- [TechCrunch: UCP Launch](https://techcrunch.com/2026/01/11/google-announces-a-new-protocol-to-facilitate-commerce-using-ai-agents/) - UCP announcement
- [Search Engine Land: UCP](https://searchengineland.com/google-universal-commerce-protocol-467290) - UCP coverage
- [InfoQ: A2A Open Source](https://www.infoq.com/news/2025/04/google-agentic-a2a/) - A2A coverage
- [FinTech Magazine: AP2](https://fintechmagazine.com/news/agentic-pay-systems-googles-agent-payments-protocol) - AP2 coverage
- [MarkTechPost: UCP](https://www.marktechpost.com/2026/01/12/google-ai-releases-universal-commerce-protocol-ucp-an-open-source-standard-designed-to-power-the-next-generation-of-agentic-commerce/) - Technical coverage
- [SEJ: ACP & UCP for SEO](https://www.searchenginejournal.com/agentic-commerce-what-seos-need-to-consider-acp-ucp/563503/) - SEO considerations
- [Marketing Brew: CES & NRF Announcements](https://www.marketingbrew.com/stories/2026/01/16/agentic-ai-announcements-ces-nrf) - Major agentic AI announcements roundup
- [Modern Retail: AI Shopping Agent Wars](https://www.modernretail.co/technology/why-the-ai-shopping-agent-wars-will-heat-up-in-2026/) - 2026 industry outlook
- [Commercetools: AI Trends Shaping Agentic Commerce](https://commercetools.com/blog/ai-trends-shaping-agentic-commerce) - 7 AI trends for 2026
- [Ecommerce Times: Unified Platforms & Agentic AI](https://www.ecommercetimes.com/story/unified-platforms-and-agentic-ai-will-define-e-commerce-in-2026-178463.html) - 2026 e-commerce outlook

### 🏢 Major Platform Announcements (January 2026)

#### Google
- [A New Era of Agentic Commerce](https://cloud.google.com/transform/a-new-era-agentic-commerce-retail-ai) - Google Cloud Blog on retail AI
- [Gemini Enterprise for CX](https://www.googlecloudpresscorner.com/2026-01-11-Google-Cloud-Brings-Shopping-and-Customer-Service-Together-with-Gemini-Enterprise-for-Customer-Experience) - Official press release
- [NRF 2026 Remarks](https://blog.google/company-news/inside-google/message-ceo/nrf-2026-remarks/) - Google CEO message on AI platform shift
- [CNBC: Google Bets on AI-Powered Retail](https://www.cnbc.com/2026/01/11/google-launches-universal-commerce-protocol-bets-on-ai-powered-retail.html) - UCP launch coverage

#### Microsoft
- [Microsoft Agentic AI for Retail](https://news.microsoft.com/source/2026/01/08/microsoft-propels-retail-forward-with-agentic-ai-capabilities-that-power-intelligent-automation-for-every-retail-function/) - Official announcement on Copilot Checkout, Brand Agents, and Dynamics 365

#### Meta
- [TechCrunch: Zuckerberg Teases Agentic Commerce](https://techcrunch.com/2026/01/28/zuckerberg-teases-agentic-commerce-tools-and-major-ai-rollout-in-2026/) - Meta Q4 earnings reveals 2026 AI roadmap

#### Amazon
- [CNBC: Amazon Buy for Me](https://www.cnbc.com/2026/01/06/amazons-ai-shopping-tool-sparks-backlash-from-some-online-retailers.html) - Coverage of Amazon's AI shopping agent
- [Modern Retail: Buy for Me Analysis](https://www.modernretail.co/technology/brands-are-upset-that-buy-for-me-is-featuring-their-products-on-amazon-without-permission/) - Deep dive on Amazon's agentic purchasing

#### Regulatory
- [UK ICO: Agentic Commerce Report](https://ico.org.uk/about-the-ico/media-centre/news-and-blogs/2026/01/ai-ll-get-that/) - Tech Futures report on AI shopping agents and data protection

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

### Visa Agentic Ready (Europe)
- [x] Barclays
- [x] HSBC UK
- [x] Banco Santander
- [x] Revolut
- [x] Commerzbank
- [x] Nationwide Building Society
- [x] Nexi Group
- [x] Raiffeisen Bank International
- [x] DZ Bank
- [x] + 12 additional issuers (21 total enrolled)

### Other Agentic Commerce Platforms
- [x] Amazon (Shop Direct / Buy for Me)
- [x] Meta (Announced agentic commerce tools for 2026)
- [x] Microsoft (Copilot Checkout, Brand Agents)
- [x] Tempo (MPP co-author, blockchain-based agent payments)

---

## License

This compilation is provided under the [MIT License](./LICENSE).

The protocols themselves are Apache 2.0 licensed by their respective maintainers.
