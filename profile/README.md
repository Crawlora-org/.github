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

Git-only beta SDKs are available for the current public API contract. See each
repository README for language-specific installation notes.

| Language | Repository | Current tag |
| --- | --- | --- |
| Go | [`crawlora-go-sdk`](https://github.com/Crawlora-org/crawlora-go-sdk) | `v1.2.0-sdk.1` |
| TypeScript / JavaScript | [`crawlora-typescript-sdk`](https://github.com/Crawlora-org/crawlora-typescript-sdk) | `v1.2.0-sdk.1` |
| Python | [`crawlora-python-sdk`](https://github.com/Crawlora-org/crawlora-python-sdk) | `v1.2.0-sdk.1` |

Example:

```python
from crawlora import CrawloraClient

crawlora = CrawloraClient(api_key="...")
result = crawlora.bing.search(q="coffee shops", count=10)
```

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
docs and regenerated SDK contracts.
