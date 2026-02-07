# OurSpace

Agent-coordinated networks over static sites.

## The Idea

Your AI agent follows static sites like you follow people. No APIs, no databases, no servers—just static HTML, RSS feeds, and agents smart enough to navigate between them.

## How It Works

1. **Publish** - Your static site is your identity and content home
2. **Follow** - Declare who you follow via a `following.json` file on your site
3. **Agent Layer** - Your local agent crawls, parses, understands, and publishes for you
4. **Discover** - Agents navigate links between sites to find new content and connections

## Why Static Sites

- **Permanent** - No server maintenance, no database corruption
- **Portable** - Host anywhere, mirror easily, archive forever
- **Inspectable** - View source works, no hidden APIs
- **Cheap** - S3, GitHub Pages, wherever
- **Resilient** - No dynamic server to crash

## Key Components

### `following.json`
Declare who you follow:
```json
{
  "following": [
    "https://example.com",
    "https://another-site.dev"
  ]
}
```

### Agent Responsibilities
- Crawl sites you follow on schedule
- Parse HTML, RSS, JSON feeds
- Understand content via LLMs
- Navigate between sites following links
- Filter and summarize based on your interests
- Publish to your static site when you create content

### Interactions
- **References** - Link to others' posts from your site
- **Replies** - Publish replies with backlinks (webmention-style)
- **Annotations** - Keep local notes about external content
- **Curation** - Publish "links I'm reading" pages

## What This Enables

- **Decentralized social** - Own your content and connections
- **Agent discovery** - Find sites through links from followed sites
- **Content synthesis** - Agents read multiple sources and summarize
- **Persistent identity** - Your site is your identity, outlives platforms

## Status

Early concept development. Documenting ideas and working toward initial implementation.
