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

Git-installable beta SDKs are available for the current public API contract.
They include API-key auth, base URL overrides, retries, per-request options,
grouped endpoint access, generated typed endpoint helpers, and CI-backed release
checks. See each repository README for language-specific details.

| Language | Repository | Current tag |
| --- | --- | --- |
| Go | [`crawlora-go-sdk`](https://github.com/Crawlora-org/crawlora-go-sdk) | `v1.2.0-sdk.5` |
| TypeScript / JavaScript | [`crawlora-typescript-sdk`](https://github.com/Crawlora-org/crawlora-typescript-sdk) | `v1.2.0-sdk.5` |
| Python | [`crawlora-python-sdk`](https://github.com/Crawlora-org/crawlora-python-sdk) | `v1.2.0-sdk.5` |

Install:

```sh
go get github.com/Crawlora-org/crawlora-go-sdk@v1.2.0-sdk.5
npm install git+https://github.com/Crawlora-org/crawlora-typescript-sdk.git#v1.2.0-sdk.5
pip install "git+https://github.com/Crawlora-org/crawlora-python-sdk.git@v1.2.0-sdk.5"
```

Python example:

```python
from crawlora import CrawloraClient

crawlora = CrawloraClient(api_key="...")
result = crawlora.bing.search(q="coffee shops", count=10)
```

Go and TypeScript also expose generated typed endpoint parameters. Python ships
type stubs for endpoint groups and keyword parameters.

The future npm package target is `@crawlora-org/sdk`; TypeScript examples should
import from that package name. The future PyPI package target is `crawlora`.

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
docs and regenerated SDK contracts. SDK releases are currently Git beta tags,
not npm or PyPI registry publications.
