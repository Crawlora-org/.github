# Crawlora

Crawlora provides developer APIs for structured public web data. Use it to
collect normalized search, marketplace, social, finance, media, reviews, and
geodata signals without maintaining scraper infrastructure yourself.

## Start Here

- Website: https://crawlora.net
- API docs: https://crawlora.net/docs
- Playground: https://crawlora.net/playground
- Pricing: https://crawlora.net/pricing
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

## SDKs

Beta SDKs are available for the current public API contract in six languages —
Go, TypeScript/JavaScript, Python, Ruby, Java, and PHP. They include API-key
auth, base URL overrides, retries, per-request options, grouped endpoint access,
generated typed endpoint helpers, typed dynamic operation calls, pagination,
middleware hooks, operation reference docs, usage recipes, and CI-backed release
checks. See each repository README for language-specific details.

| Language | Repository | Current release |
| --- | --- | --- |
| Go | [`crawlora-go-sdk`](https://github.com/Crawlora-org/crawlora-go-sdk) | `latest` for current SDK version `v1.7.0-sdk.1` |
| TypeScript / JavaScript | [`crawlora-typescript-sdk`](https://github.com/Crawlora-org/crawlora-typescript-sdk) | `latest` for current SDK version `v1.7.0-sdk.1` / `@crawlora-org/sdk@1.7.0-sdk.1` on npm |
| Python | [`crawlora-python-sdk`](https://github.com/Crawlora-org/crawlora-python-sdk) | [`crawlora`](https://pypi.org/project/crawlora/) on PyPI (`pip install --pre crawlora`) |
| Ruby | [`crawlora-ruby-sdk`](https://github.com/Crawlora-org/crawlora-ruby-sdk) | `v1.7.0-sdk.1` / `latest` — gem [`crawlora`](https://rubygems.org/gems/crawlora) on RubyGems (and GitHub Packages) |
| Java / JVM | [`crawlora-java-sdk`](https://github.com/Crawlora-org/crawlora-java-sdk) | `v1.7.0-sdk.1` / `latest` — [`net.crawlora:crawlora-sdk`](https://central.sonatype.com/artifact/net.crawlora/crawlora-sdk) on Maven Central (and GitHub Packages) |
| PHP | [`crawlora-php-sdk`](https://github.com/Crawlora-org/crawlora-php-sdk) | `latest` (dev) — [`crawlora/sdk`](https://packagist.org/packages/crawlora/sdk) on Packagist (`^1.7@dev`) |

Install:

```sh
go get github.com/Crawlora-org/crawlora-go-sdk@latest
npm install @crawlora-org/sdk@latest
pip install --pre crawlora
```

For reproducible installs, pin `v1.7.0-sdk.1` for Git-based SDKs and
`@crawlora-org/sdk@1.7.0-sdk.1` for TypeScript.

The Ruby, Java, and PHP SDKs carry the same generated contract and client
features and are all published to their language registries: Ruby (`crawlora`)
on RubyGems, Java (`net.crawlora:crawlora-sdk`) on Maven Central, and PHP
(`crawlora/sdk`) on Packagist (Ruby + Java are also mirrored to GitHub Packages).

```sh
# Ruby — from RubyGems (a prerelease, so pass --pre):
gem install crawlora --pre

# PHP — from Packagist (dev release; the -sdk.N tags aren't valid Composer versions):
composer require crawlora/sdk:^1.7@dev
```

Java — from Maven Central (no extra repository needed):

```xml
<dependency>
  <groupId>net.crawlora</groupId>
  <artifactId>crawlora-sdk</artifactId>
  <version>1.7.0-sdk.1</version>
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
`@crawlora-org/sdk`. Python is published to PyPI as `crawlora` (a `1.7.0.dev1`
prerelease — install with `pip install --pre crawlora`).

## Integrations

Crawlora also ships ready-made integrations for AI agents and the Model Context
Protocol (MCP). The hosted MCP server at `https://mcp.crawlora.net/mcp` exposes
the public API as ~440 MCP tools using stable `family.action` names.

| Integration | Repository | What it is |
| --- | --- | --- |
| MCP server | [`crawlora-mcp`](https://github.com/Crawlora-org/crawlora-mcp) | Hosted (and local stdio) Model Context Protocol server exposing the public API as ~440 MCP tools. Connect any MCP client to `https://mcp.crawlora.net/mcp`. |
| Agent Skills | [`crawlora-skills`](https://github.com/Crawlora-org/crawlora-skills) | Installable [Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) (`SKILL.md` packages) that teach any coding agent — Claude Code, Codex, Cursor, Copilot — how to fetch structured web data over the REST API. No MCP setup required. Also a Claude Code plugin marketplace. |
| OpenClaw | [`crawlora-openclaw-skill`](https://github.com/Crawlora-org/crawlora-openclaw-skill) | ClawHub MCP skill plus a native tool plugin for the [OpenClaw](https://github.com/openclaw/openclaw) personal AI agent. |

The **Agent Skills** are standalone-REST recipes — an umbrella `crawlora` catalog
skill plus focused `product-price-research`, `youtube-research`,
`app-review-mining`, and `serp-keyword-research` skills. Install one (or all) into
any agent with the `skills` CLI, then set your API key:

```sh
npx skills add github.com/Crawlora-org/crawlora-skills --skill youtube-research
export CRAWLORA_API_KEY=...
```

Or add the repo as a Claude Code plugin marketplace:
`/plugin marketplace add Crawlora-org/crawlora-skills`.

OpenClaw skills are MCP servers, so that skill connects OpenClaw straight to the
hosted Crawlora MCP server — add it to `~/.openclaw/openclaw.json` (or run
`openclaw mcp add`) and authenticate with your Crawlora API key. See the
repository README for setup.

## API Coverage

Crawlora focuses on public, credential-free data sources and stable normalized
responses. Current endpoint families include:

- Search and SERP data from Google, Bing, Brave, Google Trends, Google Finance,
  Yahoo Finance, and CoinGecko
- Prediction-market data from Polymarket, Kalshi, and Metaculus
- Marketplace and product data from Amazon, eBay, App Store, Google Play,
  Product Hunt, Etsy, Airbnb, Zillow, and TripAdvisor
- Social, media, and entertainment data from YouTube, TikTok, Instagram, Reddit,
  Spotify, Apple Podcasts, JustWatch, LinkedIn, IMDb, Rotten Tomatoes, and
  Box Office Mojo
- Reviews, business, and geodata from Trustpilot, Yelp, SimilarWeb,
  Crunchbase, Geocoding, and Google Maps datasets

## Maintenance Model

The SDKs are generated from Crawlora's public API contract and include small
hand-written wrappers for authentication, base URL override, request execution,
and grouped endpoint access. Public endpoint changes are reflected in the API
docs and regenerated SDK contracts. SDK releases use explicit beta tags plus a
moving `latest` tag; the TypeScript SDK is also published to GitHub Packages.
