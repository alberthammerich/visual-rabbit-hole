# visual-rabbit-hole

**Come for an explanation. Leave with a better question.**

An agent skill for curious people. Start with a puzzle, watch an idea take shape, and follow whichever thread catches your attention.

## a taste

You make one machine twice as fast. The factory produces exactly as much.

Why?

Imagine three machines in a line, with plenty of material to process. These are their maximum rates:

```text
       CUT             PAINT            PACK
   [12/hour] ──────→ [3/hour] ──────→ [12/hour]

                  Output: 3/hour
```

Double the cutting speed:

```text
       CUT             PAINT            PACK
   [24/hour] ──────→ [3/hour] ──────→ [12/hour]
                       ↑
              still setting the pace

                  Output: 3/hour
```

More cutting capacity. Painting still finishes only three items an hour.

You've just met a **bottleneck**. In this simplified line, the slowest stage sets the maximum steady output. Speeding up another stage can leave more unfinished work waiting for paint.

Now there's somewhere to go:

- **Go deeper:** What happens after you upgrade the painting machine?
- **Go sideways:** Where is the painting machine in your own workday?
- **Break the model:** What if the machines keep stopping and starting?

Pick a thread. Keep the picture. See what changes.

## install

```bash
npx skills add alberthammerich/visual-rabbit-hole
```

Choose your agent in the installer. Supports Claude Code, Codex, Cursor, OpenCode, and [other compatible agents](https://github.com/vercel-labs/skills#supported-agents).

## follow your curiosity

Ask your agent to use visual-rabbit-hole:

> Use visual-rabbit-hole to explain recursion.

> Help me understand entropy with visual-rabbit-hole.

> Use visual-rabbit-hole to explore why cities grow where they do.

Then follow what interests you:

> Show me what happens if we change that assumption.

> Where does this analogy stop working?

> Take me down the second rabbit hole.

Explanations build on the conversation: the useful diagram stays, the model grows, and each branch starts from what you've already explored. For a quick clarification, ask directly. For a more interactive session, ask to predict what happens before the reveal.

## the idea

Intuition first. Give the question a reason to matter, then make the mechanism visible. Use an analogy while it helps, and show where it breaks. Follow connections that share something specific: a constraint, a feedback loop, a pattern.

Text diagrams work right in chat. When the agent supports richer visuals, a small interactive illustration can help you explore what changes. Sources ground explanations when facts need checking.

Science, code, history, philosophy—start wherever you're curious.

See a [three-turn exploration](references/example-explanations.md) or read the [skill instructions](SKILL.md).

## contributing

Bring a question that deserves a better explanation.

For changes to the skill, include a short before-and-after conversation showing what improves. A clearer diagram, a stronger question, or a more honest analogy is a good place to start.
