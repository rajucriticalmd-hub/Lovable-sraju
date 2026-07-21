# Lovable-sraju

Wires [Lovable MCP](https://mcp.lovable.dev) for **Cursor** (including Grok as the model) and the **Grok CLI**.

## Cursor (Grok model included)

Once Lovable MCP is connected in Cursor, every model — including Grok — can call its tools.

1. Open this repo in **Cursor Desktop** (OAuth needs a browser; cloud agents cannot finish sign-in).
2. Confirm project config exists at `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "lovable": {
      "type": "http",
      "url": "https://mcp.lovable.dev",
      "auth": {
        "CLIENT_ID": "6d465f583e1e4ce5801b1616f735670c"
      }
    }
  }
}
```

3. Reload the window (**Cmd/Ctrl+Shift+P** → “Developer: Reload Window”).
4. Open **Settings → MCP** and enable `lovable` if needed.
5. On the first Lovable tool call, complete the Lovable OAuth browser sign-in.
6. Ask Grok (or any model): “List my Lovable workspaces.”

Optional: install the [Lovable Cursor plugin](https://docs.lovable.dev/integrations/lovable-mcp-server) for `/lovable-new`, `/lovable-iterate`, `/lovable-db`, `/lovable-deploy`.

## Grok CLI

Project config is at `.grok/config.toml`. Grok also auto-loads `.cursor/mcp.json`.

```bash
# From this repo
grok mcp list
grok mcp doctor lovable

# Or add explicitly
grok mcp add --transport http --scope project lovable https://mcp.lovable.dev
```

First tool use opens a browser OAuth flow; tokens are stored in `~/.grok/mcp_credentials.json`.

**Caveat:** Lovable’s OAuth allowlist currently lists ChatGPT, Claude, Claude Code, Cursor, and VS Code. If Grok CLI OAuth fails as an unsupported client, use **Cursor with Grok selected as the model** — that path is officially supported.

## After you’re connected

- “List my Lovable workspaces”
- “Create a Lovable project that …”
- “Iterate on project … and add …”
- “Deploy project … and give me the live URL”

Calls use your real Lovable account and credits. See `.cursor/skills/lovable-mcp/SKILL.md` for the tool workflow.
