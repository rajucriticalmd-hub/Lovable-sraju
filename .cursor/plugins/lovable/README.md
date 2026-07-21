# Lovable for Cursor

Build and ship [Lovable](https://lovable.dev) apps without leaving Cursor. The plugin wires Cursor to the Lovable MCP server, then adds rules, skills, and commands so the agent knows how to use it.

Lovable builds full-stack apps (TypeScript, Tailwind, shadcn/ui) in a cloud sandbox with a live preview. You describe what you want; the Lovable agent writes and edits the code, and rebuilds the preview after each reply. This plugin lets Cursor do that driving.

## What you get

- **MCP connection** to `https://mcp.lovable.dev`. On first use it opens a browser to sign in to your Lovable account (OAuth). No keys to paste.
- **Skills** the agent reaches for on its own:
  - `scaffold-lovable-project` — start a project from a brief
  - `iterate-with-lovable-agent` — make and verify changes on an existing project
  - `enable-lovable-cloud-database` — provision and query a Postgres database safely
  - `deploy-lovable-project` — publish and check traffic
- **Commands** you can run directly: `/lovable-new`, `/lovable-iterate`, `/lovable-db`, `/lovable-deploy`.
- **Rules** that keep the agent honest: plan before risky edits, read the diff before claiming a change is done, and treat `query_database` as production access.

## Install

Add this marketplace in Cursor, then enable the **Lovable** plugin. The first call to a Lovable tool triggers the sign-in.

If you only want the raw connection without the skills and commands, add the server to your Cursor MCP config:

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

## Using it

Start something new:

```
/lovable-new a client portal where customers log in, see their invoices, and pay outstanding ones with Stripe
```

Change something that exists:

```
/lovable-iterate on the invoices page, move the "Pay now" button into the row and disable it once an invoice is paid
```

Each project has two links the tools return: the **editor URL** for visual edits and the **preview URL** for the running app. Share the preview URL when someone wants to see the result.

## A few things worth knowing

- The code lives in Lovable's sandbox, not your local repo. You change it through messages, then read `get_diff` to see what actually changed.
- `query_database` runs with full permissions. The rules in this plugin tell the agent to read before it writes and to confirm destructive SQL first — keep that.
- Persistent guidance (tone, naming, components to reuse) belongs in project or workspace knowledge, set once, instead of repeated in every message.

## Links

- Lovable MCP docs: https://docs.lovable.dev/integrations/lovable-mcp-server
- Lovable MCP source: https://github.com/lovablelabs/mcp
- Integration catalog: https://docs.lovable.dev/integrations/introduction
