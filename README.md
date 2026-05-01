# crawler-db
Structured database of web crawler user agents for bot detection, filtering, and classification.

## crawlers.json

Array of crawler entries:

```json
[
  {
    "pattern": "Googlebot\\/",
    "url": "http://www.google.com/bot.html",
    "description": "Google's main web crawling bot for search indexing",
    "tags": ["search-engine"],
    "instances": [
      "Googlebot/2.1 (+http://www.google.com/bot.html)",
      "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
    ]
  }
]
```

| Field | Type | Description |
|-------|------|-------------|
| `pattern` | string | Regex to match against `User-Agent` |
| `url` | string | Official bot documentation page |
| `description` | string | ≤10 word summary |
| `tags` | string[] | Purpose tags (see below) |
| `instances` | string[] | Real-world `User-Agent` strings seen in the wild |

### Tags

| Tag | Purpose | Block risk |
|-----|---------|------------|
| `search-engine` | Web search indexing | Low |
| `ai-crawler` | AI/LLM training or inference | Varies |
| `social-preview` | Link previews in social/messaging apps | Low |
| `seo` | SEO tools, backlink analyzers | Medium |
| `monitoring` | Uptime checks, health probes | Low |
| `feed-reader` | RSS/Atom feed fetchers | Low |
| `archiver` | Web archiving and preservation | Low |
| `advertising` | Ad quality checks, conversion tracking | Low–Medium |
| `scanner` | Security scanners, vulnerability testers | High |
| `http-library` | Generic HTTP client libraries | Medium–High |
| `browser-automation` | Headless browsers, automation frameworks | Medium–High |
| `academic` | Research and academic crawlers | Low |

## Credits

Special thanks to [monperrus/crawler-user-agents](https://github.com/monperrus/crawler-user-agents).
