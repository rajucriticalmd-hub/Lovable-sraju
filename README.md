# Lovable-sraju

Cursor project wired to the [Lovable MCP server](https://mcp.lovable.dev) so an agent can create, iterate, and deploy Lovable apps from this workspace.

## Connect Lovable MCP in Cursor

1. Open this repo in **Cursor Desktop** (OAuth needs a browser).
2. Confirm `.cursor/mcp.json` is present (already in this repo).
3. Reload the Cursor window (**Cmd/Ctrl+Shift+P** → “Developer: Reload Window”).
4. On the first Lovable tool call, sign in to your Lovable account when prompted.
5. In **Settings → MCP**, confirm `lovable` shows as connected.

Optional: install the [Lovable Cursor plugin](https://docs.lovable.dev/integrations/lovable-mcp-server) for slash commands (`/lovable-new`, `/lovable-iterate`, `/lovable-db`, `/lovable-deploy`).

## What you can ask once connected

- “List my Lovable workspaces”
- “Create a Lovable project that …”
- “Iterate on project … and add …”
- “Deploy project … and give me the live URL”

Tool calls use your real Lovable account, credits, and projects. See `.cursor/skills/lovable-mcp/SKILL.md` for the recommended workflow and tool reference.
