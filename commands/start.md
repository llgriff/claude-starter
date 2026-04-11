First-run setup. Discover what the user wants to do and build their environment around it.

Voice input is encouraged throughout. Mac: Fn+Fn for dictation. Windows: Win+H. People are more expressive speaking than typing.

## Process

### 1. Check if already set up
If `profile.md` exists in the repo root, read it and say: "I've got your profile from last time. Want to pick up where we left off, or start fresh?"

### 2. Discovery (5 minutes, conversational)

Ask these questions one at a time. Wait for a response before moving on. Be warm and conversational, not interrogative. The user may be brand new to AI tools. Don't assume technical fluency. Match their energy and vocabulary.

**Q1: "What do you do?"**
Not their job title. What they actually spend their time on. If they say something broad like "I manage stuff," gently probe: "Like what kind of stuff? Walk me through yesterday." The specifics are where the value lives.

**Q2: "What's tedious?"**
What do they do repeatedly that feels like it should be easier? This is where the value lives. Examples to prompt if they're stuck: "Do you write a lot of emails? Manage tasks? Research things? Keep track of people? Write docs? Organize files? Plan events?"

**Q3: "What tools do you live in?"**
Which apps/services are open on their screen right now? Gmail, Slack, Notion, Google Calendar, VS Code, Notes, Messages, Safari? This maps to MCP connections. For non-technical users, focus on the apps they actually use, not developer tools.

**Q4: "If AI could do one thing for you this week, what would it be?"**
The concrete thing. Not "be more productive." Something specific like "help me write this email" or "organize my notes" or "plan this event" or "research something I've been meaning to look into."

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

After the useful thing, briefly note what happened. Don't lecture. One or two sentences max:
- "I worked from what you told me about yourself. The more I know, the more useful I get."
- "That thing I just did? You can ask me to do that anytime. You can also teach me new tricks."

### 7. Install globally

Don't ask about global vs local. Just install globally. Most users want these everywhere.

```bash
mkdir -p ~/.claude/commands ~/.claude/skills
cp commands/*.md ~/.claude/commands/ 2>/dev/null
cp skills/*.md ~/.claude/skills/ 2>/dev/null
```

Tell them: "I've set up your skills so they work everywhere, not just in this folder."

### 8. Point them forward

Keep it to three things. Don't overwhelm.

"You're set up. Three things to know:"
1. You can talk to me in any project folder. Just type `claude` in your terminal.
2. Try `/beer` before brainstorming something. It changes how I think.
3. Just use me. Ask me to do things. The more we work together, the better I get at helping you specifically.
