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
| Public SDK releases | `v1.48.0-sdk.1` (Go, TypeScript, Python, Ruby, Java, PHP); `v1.49.0-sdk.3` (Rust) | 3,737 generated operations in the six established SDKs; 3,767 in Rust |
| Hosted MCP | [`crawlora-mcp@1.17.13`](https://www.npmjs.com/package/crawlora-mcp) | 3665 tools across 472 platform groups |
| Agent Skills | [`crawlora-skills@1.24.22`](https://github.com/Crawlora-org/crawlora-skills) | 169 installable skills, including 131 bundled skills and focused workflows for creator/sports, business identity, job comparisons, pet care, supply chains, product histories, football, Reddit sentiment, Reverb used-gear price history, and BBB Scam Tracker patterns |
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
Platform clients are versioned and released independently; each package's registry
page shows its current version.

| Platform | Operations | Release | Repository | Language registries |
| --- | ---: | --- | --- | --- |
| Reddit | 12 | `0.1.2` | [`crawlora-reddit`](https://github.com/Crawlora-org/crawlora-reddit) | [npm](https://www.npmjs.com/package/@crawlora-org/reddit) · [PyPI](https://pypi.org/project/crawlora-reddit/) · [Go module](https://github.com/Crawlora-org/crawlora-reddit) · [RubyGems](https://rubygems.org/gems/crawlora-reddit) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-reddit) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-reddit/packages) · [Packagist](https://packagist.org/packages/crawlora/reddit) |
| TikTok | 25 | `0.1.3` | [`crawlora-tiktok`](https://github.com/Crawlora-org/crawlora-tiktok) | [npm](https://www.npmjs.com/package/@crawlora-org/tiktok) · [PyPI](https://pypi.org/project/crawlora-tiktok/) · [Go module](https://github.com/Crawlora-org/crawlora-tiktok) · [RubyGems](https://rubygems.org/gems/crawlora-tiktok) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-tiktok) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-tiktok/packages) · [Packagist](https://packagist.org/packages/crawlora/tiktok) |
| Amazon | 5 | `0.1.2` | [`crawlora-amazon`](https://github.com/Crawlora-org/crawlora-amazon) | [npm](https://www.npmjs.com/package/@crawlora-org/amazon) · [PyPI](https://pypi.org/project/crawlora-amazon/) · [Go module](https://github.com/Crawlora-org/crawlora-amazon) · [RubyGems](https://rubygems.org/gems/crawlora-amazon) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-amazon) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-amazon/packages) · [Packagist](https://packagist.org/packages/crawlora/amazon) |
| IMDb | 30 | `0.1.2` | [`crawlora-imdb`](https://github.com/Crawlora-org/crawlora-imdb) | [npm](https://www.npmjs.com/package/@crawlora-org/imdb) · [PyPI](https://pypi.org/project/crawlora-imdb/) · [Go module](https://github.com/Crawlora-org/crawlora-imdb) · [RubyGems](https://rubygems.org/gems/crawlora-imdb) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-imdb) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-imdb/packages) · [Packagist](https://packagist.org/packages/crawlora/imdb) |
| SofaScore | 109 | `0.3.5` | [`crawlora-sofascore`](https://github.com/Crawlora-org/crawlora-sofascore) | [npm](https://www.npmjs.com/package/@crawlora-org/sofascore) · [PyPI](https://pypi.org/project/crawlora-sofascore/) · [Go module](https://github.com/Crawlora-org/crawlora-sofascore) · [RubyGems](https://rubygems.org/gems/crawlora-sofascore) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-sofascore) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-sofascore/packages) · [Packagist](https://packagist.org/packages/crawlora/sofascore) |
| Flashscore | 54 | `0.3.5` | [`crawlora-flashscore`](https://github.com/Crawlora-org/crawlora-flashscore) | [npm](https://www.npmjs.com/package/@crawlora-org/flashscore) · [PyPI](https://pypi.org/project/crawlora-flashscore/) · [Go module](https://github.com/Crawlora-org/crawlora-flashscore) · [RubyGems](https://rubygems.org/gems/crawlora-flashscore) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-flashscore) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-flashscore/packages) · [Packagist](https://packagist.org/packages/crawlora/flashscore) |
| FotMob | 31 | `0.1.9` | [`crawlora-fotmob`](https://github.com/Crawlora-org/crawlora-fotmob) | [npm](https://www.npmjs.com/package/@crawlora-org/fotmob) · [PyPI](https://pypi.org/project/crawlora-fotmob/) · [Go module](https://github.com/Crawlora-org/crawlora-fotmob) · [RubyGems](https://rubygems.org/gems/crawlora-fotmob) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-fotmob) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-fotmob/packages) · [Packagist](https://packagist.org/packages/crawlora/fotmob) |
| YouTube | 14 | `0.1.9` | [`crawlora-youtube`](https://github.com/Crawlora-org/crawlora-youtube) | [npm](https://www.npmjs.com/package/@crawlora-org/youtube) · [PyPI](https://pypi.org/project/crawlora-youtube/) · [Go module](https://github.com/Crawlora-org/crawlora-youtube) · [RubyGems](https://rubygems.org/gems/crawlora-youtube) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-youtube) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-youtube/packages) · [Packagist](https://packagist.org/packages/crawlora/youtube) |
| Better Business Bureau | 16 | `0.3.1` | [`crawlora-bbb`](https://github.com/Crawlora-org/crawlora-bbb) | [npm](https://www.npmjs.com/package/@crawlora-org/bbb) · [PyPI](https://pypi.org/project/crawlora-bbb/) · [Go module](https://github.com/Crawlora-org/crawlora-bbb) · [RubyGems](https://rubygems.org/gems/crawlora-bbb) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-bbb) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-bbb/packages) · [Packagist](https://packagist.org/packages/crawlora/bbb) |
| Google | 40 | `0.1.1` | [`crawlora-google`](https://github.com/Crawlora-org/crawlora-google) | [npm](https://www.npmjs.com/package/@crawlora-org/google) · [PyPI](https://pypi.org/project/crawlora-google/) · [Go module](https://github.com/Crawlora-org/crawlora-google) · [RubyGems](https://rubygems.org/gems/crawlora-google) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-google) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-google/packages) · [Packagist](https://packagist.org/packages/crawlora/google) |
| Bing | 5 | `0.1.1` | [`crawlora-bing`](https://github.com/Crawlora-org/crawlora-bing) | [npm](https://www.npmjs.com/package/@crawlora-org/bing) · [PyPI](https://pypi.org/project/crawlora-bing/) · [Go module](https://github.com/Crawlora-org/crawlora-bing) · [RubyGems](https://rubygems.org/gems/crawlora-bing) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-bing) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-bing/packages) · [Packagist](https://packagist.org/packages/crawlora/bing) |
| Brave Search | 5 | `0.1.1` | [`crawlora-brave`](https://github.com/Crawlora-org/crawlora-brave) | [npm](https://www.npmjs.com/package/@crawlora-org/brave) · [PyPI](https://pypi.org/project/crawlora-brave/) · [Go module](https://github.com/Crawlora-org/crawlora-brave) · [RubyGems](https://rubygems.org/gems/crawlora-brave) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-brave) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-brave/packages) · [Packagist](https://packagist.org/packages/crawlora/brave) |
| DuckDuckGo | 6 | `0.1.1` | [`crawlora-duckduckgo`](https://github.com/Crawlora-org/crawlora-duckduckgo) | [npm](https://www.npmjs.com/package/@crawlora-org/duckduckgo) · [PyPI](https://pypi.org/project/crawlora-duckduckgo/) · [Go module](https://github.com/Crawlora-org/crawlora-duckduckgo) · [RubyGems](https://rubygems.org/gems/crawlora-duckduckgo) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-duckduckgo) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-duckduckgo/packages) · [Packagist](https://packagist.org/packages/crawlora/duckduckgo) |
| eBay | 10 | `0.1.1` | [`crawlora-ebay`](https://github.com/Crawlora-org/crawlora-ebay) | [npm](https://www.npmjs.com/package/@crawlora-org/ebay) · [PyPI](https://pypi.org/project/crawlora-ebay/) · [Go module](https://github.com/Crawlora-org/crawlora-ebay) · [RubyGems](https://rubygems.org/gems/crawlora-ebay) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-ebay) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-ebay/packages) · [Packagist](https://packagist.org/packages/crawlora/ebay) |
| Google Play | 11 | `0.1.1` | [`crawlora-googleplay`](https://github.com/Crawlora-org/crawlora-googleplay) | [npm](https://www.npmjs.com/package/@crawlora-org/googleplay) · [PyPI](https://pypi.org/project/crawlora-googleplay/) · [Go module](https://github.com/Crawlora-org/crawlora-googleplay) · [RubyGems](https://rubygems.org/gems/crawlora-googleplay) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-googleplay) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-googleplay/packages) · [Packagist](https://packagist.org/packages/crawlora/googleplay) |
| App Store | 15 | `0.1.1` | [`crawlora-appstore`](https://github.com/Crawlora-org/crawlora-appstore) | [npm](https://www.npmjs.com/package/@crawlora-org/appstore) · [PyPI](https://pypi.org/project/crawlora-appstore/) · [Go module](https://github.com/Crawlora-org/crawlora-appstore) · [RubyGems](https://rubygems.org/gems/crawlora-appstore) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-appstore) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-appstore/packages) · [Packagist](https://packagist.org/packages/crawlora/appstore) |
| Airbnb | 7 | `0.1.1` | [`crawlora-airbnb`](https://github.com/Crawlora-org/crawlora-airbnb) | [npm](https://www.npmjs.com/package/@crawlora-org/airbnb) · [PyPI](https://pypi.org/project/crawlora-airbnb/) · [Go module](https://github.com/Crawlora-org/crawlora-airbnb) · [RubyGems](https://rubygems.org/gems/crawlora-airbnb) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-airbnb) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-airbnb/packages) · [Packagist](https://packagist.org/packages/crawlora/airbnb) |
| Spotify | 38 | `0.1.1` | [`crawlora-spotify`](https://github.com/Crawlora-org/crawlora-spotify) | [npm](https://www.npmjs.com/package/@crawlora-org/spotify) · [PyPI](https://pypi.org/project/crawlora-spotify/) · [Go module](https://github.com/Crawlora-org/crawlora-spotify) · [RubyGems](https://rubygems.org/gems/crawlora-spotify) · [Maven Central](https://central.sonatype.com/artifact/net.crawlora/crawlora-spotify) / [GitHub Packages](https://github.com/Crawlora-org/crawlora-spotify/packages) · [Packagist](https://packagist.org/packages/crawlora/spotify) |

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

Beta SDKs are available in seven languages — Go, TypeScript/JavaScript, Python,
Ruby, Java, PHP, and Rust. The Rust release covers 3,767 generated operations;
the six established SDKs remain on their 3,737-operation `v1.48.0-sdk.1` release
until the next coordinated regeneration. SDKs include API-key authentication,
base URL overrides, retries, per-request options, grouped endpoint access,
generated typed endpoint helpers, typed dynamic operation calls, pagination,
operation reference docs, usage recipes, and CI-backed release checks. See each
repository README for language-specific details.

| Language | Repository | Current release |
| --- | --- | --- |
| Go | [`crawlora-go-sdk`](https://github.com/Crawlora-org/crawlora-go-sdk) | `latest` for current SDK version `v1.48.0-sdk.1` |
| TypeScript / JavaScript | [`crawlora-typescript-sdk`](https://github.com/Crawlora-org/crawlora-typescript-sdk) | `latest` for current SDK version `v1.48.0-sdk.1` / `@crawlora-org/sdk@1.48.0-sdk.1` on npm |
| Python | [`crawlora-python-sdk`](https://github.com/Crawlora-org/crawlora-python-sdk) | [`crawlora`](https://pypi.org/project/crawlora/) on PyPI (`pip install --pre crawlora`) |
| Ruby | [`crawlora-ruby-sdk`](https://github.com/Crawlora-org/crawlora-ruby-sdk) | `v1.48.0-sdk.1` / `latest` — gem [`crawlora`](https://rubygems.org/gems/crawlora) on RubyGems (and GitHub Packages) |
| Java / JVM | [`crawlora-java-sdk`](https://github.com/Crawlora-org/crawlora-java-sdk) | `v1.48.0-sdk.1` / `latest` — [`net.crawlora:crawlora-sdk`](https://central.sonatype.com/artifact/net.crawlora/crawlora-sdk) on Maven Central (and GitHub Packages) |
| PHP | [`crawlora-php-sdk`](https://github.com/Crawlora-org/crawlora-php-sdk) | `v1.48.0-beta.1` — [`crawlora/sdk`](https://packagist.org/packages/crawlora/sdk) on Packagist (`^1.48@beta`) |
| Rust | [`crawlora-rust-sdk`](https://github.com/Crawlora-org/crawlora-rust-sdk) | `v1.49.0-sdk.3` — [`crawlora`](https://crates.io/crates/crawlora) on crates.io |

Install:

```sh
go get github.com/Crawlora-org/crawlora-go-sdk@latest
npm install @crawlora-org/sdk@latest
pip install --pre crawlora
cargo add crawlora@1.49.0-sdk.3
```

For reproducible installs, pin `v1.48.0-sdk.1` for Git-based SDKs and
`@crawlora-org/sdk@1.48.0-sdk.1` for TypeScript; Rust users can pin
`crawlora = "1.49.0-sdk.3"` in `Cargo.toml`.

The Ruby, Java, and PHP SDKs carry the same generated contract and client
features and are all published to their language registries: Ruby (`crawlora`)
on RubyGems, Java (`net.crawlora:crawlora-sdk`) on Maven Central, and PHP
(`crawlora/sdk`) on Packagist (Ruby + Java are also mirrored to GitHub Packages).

```sh
# Ruby — from RubyGems (a prerelease, so pass --pre):
gem install crawlora --pre

# PHP — Composer-valid tagged beta from Packagist:
composer require crawlora/sdk:^1.48@beta
```

Java — from Maven Central (no extra repository needed):

```xml
<dependency>
  <groupId>net.crawlora</groupId>
  <artifactId>crawlora-sdk</artifactId>
  <version>1.48.0-sdk.1</version>
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
`@crawlora-org/sdk`. Python is published to PyPI as `crawlora` (a `1.48.0.dev1`
prerelease — install with `pip install --pre crawlora`).

## Integrations

Crawlora also ships ready-made integrations for AI agents, the Model Context
Protocol (MCP), and no-code automation platforms. The hosted MCP server at
`https://mcp.crawlora.net/mcp` exposes the public API as 3665 MCP tools using
stable `family.action` names.

| Integration | Repository | What it is |
| --- | --- | --- |
| MCP server | [`crawlora-mcp`](https://github.com/Crawlora-org/crawlora-mcp) | Version `1.17.13`. Hosted (and local stdio) Model Context Protocol server exposing the public API as 3665 MCP tools. Connect any MCP client to `https://mcp.crawlora.net/mcp`. |
| Agent Skills | [`crawlora-skills`](https://github.com/Crawlora-org/crawlora-skills) | Version `1.24.22`. 169 installable skills, including 131 bundled installable [Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) (`SKILL.md` packages) plus per-platform skills that teach any coding agent — Claude Code, Codex, Cursor, Copilot — how to fetch structured web data over the REST API. Recent additions include creator/sports research, app releases, job comparisons, company identity, pet-provider shortlists, supply-chain concentration, podcasts, patents, SEC evidence, football, Reddit sentiment, Reverb used-gear price history, and BBB Scam Tracker patterns. No MCP setup required. Also ships Claude Code, Codex, and Cursor plugin packages. |
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
