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
| Go | [`crawlora-go-sdk`](https://github.com/Crawlora-org/crawlora-go-sdk) | `latest` for current SDK version `v1.4.0-sdk.1` |
| TypeScript / JavaScript | [`crawlora-typescript-sdk`](https://github.com/Crawlora-org/crawlora-typescript-sdk) | `latest` for current SDK version `v1.4.0-sdk.1` / `@crawlora-org/sdk@1.4.0-sdk.1` |
| Python | [`crawlora-python-sdk`](https://github.com/Crawlora-org/crawlora-python-sdk) | `latest` for current SDK version `v1.4.0-sdk.1` |
| Ruby | [`crawlora-ruby-sdk`](https://github.com/Crawlora-org/crawlora-ruby-sdk) | `v1.5.0-sdk.2` / `latest` — gem [`crawlora`](https://rubygems.org/gems/crawlora) on RubyGems (and GitHub Packages) |
| Java / JVM | [`crawlora-java-sdk`](https://github.com/Crawlora-org/crawlora-java-sdk) | `v1.5.0-sdk.2` / `latest` — `net.crawlora:crawlora-sdk` on GitHub Packages; Maven Central publication pending |
| PHP | [`crawlora-php-sdk`](https://github.com/Crawlora-org/crawlora-php-sdk) | `latest` (dev) — [`crawlora/sdk`](https://packagist.org/packages/crawlora/sdk) on Packagist (`^1.5@dev`) |

Install:

```sh
go get github.com/Crawlora-org/crawlora-go-sdk@latest
npm install @crawlora-org/sdk@latest
pip install "git+https://github.com/Crawlora-org/crawlora-python-sdk.git@latest"
```

For reproducible installs, pin `v1.4.0-sdk.1` for Git-based SDKs and
`@crawlora-org/sdk@1.4.0-sdk.1` for TypeScript.

The Ruby, Java, and PHP SDKs carry the same generated contract and client
features. Ruby (`crawlora`) is on RubyGems, PHP (`crawlora/sdk`) is on Packagist,
and Ruby + Java are on GitHub Packages. The one remaining public-registry
publication — `net.crawlora:crawlora-sdk` on Maven Central — is in progress.

```sh
# Ruby — from RubyGems (a prerelease, so pass --pre):
gem install crawlora --pre

# PHP — from Packagist (dev release; the -sdk.N tags aren't valid Composer versions):
composer require crawlora/sdk:^1.5@dev
```

Java — from GitHub Packages, add the repository and dependency to your
`pom.xml` (GitHub Packages requires a token in `~/.m2/settings.xml`):

```xml
<repositories>
  <repository>
    <id>github</id>
    <url>https://maven.pkg.github.com/Crawlora-org/crawlora-java-sdk</url>
  </repository>
</repositories>
<dependency>
  <groupId>net.crawlora</groupId>
  <artifactId>crawlora-sdk</artifactId>
  <version>1.5.0-sdk.1</version>
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
`@crawlora-org/sdk`. The future PyPI package target is `crawlora`; until PyPI
publication is enabled, install the Python SDK from Git tags.

## Integrations

Crawlora also ships ready-made integrations for AI agents and the Model Context
Protocol (MCP). The hosted MCP server at `https://mcp.crawlora.net/mcp` exposes
the public API as ~150 MCP tools using stable `family.action` names.

| Integration | Repository | What it is |
| --- | --- | --- |
| OpenClaw | [`crawlora-openclaw-skill`](https://github.com/Crawlora-org/crawlora-openclaw-skill) | ClawHub MCP skill plus a native tool plugin for the [OpenClaw](https://github.com/openclaw/openclaw) personal AI agent. |

OpenClaw skills are MCP servers, so the skill connects OpenClaw straight to the
hosted Crawlora MCP server — add it to `~/.openclaw/openclaw.json` (or run
`openclaw mcp add`) and authenticate with your Crawlora API key. See the
repository README for setup.

## API Coverage

Crawlora focuses on public, credential-free data sources and stable normalized
responses. Current endpoint families include:

- Search and SERP data from Google, Bing, Brave, Google Trends, Google Finance,
  Yahoo Finance, and CoinGecko
- Marketplace and product data from Amazon, eBay, App Store, Google Play,
  Product Hunt, Etsy, Airbnb, Zillow, and TripAdvisor
- Social and media data from YouTube, TikTok, Instagram, Spotify, Apple
  Podcasts, JustWatch, and LinkedIn
- Reviews, business, and geodata from Trustpilot, Yelp, SimilarWeb,
  Crunchbase, Geocoding, and Google Maps datasets

## Maintenance Model

The SDKs are generated from Crawlora's public API contract and include small
hand-written wrappers for authentication, base URL override, request execution,
and grouped endpoint access. Public endpoint changes are reflected in the API
docs and regenerated SDK contracts. SDK releases use explicit beta tags plus a
moving `latest` tag; the TypeScript SDK is also published to GitHub Packages.
