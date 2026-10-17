# TarsN8N

TSG (TarsSecureGuard) MCP adapter for **N8N** — Workflow automation platform.

This is one of the **15 MCP integration projects** under github.com/HP-jh/, designed to be:

- **One-click downloadable** from TSG's MCP Marketplace
- **One-click enableable** in the TSG gateway
- **Independently versioned** (this repo) with its own release cycle
- **Tightly integrated** with TSG via the standard MCP protocol

## Quick Start

### Standalone

```bash
# Download from GitHub Releases
curl -L -o tars-n8n https://github.com/HP-jh/TarsN8N/releases/latest/download/tars-n8n-$(uname -s | tr A-Z a-z)-amd64
chmod +x tars-n8n
./tars-n8n --upstream-endpoint <your-N8N-endpoint>
```

### Via TSG MCP Marketplace

1. Open TSG admin → **MCP Marketplace**
2. Find **TarsN8N** in the list
3. Click **Download** → wait for completion
4. Click **Enable** → enter your N8N endpoint
5. The MCP server is now available to all TSG clients

## MCP Tools Exposed

| Tool | Description |
|------|-------------|
| `n8n_list_models` | List available N8N models |
| `n8n_invoke` | Invoke N8N with prompt + params |
| `n8n_health` | Health check of upstream connection |
| `n8n_status` | Current TSG integration status |

## Configuration

Configurable via env vars or `~/.tars/n8n/config.json`:

- `TARS_N8N_ENDPOINT` — upstream endpoint URL
- `TARS_N8N_API_KEY` — upstream API key (optional, for hosted services)
- `TARS_N8N_TIMEOUT` — request timeout (default 30s)
- `TARS_N8N_LOG_LEVEL` — log verbosity (default info)

## Version

- **v0.1.0** — Initial MVP (basic MCP adapter)
- See [Releases](https://github.com/HP-jh/TarsN8N/releases) for full changelog

## Cross-Repo Coordination

This repo is part of the **15 MCP integration projects** in github.com/HP-jh/. See [HP-jh/TarsSecureGuard](https://github.com/HP-jh/TarsSecureGuard) for the master gateway that orchestrates all 15.

## License

MIT — see [LICENSE](LICENSE).
