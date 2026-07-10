> [!IMPORTANT]
> # ⚠️ This marketplace has moved — please migrate
>
> This repo is a **deprecated mirror** and will be **sunset**. The canonical
> marketplace is now:
>
> ### 👉 https://github.com/Conviva/mcp-marketplace
>
> Updates are still mirrored here **for now**, but this mirror will stop
> receiving new releases once it is sunset. Migrate now to keep getting the
> latest plugin and skills.
>
> **Claude Code**
> ```
> /plugin marketplace remove Conviva-Internal/mcp-marketplace
> /plugin marketplace add Conviva/mcp-marketplace
> /plugin install conviva-dpi-mcp@conviva
> ```
>
> **Claude Desktop** — open **Customize → Plugins**, remove this marketplace,
> then **Add marketplace → Add from a repository** with
> `https://github.com/Conviva/mcp-marketplace` and reinstall **Conviva DPI MCP**.
>
> Your hosted MCP connection keeps working throughout — only the plugin/skills
> source is moving.

---

# Conviva DPI MCP

Companion Claude plugin for **Conviva DPI MCP**. It wires the hosted Conviva DPI
MCP endpoint into Claude Code and installs the companion skills
(`exploring-context-center`, `querying-predefined-metrics`,
`retrieving-behavior-segment-details`).

> This repository is a published mirror. It is generated from Conviva's internal
> source of truth on each release — do not edit it directly.

## Install

**Claude Code** — one step; the plugin wires the MCP server **and** the skills.
Run each command on its own (the copy button copies one block at a time):

1. Add the marketplace:

   ```
   /plugin marketplace add Conviva/mcp-marketplace
   ```

2. Install the plugin:

   ```
   /plugin install conviva-dpi-mcp@conviva
   ```

**Claude Desktop** — install the plugin (above) for the skills, then add the MCP
server as a custom connector (Settings → Connectors) pointed at the endpoint below.

**Cursor** — add the server to `~/.cursor/mcp.json` (global) or `.cursor/mcp.json`
(project). This gives you the **tools** (skills are Claude-plugin-only):

```json
{
  "mcpServers": {
    "conviva": {
      "url": "https://dpi-mcp.conviva.com/mcp"
    }
  }
}
```

All clients authenticate via **Okta OAuth** in your browser on first use — no
token to paste. For step-by-step setup and troubleshooting, see
[GETTING_STARTED.md](./GETTING_STARTED.md).

## What it connects to

The plugin registers an MCP server that connects to the hosted Conviva DPI MCP
endpoint:

```
https://dpi-mcp.conviva.com/mcp
```

Access is authenticated per Conviva account — installing the plugin does not by
itself grant access to data. You must be an authorized Conviva user.

## Version

`1.0.1` — see the release tags for history. Each published version
corresponds to the identically-tagged commit in Conviva's internal repository.
