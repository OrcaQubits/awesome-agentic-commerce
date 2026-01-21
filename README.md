# Awesome Agentic Commerce [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for agentic commerce protocols: UCP, ACP, AP2, and A2A

This repository is a **reference point** to official resources. It does not own or maintain these protocols. For authoritative information, always consult the official documentation.

## Contents

- [What is Agentic Commerce?](#what-is-agentic-commerce)
- [UCP - Universal Commerce Protocol](#ucp---universal-commerce-protocol)
- [ACP - Agentic Commerce Protocol](#acp---agentic-commerce-protocol)
- [AP2 - Agent Payments Protocol](#ap2---agent-payments-protocol)
- [A2A - Agent2Agent Protocol](#a2a---agent2agent-protocol)
- [How They Relate](#how-they-relate)
- [Developer Tools](#developer-tools)
- [Related Technologies](#related-technologies)
- [Learning Resources](#learning-resources)
- [Community Resources](#community-resources)
- [Adopters & Partners](#adopters--partners)

<br>

## What is Agentic Commerce?

Agentic commerce is the emerging paradigm where AI agents act on behalf of users to discover products, compare options, and complete purchases. Instead of humans clicking "buy" buttons on websites, AI assistants like ChatGPT, Gemini, or Copilot can browse catalogs, compare prices, and execute transactions autonomously.

**The Challenge:** Traditional e-commerce assumes a human is directly interacting with a website. When an AI agent acts on behalf of a user, new questions arise:
- How does a merchant know the agent is authorized to buy?
- How can agents from different platforms communicate?
- How do you prove the user actually wanted this purchase?

**The Solution:** These four protocols work together to create a secure, interoperable foundation for agent-led commerce.

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
                → Merchants & Payment Networks
```

| Protocol | Layer | Purpose |
|----------|-------|---------|
| **A2A** | Communication | Agents discover and talk to each other |
| **UCP** | Commerce | End-to-end commerce (Google ecosystem) |
| **ACP** | Commerce | Agent checkout (OpenAI/Stripe ecosystem) |
| **AP2** | Payments | Secure payment authorization with mandates |

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
- [AP2 Guide (DEV)](https://dev.to/czmilo/2025-complete-guide-to-ai-agent-payments-how-the-ap2-protocol-is-reshaping-intelligent-commerce-2imf) - DEV Community guide
- [A2A Guide (DEV)](https://dev.to/czmilo/2025-complete-guide-agent2agent-a2a-protocol-the-new-standard-for-ai-agent-collaboration-1pph) - DEV Community guide

### 📰 News Coverage

- [TechCrunch: UCP Launch](https://techcrunch.com/2026/01/11/google-announces-a-new-protocol-to-facilitate-commerce-using-ai-agents/) - UCP announcement
- [Search Engine Land: UCP](https://searchengineland.com/google-universal-commerce-protocol-467290) - UCP coverage
- [InfoQ: A2A Open Source](https://www.infoq.com/news/2025/04/google-agentic-a2a/) - A2A coverage
- [FinTech Magazine: AP2](https://fintechmagazine.com/news/agentic-pay-systems-googles-agent-payments-protocol) - AP2 coverage
- [MarkTechPost: UCP](https://www.marktechpost.com/2026/01/12/google-ai-releases-universal-commerce-protocol-ucp-an-open-source-standard-designed-to-power-the-next-generation-of-agentic-commerce/) - Technical coverage
- [SEJ: ACP & UCP for SEO](https://www.searchenginejournal.com/agentic-commerce-what-seos-need-to-consider-acp-ucp/563503/) - SEO considerations

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
- [x] Macy's
- [x] Mastercard
- [x] Sephora
- [x] Stripe
- [x] The Home Depot
- [x] Visa
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

---

## License

This compilation is provided under the [MIT License](./LICENSE).

The protocols themselves are Apache 2.0 licensed by their respective maintainers.
