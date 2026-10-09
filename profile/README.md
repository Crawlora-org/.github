# Crawlora

Crawlora provides developer APIs for structured public web data. Use it to
collect normalized search, marketplace, social, finance, media, reviews, and
geodata signals without maintaining scraper infrastructure yourself.

## Start Here

- Website: [https://crawlora.net](https://crawlora.net?utm_source=github&utm_medium=referral&utm_campaign=github-org-profile&utm_content=website)
- API docs: [https://crawlora.net/docs](https://crawlora.net/docs?utm_source=github&utm_medium=referral&utm_campaign=github-org-profile&utm_content=api-docs)
- Playground: [https://crawlora.net/playground](https://crawlora.net/playground?utm_source=github&utm_medium=referral&utm_campaign=github-org-profile&utm_content=playground)
- Pricing: [https://crawlora.net/pricing](https://crawlora.net/pricing?utm_source=github&utm_medium=referral&utm_campaign=github-org-profile&utm_content=pricing)
- API status: https://uptime.crawlora.net/status/crawlora-api
- Support: support@crawlora.net

The public API is available at:

```text
https://api.crawlora.net/api/v1
```

Most endpoints use API key authentication:

```sh
curl -sS \
  -H "x-api-key: $CRAWLORA_API_KEY" \
  "https://api.crawlora.net/api/v1/bing/search?q=coffee&count=10"
```

## Current Release Snapshot

| Surface | Current release | Coverage |
| --- | --- | --- |
| Public SDK contract | `v1.46.0-sdk.1` | 3539 generated operations across Go, TypeScript/JavaScript, Python, Ruby, Java, and PHP |
| Hosted MCP | [`crawlora-mcp@1.17.9`](https://www.npmjs.com/package/crawlora-mcp) | 3475 tools across 468 platform groups |
| Agent Skills | [`crawlora-skills@1.24.15`](https://github.com/Crawlora-org/crawlora-skills) | 165 installable skills, including 127 bundled skills and focused workflows for creator/sports, business identity, job comparisons, pet care, supply chains, product histories, football, and Reddit sentiment |
| OpenClaw | [`crawlora-openclaw-skill@1.3.1`](https://github.com/Crawlora-org/crawlora-openclaw-skill) | Hosted-MCP skill plus native tool plugin |
| n8n | [`n8n-nodes-crawlora@0.9.0`](https://www.npmjs.com/package/n8n-nodes-crawlora) | 253 curated operations across 26 resources |

The generated SDKs and MCP catalog track the same public API contract. The n8n,
Zapier, and Make integrations intentionally expose smaller, workflow-oriented
surfaces.

## Focused Platform Clients

Choose a focused package when you want just one platform's endpoints. Each
client calls Crawlora's hosted API and needs `CRAWLORA_API_KEY`; create an
account at [crawlora.net](https://crawlora.net/signup?utm_source=github&utm_medium=referral&utm_campaign=platform-clients&utm_content=client-packages-signup) and get a key in the
[console](https://crawlora.net/app?utm_source=github&utm_medium=referral&utm_campaign=platform-clients&utm_content=client-packages-console). Service usage follows your Crawlora
account plan; each package README includes runnable examples and API reference links.

| Platform | Operations | Release | Repository | Language registries |
| --- | ---: | --- | --- | --- |
| SofaScore | 43 | `0.2.0` | [`crawlora-sofascore`](https://github.com/Crawlora-org/crawlora-sofascore) | [npm](https://www.npmjs.com/package/@crawlora-org/sofascore) · [PyPI](https://pypi.org/project/crawlora-sofascore/) · [Go module](https://github.com/Crawlora-org/crawlora-sofascore) · [RubyGems](https://rubygems.org/gems/crawlora-sofascore) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-sofascore) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-sofascore/packages) · [Packagist](https://packagist.org/packages/crawlora/sofascore) |
| Flashscore | 38 | `0.2.0` | [`crawlora-flashscore`](https://github.com/Crawlora-org/crawlora-flashscore) | [npm](https://www.npmjs.com/package/@crawlora-org/flashscore) · [PyPI](https://pypi.org/project/crawlora-flashscore/) · [Go module](https://github.com/Crawlora-org/crawlora-flashscore) · [RubyGems](https://rubygems.org/gems/crawlora-flashscore) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-flashscore) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-flashscore/packages) · [Packagist](https://packagist.org/packages/crawlora/flashscore) |
| FotMob | 31 | `0.1.4` | [`crawlora-fotmob`](https://github.com/Crawlora-org/crawlora-fotmob) | [npm](https://www.npmjs.com/package/@crawlora-org/fotmob) · [PyPI](https://pypi.org/project/crawlora-fotmob/) · [Go module](https://github.com/Crawlora-org/crawlora-fotmob) · [RubyGems](https://rubygems.org/gems/crawlora-fotmob) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-fotmob) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-fotmob/packages) · [Packagist](https://packagist.org/packages/crawlora/fotmob) |
| YouTube | 14 | `0.1.4` | [`crawlora-youtube`](https://github.com/Crawlora-org/crawlora-youtube) | [npm](https://www.npmjs.com/package/@crawlora-org/youtube) · [PyPI](https://pypi.org/project/crawlora-youtube/) · [Go module](https://github.com/Crawlora-org/crawlora-youtube) · [RubyGems](https://rubygems.org/gems/crawlora-youtube) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-youtube) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-youtube/packages) · [Packagist](https://packagist.org/packages/crawlora/youtube) |
| Better Business Bureau | 9 | `0.1.0` | [`crawlora-bbb`](https://github.com/Crawlora-org/crawlora-bbb) | [npm](https://www.npmjs.com/package/@crawlora-org/bbb) · [PyPI](https://pypi.org/project/crawlora-bbb/) · [Go module](https://github.com/Crawlora-org/crawlora-bbb) · [RubyGems](https://rubygems.org/gems/crawlora-bbb) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-bbb) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-bbb/packages) · [Packagist](https://packagist.org/packages/crawlora/bbb) |

Install the focused clients for a platform such as SofaScore:

```sh
npm install @crawlora-org/sofascore
python -m pip install crawlora-sofascore
go get github.com/Crawlora-org/crawlora-sofascore@latest
gem install crawlora-sofascore
composer require crawlora/sofascore
```

For Java, add `net.crawlora:crawlora-sofascore` to your Maven dependencies. The
Java packages are also mirrored to GitHub Packages. See each repository README
for runnable calls and response formats.

## General SDKs

Beta SDKs are available for the current public API contract in six languages —
Go, TypeScript/JavaScript, Python, Ruby, Java, and PHP. They include API-key
auth, base URL overrides, retries, per-request options, grouped endpoint access,
generated typed endpoint helpers, typed dynamic operation calls, pagination,
middleware hooks, operation reference docs, usage recipes, and CI-backed release
checks. See each repository README for language-specific details.

| Language | Repository | Current release |
| --- | --- | --- |
| Go | [`crawlora-go-sdk`](https://github.com/Crawlora-org/crawlora-go-sdk) | `latest` for current SDK version `v1.46.0-sdk.1` |
| TypeScript / JavaScript | [`crawlora-typescript-sdk`](https://github.com/Crawlora-org/crawlora-typescript-sdk) | `latest` for current SDK version `v1.46.0-sdk.1` / `@crawlora-org/sdk@1.46.0-sdk.1` on npm |
| Python | [`crawlora-python-sdk`](https://github.com/Crawlora-org/crawlora-python-sdk) | [`crawlora`](https://pypi.org/project/crawlora/) on PyPI (`pip install --pre crawlora`) |
| Ruby | [`crawlora-ruby-sdk`](https://github.com/Crawlora-org/crawlora-ruby-sdk) | `v1.46.0-sdk.1` / `latest` — gem [`crawlora`](https://rubygems.org/gems/crawlora) on RubyGems (and GitHub Packages) |
| Java / JVM | [`crawlora-java-sdk`](https://github.com/Crawlora-org/crawlora-java-sdk) | `v1.46.0-sdk.1` / `latest` — [`net.crawlora:crawlora-sdk`](https://central.sonatype.com/artifact/net.crawlora/crawlora-sdk) on Maven Central (and GitHub Packages) |
| PHP | [`crawlora-php-sdk`](https://github.com/Crawlora-org/crawlora-php-sdk) | `v1.46.0-beta.1` — [`crawlora/sdk`](https://packagist.org/packages/crawlora/sdk) on Packagist (`^1.46@beta`) |

Install:

```sh
go get github.com/Crawlora-org/crawlora-go-sdk@latest
npm install @crawlora-org/sdk@latest
pip install --pre crawlora
```

For reproducible installs, pin `v1.46.0-sdk.1` for Git-based SDKs and
`@crawlora-org/sdk@1.46.0-sdk.1` for TypeScript.

The Ruby, Java, and PHP SDKs carry the same generated contract and client
features and are all published to their language registries: Ruby (`crawlora`)
on RubyGems, Java (`net.crawlora:crawlora-sdk`) on Maven Central, and PHP
(`crawlora/sdk`) on Packagist (Ruby + Java are also mirrored to GitHub Packages).

```sh
# Ruby — from RubyGems (a prerelease, so pass --pre):
gem install crawlora --pre

# PHP — Composer-valid tagged beta from Packagist:
composer require crawlora/sdk:^1.46@beta
```

Java — from Maven Central (no extra repository needed):

```xml
<dependency>
  <groupId>net.crawlora</groupId>
  <artifactId>crawlora-sdk</artifactId>
  <version>1.46.0-sdk.1</version>
</dependency>
```

Python example:

```python
from crawlora import CrawloraClient

crawlora = CrawloraClient(api_key="...")
result = crawlora.bing.search(q="coffee shops", count=10)
```

Go and TypeScript also expose generated typed endpoint parameters. Python ships
type stubs for endpoint groups, keyword parameters, and typed dynamic operation
calls.

TypeScript is published to npmjs and mirrored to GitHub Packages as
`@crawlora-org/sdk`. Python is published to PyPI as `crawlora` (a `1.46.0.dev1`
prerelease — install with `pip install --pre crawlora`).

## Integrations

Crawlora also ships ready-made integrations for AI agents, the Model Context
Protocol (MCP), and no-code automation platforms. The hosted MCP server at
`https://mcp.crawlora.net/mcp` exposes the public API as 3475 MCP tools using
stable `family.action` names.

| Integration | Repository | What it is |
| --- | --- | --- |
| MCP server | [`crawlora-mcp`](https://github.com/Crawlora-org/crawlora-mcp) | Version `1.17.9`. Hosted (and local stdio) Model Context Protocol server exposing the public API as 3475 MCP tools. Connect any MCP client to `https://mcp.crawlora.net/mcp`. |
| Agent Skills | [`crawlora-skills`](https://github.com/Crawlora-org/crawlora-skills) | Version `1.24.15`. 165 installable skills, including 127 bundled installable [Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) (`SKILL.md` packages) plus per-platform skills that teach any coding agent — Claude Code, Codex, Cursor, Copilot — how to fetch structured web data over the REST API. Recent additions include creator/sports research, app releases, job comparisons, company identity, pet-provider shortlists, supply-chain concentration, podcasts, patents, SEC evidence, football, and Reddit sentiment. No MCP setup required. Also a Claude Code plugin marketplace. |
| OpenClaw | [`crawlora-openclaw-skill`](https://github.com/Crawlora-org/crawlora-openclaw-skill) | Version `1.3.1`. ClawHub MCP skill plus a native tool plugin for the [OpenClaw](https://github.com/openclaw/openclaw) personal AI agent. |
| Zapier | [`zapier-crawlora`](https://github.com/Crawlora-org/zapier-crawlora) | Zapier integration with Get Page Content, Web Search, and Find Website Contacts actions for no-code Zaps. |
| n8n | [`n8n-nodes-crawlora`](https://github.com/Crawlora-org/n8n-nodes-crawlora) | Version `0.9.0`. n8n community node exposing 253 curated operations across 26 resources, generated from the OpenAPI spec and usable as a tool in the n8n AI Agent. |
| Make | [`make-app-crawlora`](https://github.com/Crawlora-org/make-app-crawlora) | Custom app definition for Make — Get Page Content, Web Search, and Find Website Contacts modules plus a universal "Make an API Call" module. |

The **Agent Skills** are standalone-REST recipes — an umbrella `crawlora` catalog
skill plus 161 focused skills, including `local-competitive-landscape`, `earnings-event-research`, `used-car-market-comparison`,
`software-vendor-shortlisting`, `restaurant-menu-benchmarking`,
`retail-assortment-gap-analysis`, `short-term-rental-market-research`, `google-maps-research`,
`local-business-prospecting`, `influencer-discovery`,
`journalist-media-research`, `tiktok-ad-research`, `competitor-intelligence`,
`techstack-prospecting`, `customer-feedback-analysis`, `google-trends-research`,
`sec-filings-research`, `supplier-sourcing-research`, `podcast-guest-research`,
`startup-acquisition-research`, `housing-market-research`,
`app-market-opportunity-research`, `chrome-extension-research`,
`steam-market-opportunity-research`, `crowdfunding-campaign-research`,
`event-venue-research`, and `hiring-demand-analysis`. Install one (or all) into
any agent with the `skills` CLI, then set your API key:

```sh
npx skills add github.com/Crawlora-org/crawlora-skills --skill youtube-research
export CRAWLORA_API_KEY=...
```

Or add the repo as a Claude Code plugin marketplace:
`/plugin marketplace add Crawlora-org/crawlora-skills`.

The separate **OpenClaw integration** offers a hosted MCP connection and a native
tool plugin. The Agent Skills above are standalone REST packages and are also
distributed through ClawHub. See each repository README for setup.

The **Zapier**, **n8n**, and **Make** integrations wrap the same public API as
no-code actions — get page content, web search, and find website contacts — using
`x-api-key` authentication. The n8n node also exposes a curated endpoint set as
resources and operations and is usable as a tool in the n8n AI Agent. See each
repository for the integration definition and setup.

## API Coverage

Crawlora focuses on public, credential-free data sources and stable normalized
responses. Current endpoint families include:

- Search and SERP data from Google, Bing, Brave, Google Trends, Google Finance,
  Yahoo Finance, and CoinGecko
- Prediction-market data from Polymarket, Kalshi, and Metaculus
- Marketplace and product data from Amazon, eBay, Walmart, App Store, Google
  Play, Chrome Web Store, Product Hunt, Capterra, Etsy, Airbnb, Zillow, and TripAdvisor
- Social, media, and entertainment data from YouTube, TikTok, Instagram, Threads, Reddit,
  Spotify, Apple Podcasts, JustWatch, LinkedIn, IMDb, Rotten Tomatoes,
  Metacritic, AniList, Discogs, Letterboxd, TMDB, Goodreads, and Box Office Mojo
- Reviews, business, datasets, and geodata from Trustpilot, Yelp, SimilarWeb,
  Numbeo, Crunchbase, Geocoding, Google Maps, Chrome extension intelligence,
  journalist discovery, Box Office Mojo theatrical records, and startup revenue history

## Maintenance Model

The SDKs are generated from Crawlora's public API contract and include small
hand-written wrappers for authentication, base URL override, request execution,
and grouped endpoint access. Public endpoint changes are reflected in the API
docs and regenerated SDK contracts. SDK releases use explicit beta tags plus a
moving `latest` tag; the TypeScript SDK is also published to GitHub Packages.
