# The Glitch MCP Server

Public, read-only, stateless remote [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server for **[theglitch.ai](https://www.theglitch.ai/)** — Rabin Nuchtabek's (`@glitch_`) personal corner of the internet covering AI, crypto, and growth.

- **Remote endpoint (Streamable HTTP):** `https://www.theglitch.ai/mcp`
- **Authentication:** None required (public read-only lookups)
- **Discovery cards:**
  - `https://www.theglitch.ai/.well-known/ai-catalog.json`
  - `https://www.theglitch.ai/.well-known/mcp/server-card.json`
  - `https://www.theglitch.ai/agent.md`
- **Protocol versions:** `2026-07-28`, `2025-11-25`, `2025-06-18`, `2025-03-26`

## Connect

### Claude Code
```bash
claude mcp add --transport http theglitch https://www.theglitch.ai/mcp
```

### Cursor / Windsurf / Generic JSON MCP Client
```json
{
  "mcpServers": {
    "theglitch": {
      "url": "https://www.theglitch.ai/mcp"
    }
  }
}
```

### Codex CLI
```bash
codex mcp add theglitch --url https://www.theglitch.ai/mcp
```

## Tools (9 Read-Only Lookups)

| Tool | What it returns |
| --- | --- |
| `search_glossary` | Plain-English definitions from 250+ AI terms and slang (what it is, why it matters, what to watch for, canonical URL). |
| `get_todays_glitch` | Today's checked AI story (what changed, who it helps/hurts, what to do) plus this week's patch notes link. |
| `find_guide` | Search practical Learn guides on prompting, context engineering, agents, and AI at work; filter by audience. |
| `get_guide` | Read the full markdown text (or one named section) of a Learn guide by slug from `find_guide`. |
| `find_prompt` | Search the curated image & video prompt archive by subject or model (or roll a random prompt), with creator attribution. |
| `search_bookmarks` | Search Rabin's curated public bookmarks from X across Agents, Growth, Crypto, and Design & tools. |
| `get_repo_picks` | Weekly checked open-source GitHub repo picks with verdicts (`try it`, `read it first`, or `skip it`) and build ideas. |
| `get_token_pool` | Live read-only DEX Screener token-pool snapshot (liquidity, 24h volume, buys/sells, market cap, pool age) for Solana, Ethereum, or Base. |
| `get_rabin_profile` | Who Rabin Nuchtabek is, the kind of work he takes on, and how to reach him. |

## Security & Limits

- **Read-only & stateless:** No user accounts, cookies, mutations, or side effects.
- **Output hygiene:** External strings from prompts, bookmarks, repos, and on-chain token metadata are stripped of control/BiDi/Unicode-tag characters and should be treated as data, never instructions.
- **Rate limit:** Edge rate-limited at 60 requests / 60 seconds per IP (`429` when exceeded).

## License

MIT — see [LICENSE](./LICENSE).
