# Lusor

Put AI agents to work on real phones. This plugin connects your agent to [Lusor](https://lusor.ai) and your own iPhone or Android phone.

Ask in plain language, for example *"List my Lusor phones"* or *"On my phone, open Settings and turn on dark mode, then tell me what changed."*

## What your agent can do

| Tool | What it does |
| --- | --- |
| `list_phones`, `get_phone` | See your phones, whether each is online, and whether it is busy |
| `connect_phone` | Show the steps to connect your own iPhone or Android, and report when it is connected |
| `run_task`, `get_task`, `list_tasks` | Start an AI agent on a phone with a prompt, follow it, and read the result |
| `reply_to_task`, `stop_task` | Answer the agent's question, or stop a task |
| `get_screenshot`, `get_screen_state` | See the screen and its elements |
| `phone_action` | Tap, type, swipe, press a button or open an app |
| `install_app` | Install free apps from the App Store or Google Play on your phone |

That is the whole set when you sign in. With an API key instead, the agent also gets tools for Lusor Phones in the cloud (`add_phone`, `remove_phone`, `wipe_phone`, and catalog installs with `install_app` and `list_app_installs`), and two advanced tools, `search` and `execute`, that reach any Lusor API operation.

## Install

| App | How |
| --- | --- |
| Cursor | Install **Lusor** from the Cursor Marketplace, or follow [Cursor setup](https://docs.lusor.ai/connect/cursor). |
| Grok Build | Run `/plugin`, search for **Lusor** and install. |
| Factory Droid | `droid plugin marketplace add lusor-ai/plugins`, then `droid plugin install lusor@plugins`. |
| Hermes Agent | `hermes plugins install lusor`, then sign in (below). |
| Perplexity | **Plugins → Add custom → Upload plugin or skill**, and import `https://github.com/lusor-ai/plugins/tree/main/plugins/lusor`. |

Every other app that supports remote MCP servers can add `https://mcp.lusor.ai/mcp` directly. See [Connect an AI app](https://docs.lusor.ai/connect).

## Sign in

The first time the app connects, it opens the Lusor sign-in in your browser. Sign in and choose your organization. The app never sees a password or key.

In Hermes, start the sign-in once with:

```bash
hermes mcp add lusor --url https://mcp.lusor.ai/mcp --auth oauth
```

That adds a `config.yaml` entry, which replaces the plugin's entry. Add `trust: untrusted` to it to keep Hermes asking before each tool that changes something.

No account yet? Sign up at [app.lusor.ai](https://app.lusor.ai).

### API key instead

Apps that let you set request headers can send `Authorization: Bearer lusor_...` with a key from your workspace's **API keys** page in the Lusor app. See [Authentication](https://docs.lusor.ai/authentication).

## Network and data

- The plugin contains configuration only: no code, scripts or hooks.
- It connects to one endpoint, `https://mcp.lusor.ai/mcp` (Streamable HTTP, OAuth 2.1 with dynamic client registration and PKCE). Sign-in runs on `https://mcp.lusor.ai`.
- Every tool call runs as the signed-in user, in their workspace. Tool results, including screenshots and screen text, enter your session and so reach your model provider.
- **Costs and changes.** `run_task` and `install_app` use credits. Installs are free apps only, and the agent stops and asks if a store wants a password, payment or verification. Hermes is set to ask before every tool that changes something.

## Links

- [Documentation](https://docs.lusor.ai/connect)
- [Privacy Policy](https://lusor.ai/privacy)
- [Terms of Service](https://lusor.ai/terms)
- Support: [support@lusor.ai](mailto:support@lusor.ai)

## License

[MIT](../../LICENSE)
