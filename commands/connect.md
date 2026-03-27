Discover and connect MCP servers based on what tools the user actually uses.

## Process

### 1. Check current state

```bash
cat ~/.claude/settings.json 2>/dev/null | python3 -c "import sys,json; d=json.load(sys.stdin); servers=d.get('mcpServers',{}); print(f'{len(servers)} MCP servers configured:'); [print(f'  - {k}') for k in servers]" 2>/dev/null || echo "No settings.json found"
```

### 2. Scan for signals

Check the local environment for clues about what tools they use:

```bash
# Package managers and configs
ls package.json Gemfile requirements.txt go.mod Cargo.toml pyproject.toml 2>/dev/null
# Git remotes (GitHub? GitLab? Bitbucket?)
git remote -v 2>/dev/null | head -4
# Common config files
ls .env .linear .notion .slack 2>/dev/null
ls ~/.config/linear ~/.config/notion ~/.config/slack 2>/dev/null
# Check for installed apps (macOS)
ls /Applications/ 2>/dev/null | grep -iE "slack|notion|linear|figma|zoom|obsidian" 2>/dev/null | head -10
```

### 3. Ask what they use

"Based on what I can see, here's what I'd suggest connecting. Which of these do you use?"

Present a checklist with what each enables:

**Communication:**
- Slack: Read/send messages, search channels, respond to threads
- Gmail: Search emails, draft messages, read threads
- Google Calendar: View schedule, create events, find free time

**Project Management:**
- Linear: Create/update issues, track sprints, manage projects
- Notion: Read/update pages, search across workspace

**Design:**
- Figma: Read designs, get screenshots, understand design context

**Development:**
- GitHub: Already available via `gh` CLI (built into Claude Code)

### 4. Set up selected servers

For each selected, walk through the setup. Most Claude-native MCP servers:

```bash
# Example for Claude-provided servers (if available)
# claude mcp add <server-name> --provider claude-ai

# For community servers, provide the specific install command
```

After each connection, test it with a simple query to confirm it works.

### 5. Update profile

If `profile.md` exists, update the "MCP Servers Connected" section.

### 6. Show them something

For each newly connected server, demonstrate one useful thing:
- Gmail connected? "Here are your unread emails from today."
- Calendar connected? "Here's what's on your schedule tomorrow."
- Linear connected? "Here are your open issues."

The demo is the proof. Don't just tell them it works. Show them.
