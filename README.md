# Surf Session Finder MCP Server

> Surf park session availability notifications worldwide — powered by [Surf Session Finder](https://www.surfsessionfinder.com).

This is a **remote, hosted** Model Context Protocol (MCP) server. There is nothing to install or run locally — you connect your MCP client directly to our HTTPS endpoint.

---

## Features

- 🏄 **Browse 10+ wave pools** across 5 continents
- 🔍 **Find available sessions** filtered by skill level, available spots, and time window
- 📋 **List skill levels** per pool (Beginner, Intermediate, Advanced, etc.)
- 🌐 **No authentication required** — no API keys, no sign-in
- ⚡ **Served from Cloudflare's edge network** for fast, low-latency responses worldwide

## Tools

| Tool | Description |
|------|-------------|
| `list_pools` | List all supported surf pools with IDs and locations |
| `get_session_levels` | Get skill levels available at a pool |
| `find_sessions` | Find available sessions — filter by level, spots, and time window |

## Endpoints

| Purpose | URL |
|---------|-----|
| MCP endpoint (HTTP transport) | `https://ssf-api-cf.surfsessionfinder.com/mcp` |
| Discovery manifest | `https://www.surfsessionfinder.com/.well-known/mcp.json` |

---

## Installation

### Claude Desktop / Claude.ai

Add a custom connector pointing at:

```
https://ssf-api-cf.surfsessionfinder.com/mcp
```

### Cursor / Windsurf / Other MCP clients with remote-server support

```json
{
  "mcpServers": {
    "surf-session-finder": {
      "url": "https://ssf-api-cf.surfsessionfinder.com/mcp"
    }
  }
}
```

### Clients that only support stdio (e.g. older Claude Desktop versions)

Use [`mcp-remote`](https://www.npmjs.com/package/mcp-remote) as a bridge:

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

---

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

---

## Example prompts

Once connected, try asking your AI assistant:

- *"Are there any beginner sessions at Urbnsurf Sydney this weekend?"*
- *"Find sessions with at least 2 available spots at The Wave Bristol."*
- *"What skill levels are available at SRF Park Tel Aviv?"*
- *"List all surf pools in the USA."*

## Use cases

- Planning a surf trip around session availability
- Monitoring wave pool bookings across multiple locations
- Building alerts or summaries for surf communities
- Integrating live session data into travel or sports apps

## Verification

After installing, ask your assistant: *"List the Surf Session Finder tools."*

It should report: `list_pools`, `get_session_levels`, `find_sessions`.

## Support

- 📧 Email: feedback@surfsessionfinder.com
- 🌐 Contact: https://www.surfsessionfinder.com/contact/
- 🌐 Website: https://www.surfsessionfinder.com

## License

This documentation repository is published under the MIT License.
The Surf Session Finder service itself is governed by the [Surf Session Finder Terms of Service](https://www.surfsessionfinder.com/terms/).
