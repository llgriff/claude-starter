# MCP Servers: Connecting AI to Your Tools

MCP (Model Context Protocol) lets Claude interact with external services beyond just reading files. Think of it as giving Claude hands that can reach into your other tools.

## What's Available

### Built Into Claude Code
- **Filesystem**: Already there. Claude can read and write files.
- **GitHub**: Use `gh` CLI commands. No MCP needed.
- **Web**: Claude can fetch web pages and search the web.

### Claude-Provided MCP Servers
These are first-party integrations maintained by Anthropic:
- **Google Calendar**: View schedule, create events, find free time
- **Gmail**: Search emails, read threads, draft messages
- **Linear**: Create/update issues, manage projects, track sprints
- **Figma**: Read designs, get screenshots, understand design context

### Community MCP Servers
The ecosystem is growing. Common ones:
- **Slack**: Read/send messages, search channels
- **Notion**: Read/update pages, search workspace
- **Obsidian**: Read/search your vault
- **Postgres/SQLite**: Query databases directly

## How to Set Up

Most MCP servers are added via the Claude Code CLI:

```bash
# Claude-provided servers
claude mcp add <server-name> --provider claude-ai

# Community servers (varies by server)
# Check the server's README for specific install instructions
```

After adding, restart Claude Code. The server's tools will be available immediately.

## How to Know What's Connected

```bash
# Check your current MCP servers
cat ~/.claude/settings.json | python3 -c "import sys,json; d=json.load(sys.stdin); [print(f'  {k}') for k in d.get('mcpServers',{})]"
```

Or just ask Claude: "What MCP servers do I have connected?"

## Proactive Connection

Run `/connect` to scan your environment and suggest servers based on the apps you actually use. Claude will check for installed apps, config files, and context from your conversations to recommend relevant connections.
