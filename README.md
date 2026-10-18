# TarsN8N

MCP integration for n8n (workflow automation).

## Tools

- `n8n_workflows` — List available workflows
- `n8n_execute` — Execute a workflow by ID

## Quick Start

```bash
go build -o tarsn8n
TARS_MCP_ENDPOINT=https://api.example.com TARS_MCP_API_KEY=xxx ./tarsn8n
```

## Environment Variables

- `TARS_MCP_ENDPOINT` — upstream API endpoint
- `TARS_MCP_API_KEY` — upstream API key
- `TARS_MCP_MODE` — `stdio` (default) or `http`

## License

MIT
