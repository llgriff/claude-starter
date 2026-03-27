# Intent

How you express what you want determines what you get. This isn't about prompt engineering. It's about thinking clearly about the shape of your problem and communicating it in a way that lets AI actually help.

## Match Your Approach to the Problem

Different problems want different kinds of requests.

**The problem is clear:** "Write a function that filters even numbers from a list and sums them."
You've decomposed it. You know the shape. Say it, get it, move on.

**The outcome is clear, the path isn't:** "I need to process a list of numbers and pull out a specific subset. The subset rule might change later."
You're giving the AI room to make implementation decisions. You might get something better than what you would have specified.

**Something is wrong but you're not sure what:** "I'm building a data pipeline and I keep writing the same filtering logic everywhere. Fix that."
You're pointing at a smell. The AI can see patterns across your whole codebase that you can't hold in your head at once. This is where the leverage lives.

All of these are valid. The skill is knowing which one fits the moment.

## Thinking Out Loud Is Valid

You don't need organized thoughts before you speak. Stream of consciousness, half-formed ideas, "I don't know exactly what I want but it's something like..." are all fine. The AI handles messy input well. Stop polishing your requests and start iterating on the outputs.

## The Craft: How Beer and Zyn Express Intent

Look at the `/beer` and `/zyn` skills in this repo. They're examples of intent expression at a high level.

The intent behind `/beer` is simple: "I need you to be creative." But saying "be creative" doesn't actually change anything. It's too vague to act on. So the skill expresses that intent with specificity and structure:

- It describes a *state* (the aperture widens, the inner editor steps back, threads get followed)
- It defines *behaviors* (question the frame, find your voice, let things collide)
- It sets *boundaries* (one beer, not ten: loose, not sloppy)
- It includes *self-checks* (did I go somewhere interesting or stay on the rails?)

The intent behind `/zyn` is "I need you to focus." Same problem: too vague on its own. So it does the same thing from the opposite direction:

- State: the aperture narrows, conviction goes up, filler becomes uncomfortable
- Behaviors: see the real target, name what excellent looks like, see your failure modes
- Boundaries: alert, not anxious; precise, not overwrought
- Self-checks: did I hit the target or a target nearby?

The craft is in the balance. Both skills are specific enough to actually change behavior but open enough to apply to any task. They don't tell the AI what to produce. They tell the AI how to think while producing it. That's the difference between a prompt template and an intent expression.

You can build skills like this for any mode you work in. A "deep research" mode. A "explain it to a non-technical person" mode. A "I'm debugging and I need hypotheses, not solutions" mode. The pattern is the same: describe the state, define the behaviors, set boundaries, include self-checks.

## Intent Layers

Your intent operates at multiple levels simultaneously.

**This request:** "Rename this function." Direct. The AI executes.

**This session:** "I'm refactoring the auth module." Shapes how the AI interprets every request in the conversation.

**This project:** "I'm building a task manager in TypeScript." Lives in your project-level CLAUDE.md. Every conversation inherits it.

**This is who I am:** "I'm a backend engineer who thinks in systems, prefers explicit over clever, and hates unnecessary abstractions." Lives in your global CLAUDE.md and memory. Shapes everything.

Most people only express the first layer. The more layers you fill in, the less you have to say in each request, because the AI already knows the context.

## Building Intent Infrastructure

Skills, commands, memory, and CLAUDE.md are all infrastructure for expressing intent. Each one captures a different layer:

**CLAUDE.md** captures who you are and how you work. It's the ambient context that every conversation starts with.

**Memory** captures accumulated preferences and corrections. Each "always do X, never do Y" sharpens the picture.

**Skills** capture thinking modes. When you need creativity, focus, rigor, empathy, or any other cognitive shape, a skill expresses that intent once and applies it every time.

**Commands** capture workflow patterns. When you notice yourself expressing the same sequence of intent repeatedly, a command captures it.

## The Flywheel

Every correction you make is intent data.

```
Express intent  ->  Get output  ->  Correct  ->  Save as memory/skill
     ^                                                      |
     |                                                      v
     +--------- Next time, intent understood better --------+
```

The people who get the most from AI aren't better at articulating what they want. They've built systems that understand what they mean. Their corrections compound. Eventually, raw unpolished intent produces excellent output because the infrastructure fills in what wasn't said.
