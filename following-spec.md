# `following.json` Specification

## Location

Published at the root of your static site: `https://yoursite.com/following.json`

## Format

```json
{
  "version": "1.0",
  "following": [
    {
      "url": "https://example.com",
      "added": "2025-02-07T00:00:00Z",
      "tags": ["tech", "security"]
    },
    {
      "url": "https://another-site.dev",
      "added": "2025-01-15T00:00:00Z"
    }
  ]
}
```

## Fields

### `version` (required)
Spec version. Currently `"1.0"`.

### `following` (required)
Array of sites you follow.

Each entry:
- `url` (required): Full URL to the site
- `added` (optional): ISO 8601 timestamp when you started following
- `tags` (optional): Array of tags for categorizing this follow

## Minimal Example

```json
{
  "version": "1.0",
  "following": [
    {"url": "https://example.com"},
    {"url": "https://another.site"}
  ]
}
```

## Agent Behavior

Agents should:
1. Check `following.json` for updates periodically
2. Crawl each URL in the `following` array
3. Look for standard feed formats (RSS, Atom, JSON Feed)
4. Parse HTML if no feed exists
5. Follow links to discover related content

## Future Extensions

Possible additions:
- `metadata` field with user description, avatar, etc.
- `blocked` array for sites to ignore
- `priority` field for crawl frequency
- `categories` for organizing follows

Keep it simple for now. Extend as needed.
