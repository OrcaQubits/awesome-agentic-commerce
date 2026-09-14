# Contributing

Thanks for considering a contribution. This document exists so you can tell, before spending time on a pull request, whether it is likely to be accepted.

## What this list is

> This repository is a **reference point** to official resources. It does not own or maintain these protocols.

That line from the README is the whole scope, and every decision here follows from it. This list indexes **the protocols themselves** — specifications, official SDKs and documentation, the bodies that govern them, and independent analysis of how they work.

It is **not** a directory of products and services built on top of those protocols. Those directories are valuable and several exist; this is not one of them.

### The test

When evaluating an entry, the question is:

> Does this help someone **understand or implement a protocol**, or does it **offer them a service that uses one**?

The first belongs here. The second does not — regardless of how good the service is.

## What gets accepted

- **Official protocol resources** — specifications, changelogs, reference implementations, conformance suites, official SDKs, governance documents
- **Primary announcements** — a standards body, protocol maintainer, or network publishing something material about a protocol in this list
- **Independent analysis** — write-ups that explain how a protocol works, compare protocols, or document a real implementation experience, written vendor-neutrally
- **Protocol-level developer tools** — validators, conformance checkers, inspectors, and debuggers that test *compliance with a spec*, not services that *use* a spec
- **Corrections** — fixing an outdated version number, a renamed concept, a dead link, or a claim that has since stopped being true. These are the most welcome contributions of all.

## What gets declined

- **Your own product, API, or service.** This is the most common submission and the most common decline. See below.
- **Hosted services built on a protocol** — an x402-paid API, an MCP server exposing a commercial data product, a paid agent marketplace. Using a protocol does not make something a resource *about* that protocol.
- **New sections created to house your own entry.** Adding a section so your product has somewhere to live is declined even where the entry might otherwise fit.
- **Paid-placement directories.** Anything that monetises listing other projects has a structural conflict with a curated list.
- **Off-topic tooling.** MCP being involved is not sufficient. This list covers agentic *commerce* — discovery, transaction, and settlement on a user's behalf. General MCP servers belong in [`awesome-mcp-servers`](https://github.com/punkpeye/awesome-mcp-servers).
- **Link-only PRs with no description**, or entries whose description is marketing copy rather than a factual summary.

## Self-promotion

You may submit something you built, but:

1. **Disclose it.** State your affiliation in the PR description. Undisclosed affiliation that becomes apparent during review is grounds for declining on its own.
2. **It still has to pass the scope test above.** In practice this means open-source protocol infrastructure — an SDK, a reference implementation, a validator — rather than a hosted commercial service.
3. **One submission.** Do not open separate PRs for each of your products, and do not resubmit a declined entry under a different framing.

If your project is a service rather than infrastructure, the [x402 Foundation](https://x402.org/) ecosystem pages, Coinbase's Agent.market, and the [ACP Ready directory](https://www.acpready.com/) are built for that purpose and will reach a better-matched audience.

## Entry format

Match the surrounding entries. The convention throughout is:

```markdown
- [Name](https://example.com) - Factual description, sentence case, no trailing period.
```

- A plain hyphen separates name and description — not an em-dash or a colon
- Keep descriptions to one line. Say what the thing *is*, not why it is great
- No emoji markers on individual entries. This list does not use the `📇 ☁️` convention from other awesome lists
- No pricing, no performance claims, no superlatives
- Place the entry in the existing section it belongs to. If you believe a new section is genuinely needed, open an issue first

## Accuracy

This field moves quickly and stale entries are worse than no entry. Before submitting:

- **Check every link resolves.** Dead and redirected links are the most common defect in this list's history
- **Verify version numbers and product names are current.** Protocols in this list have renamed core concepts, restructured their documentation, and retired flagship products within a single year — and much third-party writing has not caught up
- **Do not cite a retired product as though it were live**
- **Be internally consistent.** If you state a number, state the same number everywhere
- **Point at primary sources** where one exists. Prefer a specification or an official changelog over secondary coverage of it

## Submitting

1. One logical change per pull request
2. Fill in the pull request template
3. Explain *why* the entry belongs here, not just what it is

## What happens next

Pull requests are reviewed against this document. If yours is declined you will get a specific reason rather than a silent close. If it is declined on scope, that is a category judgement about this list — not an assessment of your work.

Corrections and dead-link fixes are reviewed fastest.
