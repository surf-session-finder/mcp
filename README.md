# Surf Session Finder MCP Server

Find available surf pool sessions worldwide — directly from your AI assistant.

## What it does

This MCP server gives AI assistants real-time access to session availability at 10+ wave pools across 5 continents. Ask questions like:

- *"Are there any beginner sessions at Urbnsurf Sydney this weekend?"*
- *"Find sessions with at least 2 available spots at The Wave Bristol"*
- *"What skill levels are available at SRF Park Tel Aviv?"*

Powered by [Surf Session Finder](https://www.surfsessionfinder.com) — served from Cloudflare's edge network for fast, low-latency responses worldwide.

## Supported pools

| Pool | Location |
|------|----------|
| Urbnsurf Sydney | Sydney, Australia |
| Urbnsurf Melbourne | Melbourne, Australia |
| The Wave | Bristol, UK |
| Lost Shore | Edinburgh, UK |
| Skudin Surf | New Jersey, USA |
| Waco Surf | Waco, TX, USA |
| Atlantic Park Surf | Virginia, USA |
| O2 Surftown | Munich, Germany |
| SRF Park Tel Aviv | Tel Aviv, Israel |
| SurflandBrasil | Garopaba, Brazil |

## Installation

**HTTP-native clients** (Claude Desktop, Cursor, Windsurf):

Add a new MCP server pointing at:
```
https://ssf-api-cf.surfsessionfinder.com/mcp
```

**stdio clients** (via `mcp-remote` bridge):

```json
{
  "mcpServers": {
    "surf-session-finder": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://ssf-api-cf.surfsessionfinder.com/mcp"]
    }
  }
}
```

No authentication required. No API keys. No local setup.

## Tools

| Tool | Description |
|------|-------------|
| `list_pools` | List all supported surf pools with IDs and locations |
| `get_session_levels` | Get skill levels available at a pool (Beginner, Intermediate, etc.) |
| `find_sessions` | Find available sessions — filter by level, spots, and time window |

## Verification

After installing, ask your assistant: *"List the Surf Session Finder tools."*

It should report: `list_pools`, `get_session_levels`, `find_sessions`.

## Links

- Website: [surfsessionfinder.com](https://www.surfsessionfinder.com)
- MCP endpoint: `https://ssf-api-cf.surfsessionfinder.com/mcp`
