# Claude Starter

A launchpad for working with AI effectively. Not a tutorial. A working environment that grows with you.

## Quick Start

### Option 1: Clone and go (recommended)

```bash
git clone https://github.com/llgriff/claude-starter.git
cd claude-starter
claude  # opens Claude Code in the repo
```

Then type `/start` and follow the discovery flow. In 10 minutes you'll have a personalized setup doing something useful.

### Option 2: Just grab the files

If you already have a project and just want the skills and commands:

```bash
# Copy commands
curl -sL https://raw.githubusercontent.com/llgriff/claude-starter/main/commands/start.md -o ~/.claude/commands/start.md

# Copy skills
curl -sL https://raw.githubusercontent.com/llgriff/claude-starter/main/skills/crack-a-beer.md -o ~/.claude/skills/crack-a-beer.md
curl -sL https://raw.githubusercontent.com/llgriff/claude-starter/main/skills/insert-a-zyn.md -o ~/.claude/skills/insert-a-zyn.md
```

Or clone the repo and copy everything:

```bash
git clone https://github.com/llgriff/claude-starter.git /tmp/claude-starter
cp /tmp/claude-starter/commands/*.md ~/.claude/commands/
cp /tmp/claude-starter/skills/*.md ~/.claude/skills/
```

## What's Inside

### Commands (`/slash-commands`)

| Command | What It Does |
|---------|-------------|
| `/start` | First-run discovery: figures out what you want to do, scans for MCP servers to connect, builds your profile, does something useful immediately |
| `/connect` | Scans your environment and suggests MCP server connections based on the tools you actually use |
| `/level-up` | After a week of use, analyzes your patterns and suggests the next thing to add to your setup |

### Skills (thinking modes)

| Skill | When to Use |
|-------|------------|
| `/beer` | Before creative, exploratory, or brainstorming work. Widens the aperture. Loosens the grip. Follows threads. |
| `/zyn` | Before high-stakes output: deliverables, specs, anything that needs to land. Sharpens focus. Strips filler. Locks in. |

These are state modifiers, not prompts. They change HOW Claude thinks, not WHAT it does. Use them before other work:
1. `/beer` (enter divergent mode)
2. "Help me brainstorm names for my startup"
3. Output arrives with wider aperture, unexpected connections, voice

### Guides (reference)

| Guide | What It Covers |
|-------|---------------|
| `intent.md` | How to express what you want (the skill nobody teaches) |
| `working-with-ai.md` | Mental models: planning, feedback flywheel, skills, commands, hooks, memory |
| `mcp-servers.md` | What MCP servers are, which ones matter, how to connect |

## The Idea

Most people's first experience with AI coding tools is a blank prompt. That's like being handed a guitar with no tuning and no songbook. You can make noise, but it's hard to make music.

This starter kit gives you:
1. **A discovery flow** that figures out what YOU care about (not a generic demo)
2. **Two flagship skills** that teach the concept of shaping AI's thinking
3. **A progression path** from "this is cool" to "how did I work without this"
4. **Connection to your tools** via MCP servers so AI isn't trapped in a text box

The endgame: after a few weeks, your setup is uniquely yours. Your CLAUDE.md captures your preferences. Your skills capture your work modes. Your commands capture your workflows. The AI gets better at YOUR thing specifically, not just "AI stuff" generally.

## The Flywheel

```
Work with AI  ->  Notice what's tedious  ->  Correct it
     ^                                           |
     |                                           v
Use improved setup  <-  Turn corrections into skills/commands/memory
```

Every correction is an investment. It improves this output AND every future output. The people who get the most from AI tools aren't the ones who write the best prompts. They're the ones who build the best feedback loops.

## Making It Yours

This repo is a starting point. Extend it:

- Add your own commands to `~/.claude/commands/`
- Add your own skills to `~/.claude/skills/`
- Create a `~/.claude/CLAUDE.md` with your global instructions
- Tell Claude to remember your preferences (they persist across conversations)
- Run `/level-up` periodically to see what to add next

## Requirements

- [Claude Code](https://claude.ai/code) (CLI or desktop app)
- That's it. MCP servers are optional but recommended.

## Credits

`/beer` and `/zyn` skills by [Lex Griffith](https://github.com/llgriff). Built with Claude.
