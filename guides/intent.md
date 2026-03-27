# Intent: The Only Thing That Matters

You don't need to write good prompts. You need to know what you want and be able to say it, even imperfectly. The AI's job is to parse your intent, not your grammar.

This guide is about building the muscle of expressing intent clearly and building systems that help you discover and refine your intent over time.

## Intent Is Not a Prompt

A prompt is a transaction. You write something, you get something back. Intent is a relationship. You express direction, the AI figures out the path, you course-correct, and the system gets better at understanding you.

Bad: "Write a Python function that takes a list of integers and returns the sum of all even numbers."
Fine, but you've done the AI's job for it. You figured out the implementation and dictated it.

Better: "I need to process a list of numbers and pull out a specific subset. The subset rule might change later."
Now the AI is solving the actual problem, not transcribing your solution.

Best: "I'm building a data pipeline and I keep writing the same filtering logic everywhere. Fix that."
Now the AI is solving the real problem: your architecture has a pattern that wants to be abstracted.

The deeper your intent, the more the AI can actually help. Surface-level intent gets surface-level output.

## Thinking Out Loud Is Valid

You don't need to have your thoughts organized before you speak. Speech-to-text, stream of consciousness, half-formed ideas, "I don't know exactly what I want but it's something like..." are all valid inputs.

The AI should parse for intent, not phrasing. If you say "I kind of want to, you know, make the thing that does the stuff with the users, like maybe a dashboard or something?" the AI should hear: "I want to build a user-facing view. Let me ask what data matters to you." Not: "I don't understand your request, could you be more specific?"

If your AI asks you to rephrase, the AI is broken, not your input.

## The Discovery Problem

Most people's biggest problem isn't expressing intent. It's knowing what they want in the first place. That's why `/start` exists. It's an intent discovery mechanism.

The pattern:
1. Start with what's concrete: what's tedious, what tools you use, what you wish was different
2. Let the AI reflect back what it heard: "So it sounds like you want X. Is that right?"
3. Iterate: "Not exactly. More like Y." That correction IS the intent emerging.
4. Do something concrete immediately. The output reveals whether the intent was understood.
5. Correct again. Each correction sharpens the intent.

You often don't know what you want until you see what you don't want. That's not a failure of communication. That's how intent works. Build systems that support this process instead of demanding clarity upfront.

## Levels of Intent

**Direct intent:** "Rename this function to X." You know exactly what you want. The AI executes.

**Outcome intent:** "This is slow. Fix it." You know the outcome. The AI figures out the path.

**Exploratory intent:** "I'm building a task manager. I'm not sure about the data model." You're thinking. The AI thinks with you. It should match your energy: if you're exploring, it explores. If you're deciding, it decides.

**Ambient intent:** "I'm running a turnaround consulting business and I need operational intelligence infrastructure." This is who you are and what you're building. It shapes everything. This is what goes in your CLAUDE.md and your memory: the persistent context that every conversation inherits.

Most AI interactions operate at direct intent. The real power is at outcome and exploratory levels. Ambient intent is what makes the AI genuinely yours.

## Building Intent Infrastructure

The whole point of skills, commands, memory, and CLAUDE.md is to build infrastructure for your intent. Not to write better prompts. To make the AI understand you so well that your raw, unedited, half-formed thoughts produce excellent output.

**CLAUDE.md = ambient intent.** Who you are, how you think, what matters, what to avoid. Loads into every conversation. The AI starts with your context instead of starting from zero.

**Memory = accumulated intent.** Every correction, every preference, every "always do X, never do Y" adds to the picture. Over time the corrections decrease because the AI already knows.

**Skills = intent modes.** `/beer` doesn't say "be creative." It restructures how the AI thinks so your creative intent produces better creative output. `/zyn` restructures for precision. You can build skills for any mode your intent regularly takes.

**Commands = intent patterns.** `/start` is a pattern for "I have a new person who doesn't know what they want yet." `/level-up` is a pattern for "I've been working for a week, what should evolve?" When you notice yourself expressing the same kind of intent repeatedly, capture the pattern.

**This repo = an intent discovery machine.** The whole thing is designed to extract your intent progressively, from "I don't know what I want" to "my AI knows me so well I can think out loud and it does the right thing."

## The Correction Flywheel

Every correction you make is intent data. When you say "too formal, make it casual," you've just expressed a preference that applies to every future interaction if you let it.

```
Express intent  ->  Get output  ->  Correct  ->  Save correction as memory/skill
     ^                                                         |
     |                                                         v
     +------ Next time, intent is understood better -----------+
```

The people who get the most from AI aren't better at prompting. They've built better intent infrastructure. Their corrections compound. Their CLAUDE.md captures their thinking style. Their skills shape the AI's cognition. Eventually, they express raw intent and get excellent output because the system has learned what they mean, not just what they said.

## Common Intent Failures

**Over-specifying.** You've done the thinking and you're dictating the answer. The AI becomes a typist. Leave room for it to solve the actual problem.

**Under-specifying without context.** "Make it better" without saying better how. The intent is incomplete, not the prompt. Add the dimension: faster, cleaner, shorter, more persuasive, more specific.

**Not sharing ambient context.** The AI doesn't know this is for your boss, that you're in a hurry, that you hate bullet points, that the audience is 50-year-old PE millionaires. Context is intent.

**Treating corrections as failures.** The first output being wrong isn't a problem. It's a data point. The correction is more valuable than the original output because it reveals what you actually wanted.

## The Bar

When you can think out loud, in unstructured speech, about a complex problem, and the AI produces output that makes you say "yeah, that's what I was thinking but couldn't articulate yet," the intent infrastructure is working. That's the bar. Everything in this repo is designed to get you there.
