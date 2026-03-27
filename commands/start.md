First-run setup. Discover what the user wants to do and build their environment around it.

## Process

### 1. Check if already set up
If `profile.md` exists in the repo root, read it and say: "I've got your profile from last time. Want to pick up where we left off, or start fresh?"

### 2. Discovery (5 minutes, conversational)

Ask these questions one at a time. Be conversational, not interrogative.

**Q1: "What do you do?"**
Not their job title. What they actually spend their time on. Developer? Designer? PM? Student? Side-project builder? Running a business? Just curious about AI?

**Q2: "What's tedious?"**
What do they do repeatedly that feels like it should be easier? This is where the value lives. Examples to prompt if they're stuck: "Do you write a lot of emails? Manage tasks? Review code? Research things? Write docs? Organize files?"

**Q3: "What tools do you live in?"**
Which apps/services are open on their screen right now? Gmail, Slack, Linear, Notion, Figma, GitHub, Google Calendar, VS Code, Terminal? This maps to MCP connections.

**Q4: "If AI could do one thing for you this week, what would it be?"**
The concrete thing. Not "be more productive." Something specific like "help me write this proposal" or "organize my notes" or "build a side project I've been putting off."

### 3. Scan for MCP opportunities

Based on their answers AND the local environment, suggest MCP connections:

```bash
# Check what's already configured
cat ~/.claude/settings.json 2>/dev/null | python3 -c "import sys,json; d=json.load(sys.stdin); print(json.dumps(d.get('mcpServers',{}), indent=2))" 2>/dev/null || echo "No MCP servers configured"
```

Cross-reference against known MCP servers:

| Signal | MCP Server | What It Enables |
|--------|-----------|-----------------|
| Uses Gmail / Google | Google Calendar, Gmail | Read/create events, search emails, draft messages |
| Uses Slack | Slack (community) | Read/send messages, search channels |
| Uses Linear | Linear | Create/update issues, track projects |
| Uses Notion | Notion (community) | Read/update pages, search workspace |
| Uses Figma | Figma | Read designs, get design context |
| Uses GitHub | GitHub (built-in) | Already available via `gh` CLI |
| Mentions files/docs | Filesystem | Already built into Claude Code |

For each match, explain in one sentence what it enables and offer to help set it up. Don't overwhelm. Suggest the top 2-3 most relevant.

### 4. Build their profile

Write `profile.md` to the repo root:

```markdown
# Profile

## Who
[One line from Q1]

## What's Tedious
[Bullet list from Q2]

## Tools
[List from Q3]

## First Goal
[From Q4]

## MCP Servers Connected
[List what was set up, or "none yet"]

## Setup Date
[Today's date]
```

### 5. Give them something immediately useful

Based on their first goal (Q4), do ONE thing right now that demonstrates value. Not a tutorial. An actual useful output.

Examples:
- They want to write a proposal? Draft the outline right now from a 2-sentence description.
- They want to organize notes? Scan a directory they point you at and suggest a structure.
- They want to build a side project? Scaffold it.
- They want to automate something? Write the first automation.

The goal: in 10 minutes from clone, they've seen AI do something genuinely useful for THEIR specific situation. Not a demo. Their thing.

### 6. Explain what just happened

After the useful thing, briefly explain the concepts they just used:
- "That was me working from your profile (context). The more context I have, the better I get."
- "Try `/beer` before your next brainstorming session. It changes how I think."
- "If you want me to remember something across conversations, just tell me to remember it."
- "When you notice me doing something you want me to always do, that can become a skill or a hook."

### 7. Point them forward

"You're set up. Here's what to try next:"
- `/beer` or `/zyn` before your next task (experience state-modifier skills)
- `/connect` if you want to wire up more tools
- `/level-up` in a week (I'll look at how you've been working and suggest what to add next)
- Just... use me. Ask me to do things. The more you use me, the more patterns emerge that we can turn into skills.

### 8. Setup path

Ask: "Do you want these skills and commands available in every project, or just this one?"

- **Every project (global)**: Copy commands and skills to `~/.claude/commands/` and `~/.claude/skills/`
- **Just this project**: Leave them in the repo. They'll work when you open Claude Code in this directory.

If global, run the copy:
```bash
cp commands/*.md ~/.claude/commands/ 2>/dev/null
cp skills/*.md ~/.claude/skills/ 2>/dev/null
```
