---
name: visual-rabbit-hole
description: "Teach a concept from any domain (science, math, business, philosophy, history, programming ideas): a quick ASCII-diagram explanation in chat, plus an interactive HTML page with why it exists, a vivid analogy, diagrams, a checkpoint quiz, and side quests down the rabbit hole, each with its own quiz. Use when the user wants to learn or deeply understand a concept: 'teach me X', 'help me understand X', 'deep dive into X', 'ELI5 X', 'rabbit hole on X', or /visual-rabbit-hole. Not for quick factual questions or for explaining code in the current repo."
---

# Visual Rabbit Hole

Teach one concept so the learner could have discovered it themselves (3Blue1Brown's philosophy), then send them down side quests that branch off it, and check every step with a quiz. The goal is understanding they can prove, not a page they skimmed.

## Two surfaces

The chat and the page do different jobs. Use both.

- **Chat (ASCII):** the quick, in-flow version. The learner gets the idea without leaving the terminal.
- **Page (HTML):** the depth: richer diagrams, step-throughs, quizzes and side quests.

## Modes

- **New concept** → chat answer first, then build the page.
- **"Quick" / "no page" / "just ELI5"** → chat answer only.
- **Follow-up or clarification** → chat only, short. Add a small ASCII diagram if it clarifies.
- **"Next quest" / a side-quest title / "rabbit hole: X"** → same as a new concept, opening with one line linking back to where it branched from.

## The chat answer

Short enough to read in one screen:

1. Two or three sentences: the problem this concept solves, then the analogy.
2. One ASCII diagram in a code block that shows what *changes* (before → after, or the same system in 2-3 states). Box-drawing characters (`┌─┐│└─┘├┤`) and arrows (`→ ← ↑ ↓`); keep it under ~60 columns so it doesn't wrap.
3. The Gotcha in one line.
4. The page link or path, and the side-quest titles as a list.

The page reuses this analogy and expands it; don't contradict the chat version.

## The page

One long page with a table of contents and section headers. No tabs for top-level structure. Sections in order:

1. **The Setup: what problem are we solving?** Make the learner feel the need for the idea before naming it. What frustration led someone to invent it? Include a short *Background* block for beginners, marked as skippable for readers who already know the field.
2. **The Intuition.** One vivid, physical analogy (two for complex concepts) that maps onto the real mechanism. Then work a concrete example with toy data: actual numbers, actual names, actual steps. Show what *changes*: a step-through ("Next" buttons over frames) or a slider beats a static picture whenever the concept involves motion, iteration or a parameter.
3. **The Gotcha.** A callout: "Most people think X, but actually Y." The misconception that trips people up most.
4. **Checkpoint.** 3 multiple-choice questions on the core concept (see Quizzes).
5. **Side Quests.** 3 or 4 quest cards. Mix:
   - **Go deeper** (2-3): the next branch down this concept, from accessible to advanced.
   - **Surprising connection** (1): the same structure in a completely different field. Explain *why* the connection exists.

   Each quest card: title + one-line hook, a lesson of 150-300 words with one diagram that reuses the page's diagram families, then 2 quiz questions. The last line of each quest is a copyable prompt, `rabbit hole: <quest title>`, for going further on its own page.
   The template's tracker shows "2 / 4 quests cleared". A quest is cleared when all its questions are answered correctly.
6. **Sources**, only if you searched the web. Links with one line each.

## Quizzes

The quiz is where the teaching sticks, so write it with care:

- Test understanding, not recall. The best questions make the learner *apply* the idea to a case the page didn't show ("If you doubled X, what happens to Y?").
- Medium difficulty, no trick wording. A reader who understood gets it; a skimmer doesn't.
- Distractors are real misconceptions, including the Gotcha, never obviously silly filler.
- Every option carries its own feedback explaining why it's right or wrong. Wrong answers stay retryable; the explanation is the lesson.
- 3-4 options; vary the position of the correct one.

## Diagrams

- Pick 2-3 diagram families for the page (e.g. a flow diagram, a before/after, a timeline) and reuse them across the main lesson and the quests, so the learner learns the visual language once.
- Inline SVG or plain HTML/CSS. ASCII belongs in the chat, not on the page. Label everything and put example data in the diagram itself.
- Lists are HTML lists. Code or formulas go in `<pre>` (the template styles it with `white-space: pre-wrap`).

## Writing

Classic style with the clarity and flow of Martin Kleppmann: confident, concrete, conversational, addressed to "you". Smooth transitions between sections. Rhetorical questions that let the learner sit with a puzzle for a beat before resolving it. Bold key terms on first use.

## Web search

Search when the concept involves recent developments or current data, when a real-world example would make the analogy concrete, for niche details, and to verify scientific, medical or technical claims. Don't search for well-established material. Cite what you used in Sources.

## Delivery

Start from [references/template.html](references/template.html). It has the shell, light/dark theming, table of contents, quiz component and quest tracker. Fill in the content and keep its quiz markup so the script works.

- **If an Artifact tool is available**: load the `artifact-design` skill (and `artifact-diagramming` when drawing), write the file to the scratchpad, publish it, and give the user the link.
- **Otherwise**: write `~/rabbit-holes/YYYY-MM-DD-<slug>.html` (the date prefix keeps them time-sorted) and open it (`open` on macOS, `xdg-open` on Linux).

Then finish the chat answer (see above) with the link or path and the quest titles.
