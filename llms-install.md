# Installation guide for AI agents

This is a **remote, hosted** MCP server. Do **not** clone, build, or run any code from this repository — there is no local server implementation here.

## How to add it

The server lives at:

```
https://ssf-api-cf.surfsessionfinder.com/mcp
```

For clients that natively support remote MCP servers over HTTP (e.g. Claude Desktop, Cursor, Windsurf), add a new MCP server entry pointing at that URL. No command, no args, no env vars are needed.

For clients that only support `stdio` transport, use `mcp-remote` as a bridge:

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

## Authentication

No authentication required. The server provides public session availability data.

## Verification

After install, ask the assistant: *"List the Surf Session Finder tools."* It should report:
`list_pools`, `get_session_levels`, `find_sessions`.

Then try: *"Are there any beginner sessions available at Urbnsurf Sydney this week?"*

## What it does

Surf Session Finder gives AI assistants real-time access to wave pool session availability across 10+ pools on 5 continents:

- **Australia**: Urbnsurf Sydney, Urbnsurf Melbourne
- **UK**: The Wave (Bristol), Lost Shore (Edinburgh)
- **USA**: Skudin Surf (NJ), Waco Surf (TX), Atlantic Park Surf (VA)
- **Europe**: O2 Surftown Munich (Germany)
- **Israel**: SRF Park Tel Aviv
- **Brazil**: SurflandBrasil (Garopaba)

Sessions are served from a Cloudflare edge cache for fast, low-latency responses worldwide.
