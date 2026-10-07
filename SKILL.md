---
name: visual-rabbit-hole
description: "Teach concepts through puzzles, a short visual explanation in chat, and an interactive HTML page with diagrams, quizzes, and side quests. Use for 'teach me', 'help me understand', deep dives, ELI5, rabbit holes, or /visual-rabbit-hole. Quick facts and explanations of code in the current repo do not trigger it."
---

# Visual Rabbit Hole

Make the learner feel they could have discovered the idea themselves. Start with a concrete puzzle, reveal a mechanism through a changing visual, and offer questions worth following. The chat gives the insight; the page lets the learner experiment and apply it.

## Choose the surfaces

- **New concept:** give the short chat explanation, then build an interactive page.
- **Quick / no page / just ELI5:** answer in chat only.
- **Follow-up or clarification:** answer the point directly in chat. Add a diagram if it helps.
- **Selected side quest / rabbit hole: X:** build the next explanation and page from that branch. Carry forward the useful model, labels, assumptions, and discoveries from the conversation instead of restarting.
- **Update this page:** revise the existing artifact or file, keeping solved answers only when the questions and answers remain unchanged.

Give a prediction moment, then explain in the same response. Pause for the user's answer only if they ask for an interactive chat session. Page quizzes and controls let them explore at their own pace.

## The chat

Aim for one screen:

1. A concrete puzzle or frustration that creates a need for the concept, followed by the key insight or analogy.
2. One compact text diagram showing a change, comparison, or sequence. Keep it around 60 columns wide and label what stays fixed.
3. A meaningful misconception or limit of the model, if relevant.

After building the page, finish with its actual link and a few side-quest questions. For chat-only requests, offer a next question only when useful. The page expands the same model and stays consistent with the chat.

## The page

Start from [references/template.html](references/template.html). Keep its quiz, stepper, copy-button, and tracker markup so the existing script works. Use one readable page with a table of contents; adapt section names to the subject.

1. **Setup:** pose the puzzle before revealing the concept. Include skippable beginner background where needed. Distinguish invented teaching scenarios from historical events. For interpretive subjects, explore a tension between perspectives rather than inventing a single correct mechanism.
2. **Intuition:** map a tangible analogy onto the idea, then work an example with actual numbers, names, or steps. Reuse one model and change a meaningful input or constraint. Show what changes, what stays fixed, and why the result follows. Introduce formal terms or equations when they sharpen understanding.
3. **Model limits / Gotcha:** explain where the analogy or simplifying assumption stops working. Correct a misconception that matters here, without claiming everyone makes it.
4. **Checkpoint:** three application questions on the core concept.
5. **Side quests:** three or four cards, each with a question as its title, a hook, a short lesson (roughly 150–300 words), a diagram, and two application questions. Let the user explore them in any order. Choose useful branches from:
   - **Go deeper:** uncover the next mechanism or change a constraint.
   - **Go sideways:** connect to another field, naming the specific shared structure and its limits. Include one well-supported connection.
   - **Break the model:** test an assumption or find a case the current picture cannot explain.

   End each quest with a copyable `rabbit hole: <question>` prompt. Include the parent concept and one relevant assumption when needed to make the continuation understandable in a fresh chat. The tracker marks a quest cleared when its questions are answered correctly; it does not gate access to other lessons.
6. **Sources:** link sources actually used, with a line explaining what each supports. Also place citations near claims when helpful.

A later page opens with the question it branched from and updates the useful parts of the previous visual. A short breadcrumb such as `Bottlenecks → Changing constraints → Queues` can orient a longer journey. Use conversation context and any context included in the copied prompt; ask briefly if a bare quest selection cannot be resolved.

## Quizzes

Test application to a new case, not recognition of a definition. Use medium difficulty, clear wording, three or four plausible options, and vary the correct option's position. Build distractors from misconceptions the lesson addresses.

Give every option feedback explaining the reasoning. Wrong answers stay retryable. For debated topics, test reasoning under stated premises rather than grading a contested opinion as fact.

Keep the template's best-effort, per-page progress storage. When revising quiz content or order in an existing page, change its storage key so stale answers cannot mark new questions solved.

## Visuals

Use two or three visual families consistently across the page and quests. Draw with inline SVG or HTML/CSS; reserve ASCII diagrams for chat. Label units and assumptions when they affect the result, and keep colors and labels consistent across states.

For motion, iteration, or a changing parameter, use the template's step-through or a small native control that reveals cause and effect. Provide captions so the explanation remains understandable without interaction. Use HTML lists for lists and `<pre>` for code or formulas. Keep controls keyboard-accessible and give diagrams meaningful text alternatives.

## Accuracy and voice

Talk like a curious friend at a whiteboard: short paragraphs, purposeful questions, and delight earned by the discovery. Be clear about what is established, simplified, debated, or uncertain. Distinguish an exact relationship from a suggestive resemblance.

Use available search tools for current, niche, uncertain, or high-stakes claims, and examples dependent on external facts. Prefer primary sources. If verification is unavailable, say so and stay within what can be supported.

## Delivery and checks

Use the host's available artifact or HTML preview tools. Follow relevant tool guidance when present; the skill must also work as a standalone HTML file without a particular publishing plugin.

For local delivery, use the user's requested location or the environment's output directory. Otherwise use `./rabbit-holes/YYYY-MM-DD-<slug>.html`. Open it with an available viewer and provide a clickable link. Reuse an existing file only when updating that explanation; keep separate explorations distinct.

Before delivery, replace the template placeholders and check the page's diagrams, questions, and links. When a browser is available, exercise the stepper, a wrong-answer retry, quiz feedback, quest completion, reload persistence, and the copy prompt. If browser verification is unavailable, report that limit.

For an example of the chat/page split and a three-turn journey, read [references/example-explanations.md](references/example-explanations.md).
