# Intent: The Only Thing That Matters

You don't need to write good prompts. You need to know what you want and be able to say it, even imperfectly. The AI's job is to parse your intent, not your grammar.

This guide is about building the muscle of expressing intent clearly and building systems that help you discover and refine your intent over time.

## Intent Is Not a Prompt

A prompt is a transaction. You write something, you get something back. Intent is a relationship. You express direction, the AI figures out the path, you course-correct, and the system gets better at understanding you.

Match the shape of your request to the shape of the problem.

**The problem is clear:** "Write a function that filters even numbers from a list and sums them."
You've already decomposed the problem. You know the shape of the solution. Just say it. Fast, clean, done.

**The outcome is clear, the path isn't:** "I need to process a list of numbers and pull out a specific subset. The subset rule might change later."
You know where you're going but you want the AI's judgment on how to get there. Leave room for it to make implementation decisions you might not have thought of.

**Something is wrong but you're not sure what:** "I'm building a data pipeline and I keep writing the same filtering logic everywhere. Fix that."
You're pointing at a smell, not a solution. This is where AI adds the most value: it can see patterns across your whole codebase that you can't hold in your head at once.

None of these is better than the others. They're different tools for different situations. The mistake is using only one. Most people default to the first (dictating the solution) and miss the leverage of the second and third (letting the AI solve the bigger problem).

## Thinking Out Loud Is Valid

You don't need to have your thoughts organized before you speak. Speech-to-text, stream of consciousness, half-formed ideas, "I don't know exactly what I want but it's something like..." are all valid inputs.

If you say "I kind of want to, you know, make the thing that does the stuff with the users, like maybe a dashboard or something?" a well-set-up AI will hear "user-facing view" and start asking what data matters to you.

The thing that actually holds people back isn't the AI misunderstanding them. It's self-censoring. Spending five minutes crafting the perfect request when you could have just said the messy version and been done. The AI handles messy fine. Stop polishing your inputs and start iterating on the outputs.

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
