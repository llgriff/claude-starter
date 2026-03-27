# Working With AI: The Mental Models

## Planning vs Doing

**When to plan:** You're about to do something that's hard to undo, touches multiple files, or you're not sure about the approach. Say "let's plan this before we build" or use plan mode.

**When to just go:** You know what you want, it's contained, and if it's wrong you can redo it. "Add a dark mode toggle to this component." Just do it.

**Most people over-plan.** They write a detailed spec for something they could have just tried. The AI can build a first version faster than you can write the spec. Try it, see if it's right, iterate.

## The Feedback Flywheel

This is the most important concept. It's how a generic AI becomes YOUR AI.

1. **AI does something.** Maybe it's right. Maybe it's not.
2. **You correct it.** "No, I wanted it shorter." "Don't use bullet points." "The tone is too corporate."
3. **The correction improves this output.** Immediate value.
4. **You tell the AI to remember.** "Always write in a casual tone." Now it applies to EVERY future conversation.
5. **Over time, patterns emerge.** Corrections cluster. Those clusters become skills, commands, or CLAUDE.md instructions.

The flywheel: work -> correct -> remember -> improve -> work better -> correct less.

## Skills: Changing How the AI Thinks

A skill isn't a prompt template. It's a thinking mode.

`/beer` doesn't say "write creatively." It shifts the AI into a state where:
- The aperture widens (more connections, more possibilities)
- The inner editor steps back (half-formed ideas are welcome)
- Threads get followed (tangents are features, not bugs)

`/zyn` doesn't say "write carefully." It shifts to:
- The aperture narrows (one target, one context, one person)
- Conviction goes up (decide what you think, then say it)
- Filler becomes intolerable (every word carries weight)

You can create your own skills for your own work modes. A "customer support" skill. A "code review" skill. A "journaling" skill. Whatever mode you enter regularly that benefits from a specific cognitive shape.

## Commands: Repeatable Workflows

When you find yourself typing the same multi-step instructions, make it a command.

A command is a markdown file in `~/.claude/commands/` that defines a workflow. You invoke it with `/command-name`. Examples:
- `/start` runs a discovery flow (you've already seen this)
- `/daily` could be your morning briefing (check email, calendar, tasks)
- `/review` could be a code review checklist
- `/publish` could be your blog post workflow

The bar for creating a command: if you've done the same sequence three times, it's a command.

## Hooks: Automatic Behaviors

Hooks trigger automatically on events. You don't invoke them. They fire when something happens.

Examples:
- Before every commit: run the linter
- After every file edit: check for security issues
- On session start: load relevant context

Hooks live in `~/.claude/settings.json`. You probably don't need them on day one. They become useful when you have a behavior you want to ALWAYS happen without having to remember to ask.

## MCP: Connecting to Your Tools

MCP (Model Context Protocol) servers let Claude interact with external services. Without MCP, Claude can only see files. With MCP, Claude can:
- Read your email and draft responses
- Check your calendar and schedule meetings
- Create and update tasks in Linear/Notion
- Read Figma designs and write code from them

Run `/connect` to see what's available and set things up.

## Memory: Persistence Across Conversations

Each conversation with Claude starts fresh. Memory fixes that.

When you tell Claude to remember something, it saves to a file that gets loaded into every future conversation. Use it for:
- Preferences: "I prefer TypeScript over JavaScript"
- Context: "I'm building a task manager app called TodoFlow"
- People: "My cofounder Sarah handles design"
- Corrections: "Never use em dashes in my writing"

Memory is what turns Claude from a stranger you re-explain everything to into a collaborator who knows your context.
