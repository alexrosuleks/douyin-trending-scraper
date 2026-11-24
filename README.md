# Douyin Trending Scraper: Douyin Scraper API for Python & Node.js (2026)

Scrape Douyin (抖音) trending topics from all 5 hot-search boards: rank, topic, hot value, views, video count, cover and link. No login needed. JSON, CSV, Excel.

**[▶ Try the Douyin Trending Scraper free on Scrapely](https://scrape.ly/store/echofield/douyin-trending-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Douyin data with the [Douyin Trending Scraper](https://scrape.ly/store/echofield/douyin-trending-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the douyin scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Douyin scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/douyin-trending-scraper) or from your code with the SDK.
- **Structured douyin data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $6.80 per 1,000 trending topic results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Douyin changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Douyin data can you extract?

Scrape Douyin (抖音) trending topics from all 5 hot-search boards: rank, topic, hot value, views, video count, cover and link. No login needed. JSON, CSV, Excel.

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/douyin-trending-scraper').call({"boards": ["hotspot"], "maxResultsPerBoard": 50, "minHotValue": 0, "dedupeAcrossBoards": true, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/douyin-trending-scraper').call(run_input={ "boards": [ "hotspot" ], "maxResultsPerBoard": 50, "minHotValue": 0, "dedupeAcrossBoards": True, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~douyin-trending-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "boards": [
    "hotspot"
  ],
  "maxResultsPerBoard": 50,
  "minHotValue": 0,
  "dedupeAcrossBoards": true,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Douyin Trending Scraper page](https://scrape.ly/store/echofield/douyin-trending-scraper).

## Pricing

**$6.80 per 1,000 trending topic results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/douyin-trending-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Douyin with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Douyin with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a douyin scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~douyin-trending-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Douyin legal?** This scraper collects publicly available data. Check Douyin's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related Douyin scrapers

- [Douyin Scraper](https://github.com/alexrosuleks/douyin-scraper): Scrape public Douyin (抖音) profiles and videos: caption, likes, comments, shares, plays, music and video URL. No login…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** douyin trending scraper, douyin scraper, douyin scraper api, douyin scraper python, douyin scraper node.js,
scrape douyin, douyin data extraction, douyin crawler, douyin api, export douyin data to csv, douyin-trending-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/douyin-trending-scraper).
