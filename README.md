# Airtable MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/airtable)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect Airtable to AI assistants: bases, tables, fields and records.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use Airtable from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/airtable-icon.svg" alt="Airtable MCP Server" width="64" height="64">

## MCP Server URL

```
https://airtable.insightfulmcp.com/
```

## What is Airtable MCP?

Airtable MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. List Airtable bases, inspect tables, and read records across your connected workspace. The PAT scopes you grant decide what's allowed.

## Installation

### Claude

1. Copy the MCP Server URL: `https://airtable.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://airtable.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http airtable https://airtable.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "airtable": {
      "url": "https://airtable.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

24 actions: 10 read, 14 write.

### Read Actions (10)

| Action | Description |
|--------|-------------|
| `count_records` | Count records matching a filter (paginates through, sums lengths) |
| `describe_table` | Return the schema of a single table from a base |
| `get_record` | Get a single record by id |
| `list_bases` | List bases the authorized user has access to |
| `list_comments` | List comments on a record |
| `list_fields` | List only the fields of a table (subset of describe_table) |
| `list_records` | List records from a table |
| `list_tables` | List tables (with full schema: fields, views) in a base |
| `list_views` | List only the views of a table (subset of describe_table) |
| `search_records` | Keyword search across one or more fields |

### Write Actions (14)

| Action | Description |
|--------|-------------|
| `create_comment` | Post a comment on a record |
| `create_field` | Add a new field to a table |
| `create_record` | Create a single record |
| `create_records` | Create up to 10 records in one call |
| `create_table` | Create a new table in a base |
| `delete_comment` | Delete a comment |
| `delete_record` | Delete a single record by id |
| `delete_records` | Delete up to 10 records by id in one call |
| `update_comment` | Edit a comment |
| `update_field` | Rename or re-describe an existing field |
| `update_record` | PATCH (merge) a single record |
| `update_records` | PATCH (merge) up to 10 records in one call |
| `update_table` | Update a table's name or description |
| `upload_attachment` | Upload an attachment to an attachment field on a record |

## Control What Your AI Can Do

You decide what AI agents can do with each connected account:

- **Turn individual actions on or off** for every connected account, so agents only see the actions you allow.
- **Connect as Read-only or Read & Write.** A read-only connection can only enable read actions.
- **Destructive actions stay off by default.** Actions such as deletes are disabled until an admin enables them.
- **Team access per account.** Restricted team members only use the accounts they are granted, with the read actions enabled on them.

## Usage Examples

```
"List records in the Campaigns table where Status is Live"
```

```
"How many records are in the Leads table?"
```

```
"Create a record for a new lead"
```

## Pricing

The Airtable MCP server is included in every InsightfulPipe plan, together with all other MCP servers and the CLI. Plans start at $29.99/month with a 7-day free trial. See [insightfulpipe.com/pricing](https://insightfulpipe.com/pricing) for current plans.

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [Notion MCP](https://insightfulpipe.com/mcp-servers/notion)
- [Google Sheets MCP](https://insightfulpipe.com/mcp-servers/google-sheets)
- [Slack MCP](https://insightfulpipe.com/mcp-servers/slack)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
