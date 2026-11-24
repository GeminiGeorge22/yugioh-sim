# Yu-Gi-Oh Sim

Yu-Gi-Oh Sim is a **Yu-Gi-Oh! simulator** you add to Claude, ChatGPT, Cursor, or VS Code. Paste a `.ydk` and ask: Is this legal on the TCG banlist? How often do I open a starter plus an extender? How many hand traps do I need going second? Goldfish this list.

Operated by **FMF Tools**.

- Live site: https://yugioh-sim.fmf-x402.workers.dev/
- MCP endpoint (Streamable HTTP): https://yugioh-sim.fmf-x402.workers.dev/mcp
- Install page: https://yugioh-sim.fmf-x402.workers.dev/install
- Tools and prices: https://yugioh-sim.fmf-x402.workers.dev/docs

No account is required. `tools/list`, deck check, and opening-hand odds are free. Paid sims are charged per successful call through MPP on Tempo or x402 on Base (USDC). Bad input is refused and is not charged.

## Install

MCP server URL: `https://yugioh-sim.fmf-x402.workers.dev/mcp`

### Claude Desktop

Settings → Connectors → Add custom connector → URL: `https://yugioh-sim.fmf-x402.workers.dev/mcp`

Or add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "yugioh-sim": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://yugioh-sim.fmf-x402.workers.dev/mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http yugioh-sim https://yugioh-sim.fmf-x402.workers.dev/mcp
```

### Cursor

`~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "yugioh-sim": {
      "url": "https://yugioh-sim.fmf-x402.workers.dev/mcp"
    }
  }
}
```

### VS Code (Copilot agent mode)

```bash
code --add-mcp '{"name":"yugioh-sim","type":"http","url":"https://yugioh-sim.fmf-x402.workers.dev/mcp"}'
```

### ChatGPT

Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create connector. Name: Yu-Gi-Oh Sim. MCP server URL: `https://yugioh-sim.fmf-x402.workers.dev/mcp`. Authentication: none.

## Tools

| MCP tool | Price |
|---|---|
| ygo_deck_check | free |
| ygo_opening_hand_odds | free |
| ygo_combo_odds | $0.001 |
| ygo_handtrap_odds | $0.001 |
| ygo_goldfish | $0.003 |

## Licence and fan notice

This repository is MIT licensed. Yu-Gi-Oh Sim is an unofficial fan tool, not affiliated with or endorsed by Konami. Yu-Gi-Oh! and card names are trademarks of their owners. Card data and banlists come from the YGOPRODeck API. Card data tools are free. Paid tools sell only our own computation and return no card data.

Contact: fmf-tools@agentmail.to
