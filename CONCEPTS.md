# Core Concepts

## Pub/Sub Without Servers

Traditional pub/sub: subscribers connect to a broker, publishers push updates.

Agent networks: "publishing" is updating your static site, "subscribing" is your agent checking sites for updates.

No broker. No persistent connections. Just static content and agents that know how to read it.

## The Follower Graph

`following.json` on your site declares who you follow. Other agents can read this to discover connections.

Your agent builds a local graph:
- Sites you follow directly
- Sites they reference
- Common connections
- Citation patterns

This graph is local to you. Your agent doesn't need to ask anyone for it.

## Agent as Interface Layer

The web before platforms was hard to navigate. RSS readers helped but required manual curation.

Agents change this:
- They understand content semantically (LLMs)
- They navigate links intelligently
- They filter based on your actual interests
- They synthesize across sources

The agent is your personal interface to the distributed web.

## Interactions Without Real-Time

You can't "like" or "comment" on someone's static site in real-time. But you can:

**Reference** - Link to their content from your site
**Reply** - Publish a post with a backlink
**Curate** - Add to a "reading" or "links" page
**Annotate** - Keep local notes (never public unless you choose)

Interactions are async by default. This is a feature, not a limitation.

## Discovery Through Links

How do you find new sites? Your agent:
1. Reads sites you follow
2. Extracts links from their content
3. Checks `following.json` files
4. Discovers sites referenced frequently
5. Suggests based on topic overlap with your interests

Discovery is organic. No algorithm, no recommendation engine—just following links.

## Why This Works Now

**Static site generators** - Easy to publish
**LLMs** - Agents can understand content
**RSS/JSON feeds** - Structured data is available
**Cheap hosting** - Static sites cost nothing
**Local agents** - You run them, you control them

The pieces exist. We're just wiring them together differently.

## What Makes It Decentralized

- No central platform owns your identity
- No API keys or rate limits
- No terms of service to violate
- No algorithm deciding what you see
- No company can shut it down

Your site, your agent, your control.
