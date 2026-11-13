# Lusor plugins

Plugins that give AI agents real phones through [Lusor](https://lusor.ai): your own iPhone or Android phone, or a Lusor Phone in the cloud.

| Plugin | What it does |
| --- | --- |
| [`lusor`](plugins/lusor) | Connects your agent to the Lusor MCP server at `https://mcp.lusor.ai/mcp`, so it can run tasks on your phones and control them directly. |

The plugin follows the [Agent Plugins](https://agent-plugins.org) standard and carries the manifests Cursor, Factory Droid, Grok Build, Hermes Agent and Perplexity read. Install steps for each app are in the [plugin's README](plugins/lusor/README.md).

## Factory Droid

```bash
droid plugin marketplace add lusor-ai/plugins
droid plugin install lusor@plugins
```

## Other apps

Any app that supports remote MCP servers can add `https://mcp.lusor.ai/mcp` directly. See [Connect an AI app](https://docs.lusor.ai/connect).

## License

[MIT](LICENSE)
