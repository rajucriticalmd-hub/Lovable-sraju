# Lovable-sraju

Installs the official **Lovable Cursor plugin** (MCP + commands + skills + rules) so Cursor can create, iterate, and deploy Lovable apps.

## Install Lovable MCP through Cursor (recommended)

### Option A — Marketplace plugin (best)

1. Open **Cursor Desktop**
2. Open **Customize** (sidebar) or go to [cursor.com/marketplace](https://cursor.com/marketplace) and search **Lovable**
3. Install / enable the **Lovable** plugin (`/add-plugin lovable`)
4. Reload the window if prompted
5. On the first Lovable tool call, complete Lovable OAuth in the browser
6. Confirm in **Settings → MCP** that `lovable` is connected

### Option B — One-click MCP deeplink

On a machine with Cursor Desktop installed, open:

```text
cursor://anysphere.cursor-deeplink/mcp/install?name=lovable&config=eyJ0eXBlIjogImh0dHAiLCAidXJsIjogImh0dHBzOi8vbWNwLmxvdmFibGUuZGV2Lz9zcmM9Y3Vyc29yLXBsdWdpbiIsICJhdXRoIjogeyJDTElFTlRfSUQiOiAiNmQ0NjVmNTgzZTFlNGNlNTgwMWIxNjE2ZjczNTY3MGMifX0
```

Then sign in when Cursor prompts you.

### Option C — This repo already has the plugin files

This project vendors the official plugin:

| Path | What it provides |
| --- | --- |
| `.cursor/mcp.json` | Lovable MCP server (`https://mcp.lovable.dev/?src=cursor-plugin`) |
| `.cursor/commands/` | `/lovable-new`, `/lovable-iterate`, `/lovable-db`, `/lovable-deploy` |
| `.cursor/skills/` | Scaffold / iterate / database / deploy skills |
| `.cursor/rules/` | Lovable workflow + Cloud DB safety rules |
| `.cursor/plugins/lovable/` | Full plugin copy (same as marketplace) |

Open the repo in Cursor Desktop → reload → authenticate on first tool use.

## After install

```
/lovable-new a client portal where customers log in and pay invoices with Stripe
```

Or ask naturally: “List my Lovable workspaces.”

## Note about Cloud Agents

Lovable MCP uses **OAuth only** (browser sign-in). Cloud Agents cannot finish that handshake. Use **Cursor Desktop** for install + auth; once connected there, Grok (or any model) can call Lovable tools.
