# visual-rabbit-hole

an agent skill that explains any concept like you're talking to a curious friend with a whiteboard.

you get the quick version right in chat, with an ascii diagram. then it builds you an interactive page: why the idea exists, an analogy that actually hits, diagrams you can step through, and the gotcha everyone misses. then a quiz to prove you got it, and side quests down the rabbit hole, each with its own quiz. clear them all.

works for anything — physics, philosophy, finance, code, whatever you're trying to wrap your head around.

## install

```bash
npx skills add albertbethlowsky/visual-rabbit-hole
```

works with claude code, cursor, codex, opencode, and [40+ other agents](https://github.com/vercel-labs/skills#available-agents).

## use

ask it to teach you something:

- "teach me recursion"
- "help me understand inflation"
- "deep dive into how mRNA works"
- "rabbit hole on monads"

pages land in `~/rabbit-holes/YYYY-MM-DD-<slug>.html` (or as a claude.ai artifact when the agent supports it). quiz progress is saved in your browser. it searches the web when it needs real-world examples or current info.

## contributing

PRs are open. you're welcome to contribute.

but be real with yourself before you open one: if it changes core ideas or isn't well thought through, it's getting closed. think it through, make it sharp, then submit.
