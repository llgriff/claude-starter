Check how the user has been working and suggest the next thing to add to their setup.

Run this after a week of use, or whenever things feel like they could be better.

## Process

### 1. Read their profile
Read `profile.md` for context on who they are and what they set up.

### 2. Check what they have
```bash
echo "=== Commands ==="
ls ~/.claude/commands/ 2>/dev/null || echo "none"
echo "=== Skills ==="
ls ~/.claude/skills/ 2>/dev/null || echo "none"
echo "=== MCP Servers ==="
cat ~/.claude/settings.json 2>/dev/null | python3 -c "import sys,json; d=json.load(sys.stdin); [print(f'  {k}') for k in d.get('mcpServers',{})]" 2>/dev/null || echo "none"
echo "=== Memory ==="
ls ~/.claude/memory/ 2>/dev/null || echo "none"
echo "=== CLAUDE.md ==="
test -f ~/.claude/CLAUDE.md && echo "exists" || echo "not created yet"
```

### 3. Check recent usage
```bash
python3 -c "
import json, datetime, collections
cmds = collections.Counter()
topics = []
count = 0
with open('$HOME/.claude/history.jsonl') as f:
    for line in f:
        entry = json.loads(line)
        ts = entry.get('timestamp', 0)
        dt = datetime.datetime.fromtimestamp(ts/1000)
        if dt < datetime.datetime.now() - datetime.timedelta(days=7):
            continue
        count += 1
        display = entry.get('display', '')
        if display.startswith('/'):
            cmds[display.split()[0]] += 1
        # Look for repeated phrases
        lower = display.lower()
        for kw in ['always', 'every time', 'again', 'remember', 'don\\'t forget']:
            if kw in lower:
                topics.append(display[:100])

print(f'Messages in last 7 days: {count}')
print(f'Commands used: {dict(cmds)}')
if topics:
    print(f'Correction/preference signals:')
    for t in topics[-5:]:
        print(f'  {t}')
" 2>/dev/null
```

### 4. Suggest next steps based on where they are

**If they have no custom CLAUDE.md:**
"You should create a personal CLAUDE.md at `~/.claude/CLAUDE.md`. This is your global instruction set. Tell Claude who you are, how you like to work, what to avoid. It loads into every conversation automatically."

**If they have no memory files:**
"When you tell me something important about your preferences or your projects, I can save it so I remember across conversations. Try telling me something to remember."

**If they haven't connected any MCP servers:**
"Run `/connect` to wire me into your actual tools. Right now I can only see files. With MCP, I can read your email, check your calendar, manage your tasks."

**If they only have beer/zyn skills:**
"You've been using the state-modifier skills. Now try creating your own. Think about a type of work you do often. What thinking mode does it need? Write a skill that puts Claude in that mode."

**If they've been using commands but haven't created their own:**
"I see you've been doing [repeated pattern]. Want to turn that into a slash command? It would save you from typing the same thing each time."

**If they've been correcting Claude repeatedly:**
"I noticed you've told me [pattern] a few times. Want to save that as a permanent instruction? I'll add it to your CLAUDE.md so you never have to say it again."

### 5. Offer one concrete action

Don't give them a list of 10 things. Pick the ONE highest-impact next step and offer to do it right now.

"The most useful thing you could add right now is [X]. Want me to set it up?"
