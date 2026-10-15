# Settings

The Settings page uses a **left nav + content area** layout. After changing options, click **Save Settings** in the top-right corner to persist changes locally.

## Settings Tabs

| Tab | Description |
|-----|-------------|
| **General** | Theme, log level, body/WebSocket capture limits, workspace paths |
| **Proxy** | Listen port, bind address, upstream proxy |
| **Browser** | Default browser, custom path, incognito, CDP debug port |
| **Certificate** | CA path, export/regenerate, GM SPKI display |
| **About** | App version |

::: tip Where to configure AI
Model, providers, MCP, Engram, and Skills live under **AI window → Settings** (see [AI Features](./ai.md)). The main Settings page has no AI tab.
:::

::: tip Workspace paths
Under **General → Local Workspace**, view and open the app data root, config file, database, certificates, reports, and plugin directories.
:::

## General

| Option | Description |
|--------|-------------|
| Theme | Dark / Light / System / Custom (presets and color tuning) |
| Log level | Info or Debug |
| Max request body capture | MB, default 10 |
| Max WebSocket message capture | MB, default 1 |

## Proxy

| Option | Default | Description |
|--------|---------|-------------|
| Proxy port | `8080` | Local MITM listen port |
| Listen address | `127.0.0.1` | Bind IP |
| Upstream proxy | empty | Optional, e.g. `http://proxy.corp:8080` |

::: info Domain filtering
Domain exclude rules are configured in the **Forwarder** filter bar, not in Settings.
:::

## Browser

| Option | Description |
|--------|-------------|
| Default browser | Auto-detected Chrome / Firefox / Edge, etc. |
| Custom browser path | Override executable path |
| Incognito / private mode | Add privacy launch flags |
| Auto-clean profile on exit | Remove the current project's browser profile before each launch (`browser-profile/{projectId}/`); other projects are unaffected |
| Extra launch args | e.g. `--window-size=1280,720` |
| CDP remote debug port | Browser Agent entry for Chromium, often `9222` |

**Launch Browser** in the title bar injects proxy and certificate-related flags automatically.

## Certificate

| Action | Description |
|--------|-------------|
| View CA path | Generated on first proxy start |
| Export root CA | Export for OS/browser trust store |
| Regenerate CA | New key pair; reinstall required |
| CA key password | Optional, stored locally |
| GM SPKI fingerprint | SM3 display only; signing algorithm unchanged |

Platform install guides are shown on the **Certificate** tab.

## AI configuration

These sections map to **AI window → Settings** navigation (shared local config with main Settings).

### Chat Model

| Option | Description |
|--------|-------------|
| Active Provider | Provider used for chat |
| Model | Pick from list or type a custom model name |
| Max Tokens | Max tokens per reply |
| Temperature | Sampling temperature 0–2 |
| Tool round limit | Max consecutive tool calls per user message |
| Context window preview | Click **Re-resolve** for current model context limit |

### Extensions (modals)

Click a card to open a modal. Changes apply to the current draft immediately; click **Save Settings** to persist.

| Card | Contents |
|------|----------|
| **Provider** | API key, base URL, model list, default context tokens |
| **Engram memory** | Cross-session recall, summaries, enable switch |
| **MCP Servers** | Stdio / HTTP-SSE transport, reconnect status |
| **Dynamic Tools** | Shell subprocess tools, parameter schema |
| **AI Agent** | Personas and system prompts |
| **Skills** | SKILL.md packs and tool scope |
| **Advanced** | Tool permissions, context budget, Ollama `/api/show`, Python sandbox |

#### MCP example (Stdio)

In the **MCP Servers** modal:

| Field | Example |
|-------|---------|
| Name | `filesystem` |
| Transport | Stdio |
| Command | `npx` |
| Args | `-y, @modelcontextprotocol/server-filesystem, /path/to/dir` |

Save, then **Reconnect** in the modal to verify connected servers and tool counts.

## Config file

Advanced options are stored in the app data directory and maintained when you save settings. **Manual editing is not recommended.** For bulk deployment or enterprise customization, contact support.

## Troubleshooting

### Settings not applied

1. Confirm **Save Settings** was clicked
2. Restart and set log level to Debug under General

### Certificate / HTTPS capture issues

1. Install CA into the **trusted root** store
2. Re-export after CA regeneration
3. Firefox uses a separate certificate store

### AI connection failures

1. Check API key and base URL under **AI window → Settings → Provider**
2. Reconnect MCP servers and verify status
3. Confirm you clicked **Save Settings**
