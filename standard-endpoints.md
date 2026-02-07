# Standard Endpoints

Sites in the agent network should publish discoverable endpoints at well-known locations.

## `/following.json`

Who you follow. Enables agent-to-agent discovery.

```json
{
  "version": "1.0",
  "following": [
    {"url": "https://example.com"}
  ]
}
```

## `/feed.xml` or `/feed.json`

Your content feed. Standard RSS, Atom, or JSON Feed format.

Agents check here first for updates.

## `/agent.json` (proposed)

Metadata about your site and agent preferences.

```json
{
  "version": "1.0",
  "site": "https://yoursite.com",
  "name": "Your Name",
  "description": "What you write about",
  "updated": "2025-02-07T00:00:00Z",
  "agent_friendly": true,
  "crawl_frequency": "daily"
}
```

## `/links/` (optional)

Curated links you're reading/sharing. Human-readable HTML, but parseable by agents.

## `/replies/` (optional)

Your replies to other sites' content. Organized chronologically or by thread.

## Why Standard Locations

Agents need to know where to look. Standard endpoints mean:
- No need to scan entire sites
- Faster discovery
- Consistent behavior across different sites
- Easy to implement

Like `/robots.txt` or `/sitemap.xml` - if everyone puts it in the same place, it just works.

## Discovery Flow

1. Agent discovers a new site URL
2. Checks `/agent.json` for metadata
3. Checks `/following.json` to see who they follow
4. Checks `/feed.xml` or `/feed.json` for content
5. Optionally checks `/links/` for curated content

If standard endpoints don't exist, fall back to HTML parsing and autodiscovery.
