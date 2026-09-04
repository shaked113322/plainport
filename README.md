# Plainport

Plainport is a public, stateless MCP server and REST API for bounded web intake and deterministic data utilities. It helps autonomous agents inspect public pages, extract metadata and links, normalize feeds and sitemaps, convert HTML to Markdown, compare text, and validate JSON Schema.

No model calls. No login. No JavaScript browser automation. No payload retention.

## Connect directly

Remote MCP (Streamable HTTP): https://plainport.exportitnow.workers.dev/mcp

The server supports MCP protocol 2026-07-28, server/discover, tools/list, and tools/call. It is stateless and returns structured JSON envelopes.

For clients that accept JSON configuration:

{
  "mcpServers": {
    "plainport": {
      "url": "https://plainport.exportitnow.workers.dev/mcp"
    }
  }
}

## Machine-readable metadata

- Documentation: https://plainport.exportitnow.workers.dev/docs
- OpenAPI: https://plainport.exportitnow.workers.dev/openapi.json
- Agent orientation: https://plainport.exportitnow.workers.dev/llms.txt
- Complete tool schemas: https://plainport.exportitnow.workers.dev/llms-full.txt
- Registry manifest: https://plainport.exportitnow.workers.dev/server.json
- MCP Server Card: https://plainport.exportitnow.workers.dev/.well-known/mcp/server-card.json
- Health: https://plainport.exportitnow.workers.dev/health

## Tools

fetch_markdown, inspect_url, extract_metadata, extract_links, parse_feed, parse_sitemap, inspect_robots, html_to_markdown, diff_text, and validate_json_schema.

All tools are read-only/idempotent. Public fetches are bounded by timeout, body-size, redirect, and rate limits. Plainport does not crawl recursively, execute JavaScript, bypass authentication, or access private network targets.

## Registry identity

Official MCP Registry name: dev.workers.exportitnow.plainport/plainport

Issues and suggestions: use the GitHub issue tracker.

## Privacy

Requests are processed in memory. The service does not intentionally store submitted URLs, request bodies, fetched content, IP addresses, or raw user agents. Operational usage metrics record only aggregate event dimensions such as interface, tool, outcome, and duration.
