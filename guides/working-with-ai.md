# Working With AI: The Mental Models

## Planning vs Doing

**When to plan:** You're about to do something that's hard to undo, touches multiple files, or you're not sure about the approach. Say "let's plan this before we build" or use plan mode.

**When to just go:** You know what you want, it's contained, and if it's wrong you can redo it. "Add a dark mode toggle to this component." Just do it.

**Most people over-plan.** They write a detailed spec for something they could have just tried. The AI can build a first version faster than you can write the spec. Try it, see if it's right, iterate. The output is the spec.

## The Feedback Flywheel

This is the most important concept. It's how a generic AI becomes YOUR AI.

1. **AI does something.** Maybe it's right. Maybe it's not.
2. **You correct it.** "No, I wanted it shorter." "Don't use bullet points." "The tone is too corporate."
3. **The correction improves this output.** Immediate value.
4. **You tell the AI to remember.** "Always write in a casual tone." Now it applies to every future conversation.
5. **Over time, patterns emerge.** Corrections cluster. Those clusters become skills, commands, or CLAUDE.md instructions.

The flywheel: work -> correct -> remember -> improve -> work better -> correct less.

The people who get the most out of AI aren't better at prompting. They run the flywheel more. Every correction is an investment.

## Skills: Changing How the AI Thinks

A skill isn't a prompt template. It's a thinking mode.

`/beer` doesn't say "write creatively." It shifts the AI into a state where the aperture widens, the inner editor steps back, and tangents become features. `/zyn` doesn't say "write carefully." It narrows focus, raises conviction, and makes filler intolerable.

The difference matters. A prompt template gives you the same output shape every time. A thinking mode changes how the AI approaches whatever comes next. You can stack them: `/beer` then "help me brainstorm names for my startup" produces fundamentally different output than the same request without the state shift.

You can create your own skills for your own work modes. Whatever mode you enter regularly that benefits from a specific cognitive shape. A "debugging" skill. A "writing for my boss" skill. A "Sunday planning" skill. Drop a markdown file in `~/.claude/skills/` and it's available everywhere.

## Commands: Repeatable Workflows

When you find yourself typing the same multi-step instructions, make it a command.

A command is a markdown file in `~/.claude/commands/` that defines a workflow. You invoke it with `/command-name`. Examples:
- `/start` runs a discovery flow (you've already seen this)
- `/daily` could be your morning briefing (check email, calendar, tasks)
- `/review` could be a code review checklist
- `/publish` could be your blog post workflow

The bar: if you've done the same sequence three times, it's a command. Don't over-think it. A command can be three lines. It can also be a hundred. Start simple, extend when you need to.

## Hooks: Automatic Behaviors

Hooks trigger automatically on events. You don't invoke them. They fire when something happens.

Examples:
- Before every commit: run the linter
- After every file edit: check for security issues
- On session start: load relevant context

Hooks live in `~/.claude/settings.json`. You probably don't need them on day one. They become useful when you notice yourself saying "I always want X to happen after Y." That's a hook waiting to be born.

## Memory: Persistence Across Conversations

Each conversation starts fresh. Memory fixes that.

When you tell Claude to remember something, it saves to a file that gets loaded into every future conversation. Use it for:
- Preferences: "I prefer TypeScript over JavaScript"
- Context: "I'm building a task manager app called TodoFlow"
- People: "My cofounder Sarah handles design"
- Corrections: "Never use em dashes in my writing"

Memory is what turns a stranger you re-explain everything to into a collaborator who knows your context. It's the most underused feature. Most people never tell the AI to remember anything, then wonder why every conversation starts from zero.

## MCP: Connecting to Your Tools

MCP servers let the AI interact with external services: email, calendar, task managers, design tools. Without them, the AI can only see files. With them, it becomes part of your actual workflow.

Run `/connect` to scan your environment and set things up. It takes a few minutes and the difference is immediate.

## CLAUDE.md: Your Global Instructions

This is the file that makes everything else work. It loads into every conversation and tells the AI who you are, how you work, and what matters to you.

A good CLAUDE.md includes:
- Who you are and what you're building
- How you like to communicate (direct? casual? formal?)
- What to avoid (things that annoy you, patterns that don't work)
- Key context (people, projects, tools)

Without a CLAUDE.md, every conversation starts generic. With one, every conversation starts from your context. The difference compounds fast.

Create yours at `~/.claude/CLAUDE.md`. Start with three lines. Add to it when you notice the AI missing context it should have.

## The Progression

**Week 1:** You're using the AI for tasks. It's helpful but generic. You correct it a lot.

**Week 2:** You've told it to remember a few things. You've tried `/beer` and `/zyn`. The corrections are getting fewer. You created your first command for something you do every morning.

**Month 1:** Your CLAUDE.md has 20 lines. You have 3-4 custom commands. Memory captures your key preferences. The AI feels like it knows you. You start thinking out loud instead of crafting careful requests.

**Month 3:** The AI is a collaborator, not a tool. It knows your projects, your people, your style. You express raw intent and get output that matches what you were thinking. You've forgotten what it was like to start every conversation from scratch.

That's the arc. Everything in this repo is designed to accelerate it.
